---
layout: default
title: Recommended minimum data and metadata variables for calculating genetic diversity indicators
parent: Data collection
nav_order: 4
---

# Recommended minimum data and metadata variables for calculating genetic diversity indicators

This section outlines the minimum data needed to calculate the genetic diversity indicators for a particular species within a country (Table 1), as well as additional metadata variables that are optional though can be useful for reproducibility, traceability and analyses (Table 2). 

Data for each variable can be recorded using any tool (e.g. Excel, scripts for extracting data from existing databases), but you can also use the user-friendly Kobotoolbox described above. Thus for each variable, we also provide the name of that variable in the Kobo form, for anyone not using the Kobo form. Using this name for the variables is also needed for the R processing scripts to run accordingly, thus, we suggest using the following variable names if the provided scripts would be used. 

{: .note }
Although the taxonomic information of the species is necessary to gather data and perform the assessment of the genetic diversity indicators, for public reports it is possible to obscure the taxonomic information in cases where making this information public could harm the species conservation. In fact, none of the information collected is required to be made public.

### Table 1 - Variables strictly needed to perform the assessment and estimate genetic diversity indicators.

<style>
table th:first-of-type {
    width: 10%;
}
table th:nth-of-type(2) {
    width: 30%;
}
table th:nth-of-type(3) {
    width: 20%;
}
table th:nth-of-type(4) {
    width: 20%;
}
table th:nth-of-type(5) {
    width: 20%;
}
</style>

