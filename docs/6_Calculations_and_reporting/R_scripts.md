---
layout: default
title: R scripts for calculation and reporting
parent: Calculations and reporting
nav_order: X
---

# R scripts for calculation and reporting

{: .note }
If collecting data using the Kobo form, the assessors do not have to do any direct calculation of indicators.


While manual calculation is certainly possible (e.g., using Excel), we have created a series of R scripts to process the kobo output and estimate the indicators. These scripts account for variable inputs (e.g., point and range values for Nc) and will reduce data conversion errors. They are available at https://github.com/AliciaMstt/GeneticIndicators  and are explained below. 

## 
Functions to extract the data for each indicator from the Kobo form output:

The following R functions take as input a data frame with the data downloaded from the Kobo form and **extract and format the data** in order to estimate each of the Genetic Diversity Indicators.

See examples of the input and output data frames in the "Estimating indicator…" sections below. And see the notebook [quality check](https://aliciamstt.github.io/GeneticIndicators/1_quality_check.html) and [cleaning for the multinational pilot assessment](https://aliciamstt.github.io/GeneticIndicators/2_cleaning.html), and [section 4](https://aliciamstt.github.io/GeneticIndicators/#4-pipeline-used-in-the-multinational-assessment) of this [repository](https://github.com/AliciaMstt/GeneticIndicators) for detailed examples of how these functions were used as part of a pipeline.

Functions:

Functions:

* [get_indicator1_data()](https://github.com/AliciaMstt/GeneticIndicators/blob/main/get_indicator1_data.R): extracts and formats the data needed to estimate the Ne 500 indicator (the proportion of populations within species with an effective population size Ne greater than 500). **In the kobo output, population data is in different columns, this function transforms it so that population data is in rows.** This is needed for downstream analyses. Note that if the [Population information template](https://github.com/AliciaMstt/GeneticIndicators#population-information-template) was used (species with more than 25 populations) you will need to run an additional step before analysing the data, see below (Getting the population data if the template was used). In the output, each population is a row, and there are as many rows per taxon as there are populations within it.


* [get_indicator2_data()](https://github.com/AliciaMstt/GeneticIndicators/blob/main/get_indicator2_data.R): outputs a data frame with the data needed to estimate the PM indicator (the proportion of maintained populations within species). Each row is a taxon.


* [get_indicator3_data()](https://github.com/AliciaMstt/GeneticIndicators/blob/main/get_indicator3_data.R): outputs a data frame with the data needed to estimate the genetic monitoring indicator (number of species in which genetic diversity has been or is being monitored using DNA-based methods). Each row is a taxon.


* [get_metadata()](https://github.com/AliciaMstt/GeneticIndicators/blob/main/get_metadata.R): extracts the metadata for taxa and indicators, in some cases creating new useful variables, like taxon name (joining Genus, species, etc) and if the taxon was assessed only a single time or multiple times. Each row is a taxon.


Arguments:
`kobo_output` = a data frame object read into R from the `.csv` file resulting from exporting the Kobotoolbox data as explained above.

### Getting the population data if the template was used


If information of more than 25 populations was available for the Ne >500 indicator, it was collected in the [template to upload data instead of using the kobo form](https://github.com/AliciaMstt/GeneticIndicators#population-information-template). In that case, the data gets stored in a separate attachment for each taxa, which you need to download and merge with the rest of the data.

The url to the attachment file is available in the kobo output data under the variable `pop_tabular_file_URL`. This url could be used to download each of the attachments with the function:

[download\_kobo\_attachment()](https://github.com/AliciaMstt/GeneticIndicators/blob/main/download_kobo_attachment.R): downloads an attachment of a kobo survey.

Arguments:

`url = `url to the file to download. For example for pop data downloaded using the template, the url is stored in the column pop_tabular_file_URL of kobo_clean

`local_file_path `= local path (and file name, including extension) where to save file
username = your kobo username, should have permissions to download this data

`password` = your kobo password

Then, the function:
* [process_attached_files()](https://github.com/AliciaMstt/GeneticIndicators/blob/main/process_attached_files.R) processes the original attachment files to make them compatible with how population data is expected to estimate the Ne >500 indicator.

Importantly, it checks the columns that **should be numbers**, but they may have been stored as characters because "," "-" "(" or other characters may have been typed. The function will try to correct this, **which may change the original data**. Please manually check any file flagged as transformed in the log produced by the function to ensure everything is correct.

The output from `process\_attached\_files()` is a data frame that can be joined to the data frame output from get_indicator1_data() to estimate the indicator values.


### Estimate the Ne 500 indicator

To estimate the Ne 500 indicator you need the data in the format provided by [get_indicator1_data()](), i.e. **each population is a row** and the population size data (either **Ne** or **Nc**) is provided in different columns.


|taxon          |population |Name            |    Ne| NeLower| NeUpper|NeYear |GeneticMarkers             |NcType   |NcMethod        |NcRange          |
|:--------------|:----------|:---------------|-----:|-------:|-------:|:------|:--------------------------|:--------|:---------------|:----------------|
|Alces alces    |pop1       |North           |  4950|      NA|      NA|2020   |whole\_genome\_sequence\_data |Nc\_range |Nc\_method\_count |more\_5000\_bymuch |
|Alces alces    |pop2       |South           |   194|      NA|      NA|1980   |whole\_genome\_sequence\_data |Nc\_range |Nc\_method\_count |more\_5000\_bymuch |
|Alces alces    |pop3       |Transition zone | 11519|      NA|      NA|2020   |whole\_genome\_sequence\_data |Nc\_range |Nc\_method\_count |more\_5000\_bymuch |
|Siluris glanis |pop1       |Båven           |    12|       6|      33|2004   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |
|Siluris glanis |pop2       |lower Emån      |    13|       7|      31|2004   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |
|Siluris glanis |pop3       |Upper Emån      |    11|       5|      26|2010   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |
|Siluris glanis |pop4       |Möckeln         |    13|       7|      30|2010   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |
|Siluris glanis |pop5       |Försjön         |     9|       4|      26|2006   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |
|Siluris glanis |pop6       |Helgeå          |    11|       6|      26|2010   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |

If **Nc** was provided, it is necessary to **transform it to Ne** by multiplying it for a ratio. This is done with the function:

 
 * [`transform_to_Ne()`](https://github.com/AliciaMstt/GeneticIndicators/blob/main/transform_to_Ne.R): This functions gets the Nc data from point or range estimates and transforms it to Ne 
 multiplying for a ratio Ne:Nc (defaults to 0.1 if none provided)
 
 Arguments: 
 `ind1_data`: data for Ne 500 indicator as produced by `get_indicator1_data()`
 `ratio`: desired Ne:Nc ratio. Should range 0-1. Defaults to 0.1
  
 Output:
 Original ind1\_data df with two more columns:
 `Nc\_from\_range`: (conversion of "more than..." to numbers)
 `Ne\_from\_Nc`: Ne estimated from NcRange or NcPoint  
 `Ne\_combined`: Ne estimated from Ne if Ne is available, otherwise, from Nc

Example: `ind1_data<-transform_to_Ne(ind1_data = ind1_data, ratio = 0.1)` 

Output selecting the most relevant columns:



|taxon          |population |Name            |    Ne| NeLower| NeUpper|NeYear |GeneticMarkers             |NcType   |NcMethod        |NcRange          | Nc\_from\_range| Ne\_from\_Nc| Ne\_combined|
|:--------------|:----------|:---------------|-----:|-------:|-------:|:------|:--------------------------|:--------|:---------------|:----------------|-------------:|----------:|-----------:|
|Alces alces    |pop1       |North           |  4950|      NA|      NA|2020   |whole\_genome\_sequence\_data |Nc\_range |Nc\_method\_count |more\_5000\_bymuch |         10000|       1000|        4950|
|Alces alces    |pop2       |South           |   194|      NA|      NA|1980   |whole\_genome\_sequence\_data |Nc\_range |Nc\_method\_count |more\_5000\_bymuch |         10000|       1000|         194|
|Alces alces    |pop3       |Transition zone | 11519|      NA|      NA|2020   |whole\_genome\_sequence\_data |Nc\_range |Nc\_method\_count |more\_5000\_bymuch |         10000|       1000|       11519|
|Siluris glanis |pop1       |Båven           |    12|       6|      33|2004   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |           500|         50|          12|
|Siluris glanis |pop2       |lower Emån      |    13|       7|      31|2004   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |           500|         50|          13|
|Siluris glanis |pop3       |Upper Emån      |    11|       5|      26|2010   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |           500|         50|          11|
|Siluris glanis |pop4       |Möckeln         |    13|       7|      30|2010   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |           500|         50|          13|
|Siluris glanis |pop5       |Försjön         |     9|       4|      26|2006   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |           500|         50|           9|
|Siluris glanis |pop6       |Helgeå          |    11|       6|      26|2010   |microsatellites            |Nc\_range |Nc\_method\_count |less\_5000\_bymuch |           500|         50|          11|

Lastly, you can estimate the Ne 500 indicator with the function:

* [`estimate_indicator1()`](https://github.com/AliciaMstt/GeneticIndicators/blob/main/estimate_indicator1.R): This functions estimates the Ne 500 indicator, ie for each assessment of a taxon it calculates the proportion of populations within it which are above Ne 500. Notice it uses the assessment id `X_uuid` (unique record of a taxon), because a single taxon could be assessed by different countries or more than once with different parameters. The output is a new dataframe with a row per assessment, metadata, new columns used to estimate the indicator (number of pops) and the indicator value.
 
Arguments: 
`ind1_data`: population size data as produced by `get_indicator1_data()` and after running `transform_to_Ne()`.

Example: `indicator1<-estimate_indicator1(ind1_data = ind1_data)`

Output selecting the most relevant columns:

|X\_uuid                               |taxon                   |country\_assessment | n\_pops| n\_pops\_Ne\_data| n\_pops\_more\_500| indicator1|
|:------------------------------------|:-----------------------|:------------------|------:|--------------:|---------------:|----------:|
|010d85cd-51d6-4c20-86ee-ebdb21bef77b |Etheostoma chienense    |US                 |      2|              1|               1|          1|
|018d6a54-b069-4bdb-845c-85249bdf2bbb |Graptopetalum bartramii |US                 |     47|             46|               0|          0|
|019bd95f-b8e9-4ef5-9041-ea4e40d81e64 |Cerambyx cerdo          |Sweden             |      1|              1|               0|          0|
|01b10b29-9e13-472b-9bf3-585e990c6905 |Spheniscus demersus     |South Africa       |      1|              1|               1|          1|
|0301e6b3-b4e3-4fdc-9029-d5a375e32f1b |Posidonia oceanica      |France             |      3|              3|               3|          1|
|037d6c8f-7b29-4654-98da-18e31b23c1e0 |Etheostoma maydeni      |US                 |      4|              2|               2|          1|
|03f03179-14bb-4c15-a4fd-5c660b0647c1 |Parahyaena brunnea      |South Africa       |      1|              1|               1|          1|
|0586b61e-7805-42d7-84e1-dd8a6983c941 |Bombina variegata       |Belgium            |     12|             12|               0|          0|
|065a53ba-051b-440c-a189-9a3c47d02571 |Caracal caracal         |South Africa       |      1|              1|               0|          0|

See the notebook of the [analyses and figures for the multinational pilot assessment](https://aliciamstt.github.io/GeneticIndicators/3_manuscript_figures_analyses.html#estimate-indicators) and [section 4 of this README](https://aliciamstt.github.io/GeneticIndicators/#4-pipeline-used-in-the-multinational-assessment) for detailed examples of how these functions were used as part of a pipeline.

### Estimate the PM indicator 

To estimate the PM indicator you need the data in the format provided by `get_indicator2_data()`, i.e. **each row is a taxon** of a single assessment, and the number of extant and extinct populations are provided. Example selecting the most relevant columns:


|country\_assessment |taxon                    | n\_extant\_populations| n\_extint\_populations|
|:------------------|:------------------------|--------------------:|--------------------:|
|Sweden             |Alces alces              |                    3|                    0|
|Sweden             |Siluris glanis           |                    6|                    6|
|Sweden             |Dendrocopos leucotos     |                    5|                   12|
|South Africa       |Encephalartos latrifrons |                    1|                    0|
|South Africa       |Capensibufo rosei        |                    2|                    4|
|France             |Galemys pyrenaicus       |                    3|                    0|
|France             |Luscinia svecica         |                    2|                   NA|
|France             |Taxus baccata            |                    1|                   NA|
|France             |Angelica heterocarpa     |                    4|                   NA|



To estimate the PM indicator (proportion of populations maintained within species) you only need to divide the number of currently existing populations (`n_extant_populations`) over the total number of populations, which sums the number of extant and extinct populations (`n_extint_populations`). Notice that the PM indicator can only be estimated if there is no missing data in the number of populations.

Example:

```
ind2_data$indicator2<- ind2_data$n_extant_populations / (ind2_data$n_extant_populations + ind2_data$n_extint_populations)
```

Output selecting the most relevant columns:


|country\_assessment |taxon                    | n\_extant\_populations| n\_extint\_populations| indicator2|
|:------------------|:------------------------|--------------------:|--------------------:|----------:|
|Sweden             |Alces alces              |                    3|                    0|       1.00|
|Sweden             |Siluris glanis           |                    6|                    6|       0.50|
|Sweden             |Dendrocopos leucotos     |                    5|                   12|       0.29|
|South Africa       |Encephalartos latrifrons |                    1|                    0|       1.00|
|South Africa       |Capensibufo rosei        |                    2|                    4|       0.33|
|France             |Galemys pyrenaicus       |                    3|                    0|       1.00|
|France             |Luscinia svecica         |                    2|                   NA|         NA|
|France             |Taxus baccata            |                    1|                   NA|         NA|
|France             |Angelica heterocarpa     |                    4|                   NA|         NA|

See the n[otebook of the analyses and figures for the multinational assessment](https://aliciamstt.github.io/GeneticIndicators/3_manuscript_figures_analyses.html#estimate-indicators) and [section 4 of this README](https://aliciamstt.github.io/GeneticIndicators/#4-pipeline-used-in-the-multinational-assessment) for detailed examples of how these functions were used as part of a pipeline.

### Estimate the genetic monitoring indicator

The genetic monitoring indicator refers to the number (count) of taxa by country in which genetic monitoring is occurring. This is stored in the variable `temp_gen_monitoring` as a “yes/no” answer for each taxon.

To estimate the genetic monitoring indicator you need the data in the format provided by `get_indicator3_data()`, i.e. **each row is a taxon** and the column `temp_gen_monitoring` is provided along with other variables that provide metadata.

Example selecting the most relevant variables:

|country\_assessment |taxon                    |multiassessment   |temp\_gen\_monitoring |gen\_studies |gen\_monitoring\_years |
|:------------------|:------------------------|:-----------------|:-------------------|:-----------|:--------------------|
|sweden             |Alces alces              |single\_assessment |yes                 |pop         |1839-2020            |
|sweden             |Siluris glanis           |single\_assessment |yes                 |phylo\_pop   |1980-2018            |
|sweden             |Dendrocopos leucotos     |single\_assessment |no                  |phylo\_pop   |NA                   |
|south\_africa       |Encephalartos latrifrons |single\_assessment |no                  |pop         |NA                   |
|south\_africa       |Capensibufo rosei        |single\_assessment |yes                 |phylo\_pop   |2008;2015            |
|france             |Galemys pyrenaicus       |single\_assessment |yes                 |phylo\_pop   |2011-2013            |
|france             |Luscinia svecica         |single\_assessment |no                  |phylo\_pop   |NA                   |
|france             |Taxus baccata            |single\_assessment |no                  |phylo\_pop   |NA                   |
|france             |Angelica heterocarpa     |single\_assessment |no                  |pop         |NA                   |

To estimate the indicator, we only need to count how many "yes" are in `temp_gen_monitoring`, keeping only one of the records if the taxon was multiassessed. For example with `dplyr`:

```
ind3_data %>%
                 # keep only one record if the taxon was assessed more than once within the country
                 select(country_assessment, taxon, temp_gen_monitoring) %>%
                 filter(!duplicated(.)) %>%

                 # count "yes" in tem_gen_monitoring by country
                 filter(temp_gen_monitoring=="yes") %>%
                 group_by(country_assessment) %>%
                 summarise(n_taxon_gen_monitoring= n()) 
```

The output is the number of taxa with genetic monitoring per country (or per any other variable used in `group_by`):

|country\_assessment | n\_taxon\_gen\_monitoring|
|:------------------|----------------------:|
|australia          |                     10|
|belgium            |                     10|
|france             |                      7|
|mexico             |                      7|
|south\_africa       |                      5|
|sweden             |                     20|
|united\_states      |                      6|

See the n[otebook of the analyses and figures for the multinational assessment](https://aliciamstt.github.io/GeneticIndicators/3_manuscript_figures_analyses.html#estimate-indicators) and [section 4 of this README](https://aliciamstt.github.io/GeneticIndicators/#4-pipeline-used-in-the-multinational-assessment) for detailed examples of how these functions were used as part of a pipeline.

### Dependencies

Functions were developed and tested using:

* R version 4.2.1
* utile.tools_0.2.7
* dplyr_1.0.9
* tidyr_1.2.0

If you are getting a message with something like "**Error in `mutate()`** ... **Caused by error in `na_if()`:**" it is likely because you have a different version of dplyr or tidyr than above.