| Section | Variable description | Type | Example | Variable name in Kobotoolbox form or processing scripts |
|---|---|---|---|---|
| **Assessment** |  |  |  |  |
|  | Country of assessment  | Categorical | Mexico | country_assessment |
|  | Year of the assessment  | Date Year | 2023 | year_assessment |
|  | A unique id for the assessment (automatically generated if using Kobo) | Character text | 87eb6bd2-58cb-4def-9b0c-fbea85304e41 | X_uuid |
| **Taxon** |  |  |  |  |
|  | Scientific name of the taxon (including genus, species and any infraspecific epithet) being evaluated | Character text | Juniperus blancoi | taxon |
| **Proportion Maintained (PM) indicator** |  |  |  |  |
|  | Number of extant (known) populations within the country of assessment | Integer | 8 | n_extant_populations |
|  | Number of extinct (known) populations within the country of assessment. | Integer | 2 | n_extinct_populations |
| **Population size data for Ne 500 indicator** |  |  |  |  |
|  | Population id unique within the species (automatically generated if using Kobo) | Character text | pop1 | population |
|  | Point estimate of the Ne of the population, if available from genetic data  | decimal | 320 | Ne |
|  | The range of the population census size,  if the population size type selected is Nc_range. See “Quantitative range or qualitative estimates” in [How to get the Nc?](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Populations_sizes.html#how-to-get-the-nc) | Categorical | less_5000_bymuch | NcRange |
|  | NcRange values transformed  to numeric values, if NcRange was provided. (See “Quantitative range or qualitative estimates” in [How to get the Nc?](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Populations_sizes.html#how-to-get-the-nc)) Single Nc value for analysis, estimated from NcRange values. NcRange values can be converted into a single number using the following guidelines:  If NcRange is 'more than 5000 by much', Nc_from_range = 10000; 'more than 5000' = 5500; 'range includes 5000 = 5001; 'less than 5000' = 4050;  'less than 5000 by much' = 500 | Integer | 5500 | Nc_from_range |
|  | Ne estimate based on Nc, if Nc was provided. Calculated by multiplying Nc by a ratio (0.1 default or other) | Numeric | 300 | Ne_from_Nc |
|  | Single Ne estimated used for analysis for this population. Ne from genetic data has preference. If not available, Ne_from_Nc can be used. | Numeric | 320 | Ne_combined |
| **DNA-based monitoring indicator** |  |  |  |  |
|  | Whether genetic studies have been conducted in the assessed species, and if so of what type - phylogenetic / phylogeographic studies, population-level studies or both. | Categorical | phylo_pop | gen_studies |
|  | Whether temporal genetic monitoring has been conducted for one or more populations of this species | Categorical | yes | temp_gen_monitoring |
|  | Years during which the genetic monitoring has taken place | Date Year | 2008;2015 | gen_monitoring_years |


### Table 2 - Optional metadata variables useful for reproducibility, traceability and other analyses

| Section | Variable description | Type | Example | Variable name in Kobotoolbox form or processing scripts |
|---|---|---|---|---|
| **Assessment** |  |  |  |  |
|  | Name of assessor | Character text | Alicia Mastretta-Yanes | name_assessor |
|  | Whether the assessment of the species was done a single time (single_assessment) or more than once (multiassessment). See [How to account for uncertainty](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/uncertainty.html) section. | Categorical | single_assessment | multiassessment |
| **Taxon** |  |  |  |  |
|  | Taxonomic Authority and year for the species (or subspecies/variety) being assessed. | Character text | (Martinez, 1946) | scientific_authority |
|  | Taxonomic Group according to a desired classification useful for summaries. *  | Categorical | mammal | taxonomic_group |
|  | The most widely used common name(s) for the species, followed by the language in brackets. ^ | Character text | Cape buffalo (EN); southern savannah buffalo (EN) | common_name |
|  | GBIF taxon id ^ | Integer | 2684495 | GBIF_taxonID |
|  | Source of species population information (literature reference, website link, expert consultation). If more than once source was used, they are separated by semicolon ";" | Character text | Mastretta-Yanes, A., Wegier, A., Vázquez-Lobo, A., & Piñero, D. (2012). Distinctiveness, rarity and conservation in a subtropical highland conifer. Conservation Genetics, 13(1), 211–222. https://doi.org/10.1007/s10592-011-0277-y ;  Moreno-Letelier, A., Mastretta-Yanes, A., & Barraclough, T. G. (2014). Late Miocene lineage divergence and ecological differentiation of rare endemic Juniperus blancoi: Clues for the diversification of North American conifers. New Phytologist, 203(1), 335–347. https://doi.org/10.1111/nph.12761 ; Experts Socorro González-Elizondo and Alicia Mastretta-Yanes; https://enciclovida.mx/especies/155216-juniperus-blancoi | source_populations |
| **Pop size for Ne 500** |  |  |  |  |
|  | Population name | text | Gironde | name |
|  | Whether the population is historically natural or was introduced, re-introduced or reinforced. See [Glossary](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/7_Glossary/Glossary.html#glossary). | Categorical | reinforced | Origin |
|  | If the population was  introduced, re-introduced or reinforced, year or years in which this was done.  | text | 1995; 2007; 2008; 2009; 2010; 2011; 2012; 2013; 2014 | IntroductionYear |
|  | Lower limit of the Ne confidence interval for the population, if available. | decimal | 238 | NeLower |
|  | Upper limit of the Ne confidence interval for the population, if available.  | decimal | 405 | NeUpper |
|  | Year or years  in which the data was sampled to estimate Ne for the population | text | 2011-2014 | NeYear |
|  | Genetic markers used to estimate Ne for this population. | Categorical | microsatellites | GeneticMarkers |
|  | Method used to calculate Ne for the population. | Categorical | temporal_allele | MethodNe |
|  | References of all relevant sources reporting on effective population size for the population. Separated by a semicolon (;). | text | daSilva&Tolley 2018. Conservation genetics of an endemic and threatened amphibian (Capensibufo rosei): a leap towards establishing a genetic monitoring framework. Conservation genetics 19:349-363. doi: 10.1007/s10592-017-1008-9 | SourceNe |
|  | Whether the census population size (Nc) is a point or range estimate for the population  | character text | Nc_point | NcType |
|  | Year or years in which the Nc was estimated for the population (year when the sampling was done, not when it was published) | text | 2010 | NcYear |
|  | Method to calculate Nc for the population. See options in [How to estimate Nc?](8https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Populations_sizes.html#how-to-get-the-nc) | Categorical | Nc_method_count | NcMethod |
|  | The point estimate of the population size, if the population size type selected is Nc_point. See “Point estimates in [How to get the Nc?](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Populations_sizes.html#how-to-get-the-nc)” | Integer | 2168 | NcPoint |
|  | The lower limit of the point estimate of the population size, if the population size type (Nc_type_pop*) selected is Nc_point. | Integer | 2040 | NcLower |
|  | The upper limit of the point estimate of the population size, if the population size type (Nc_type_pop*) selected is Nc_point. | Integer | 2312 | NcUpper |
|  | References of all relevant sources reporting on census population size for each population. Separated by a semicolon (;). | Character text | Becker, F. 2017. Estimating the Population Size of a Rare and Elusive Species: the Case of Roses Mountain Toadlet. MSc thesis. University of Cape Town. | SourceNc |
|  | Source of the single Ne estimate used for analysis (Ne_combined) - genetic data, Nc point estimate or Nc range estimate. | Categorical | genetic data | Ne_calculated_from |
| **Ne:Nc ratio for the Ne 500 indicator** |  |  |  |  |
|  | Ne:Nc ratio for the species being assessed or a related species, if available | Decimal number | 0.082 | ratio_species_related |
|  | Scientific name of the closely related/highly similar species the Ne:Nc ratio is based on, if such is the case | Character text | Pelophylax lessonae | species_related |
|  | Year of sampling in which the Ne:Nc ratio was established | Date year | 2014 | ratio_year |
|  | List of all relevant sources used in determining the conversion ratio or further information if needed.Separated by a semicolon (;). | Character text | Cayuela et al. 2021 Demography, genetics, and decline of a spatially structured population of lekking bird. Oecologia 195:117-129 | source_popsize_ratios |
| **Optional taxon information (useful for analyses)** |  |  |  |  |
|  | Realm or realms which the species inhabits | Categorical | Freshwater terrestrial | realm |
|  | Habitat of the species according to the IUCN Habitat Classification Scheme. https://www.iucnredlist.org/resources/habitat-classification-scheme. Select all that apply. | Categorical | shrubland wetland | IUCN_habitat |
|  | Whether the species is a national endemic | Categorical | Yes | national_endemic |
|  | Whether the species range is wide-ranging  or restricted, based on criteria outlined in [Glossary](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/7_Glossary/Glossary.html#species-range).  | Categorical | wide_ranging | species_range |
|  | Global Red List Category (IUCN) | Categorical | LC | global_IUCN |
|  | National or regional Red List Category (any red listing different to the Global) | Categorical | NT | regional_redlist |

\* Needed to perform summary analyses or aggregate results by desired categories.

^ The GBIF taxon id is useful because it links the taxonomic identification of the species to other information, and to track taxonomic changes. The common names of the species are useful for communication and community participation. 

{: .note }
Other useful metadata include the realm (terrestrial, aquatic, marine), and ecosystem (e.g. rainforest), as well as threat status. These are not required, but they are useful to disaggregate the indicators.

[Previous: KoboToolBox help](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/5_Data_collection/Kobo_toolbox_help.html#kobotoolbox-help){: .btn .btn-blue .mr-4 }
[Next: Calculations and reporting](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/6_Calculations_and_reporting/Calculations_and_reporting.html#calculations-and-reporting){: .btn .btn-green }
