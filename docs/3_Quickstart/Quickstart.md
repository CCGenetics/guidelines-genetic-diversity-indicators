---
layout: default
title: Quickstart
nav_order: 3
has_children: false
---


# Quickstart guide to genetic indicators
{: .no_toc }

Here we summarize the ten steps to estimate the Ne 500 and PM genetic diversity indicators. Please refer to the [Species list](https://github.com/AliciaMstt/guidelines-genetic-diversity-indicators/blob/main/docs/4_Species_list/Species_list.md#species-list), [How to guides](https://github.com/AliciaMstt/guidelines-genetic-diversity-indicators/blob/main/docs/3_Howto_guides_examples/Howto_guides_examples.md#how-to-guides--examples), and [Calculations and reporting](https://github.com/AliciaMstt/guidelines-genetic-diversity-indicators/blob/main/docs/6_Calculations_and_reporting/Calculations_and_reporting.md#calculations-and-reporting) sections of these guidelines for more detailed advice. 

Notice that we have made available a Kobotoolbox form that you can use to gather data and metadata from steps 2-5, and a series of R scripts to perform the calculations from steps 5-8.


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Preliminary

### Step 1. Define a species list for which to estimate the indicators

At minimum, 100 species should be evaluated, though ideally many more will be used if capacity is available (e.g. up to 1000). The selection of species should be unbiased.  For example, selecting only charismatic species (butterflies, orchids, etc.), species of economic value or rare/ endangered species would result in an indicator that represents the genetic condition of species in that subset rather than all species. Thus the set of species should be as unbiased as possible; this can be achieved by random selection from a list of known, extant species. Analysis and reporting of the indicator may wish to disaggregate for particular subsets e.g. harvested species, pollinators, keystone species, but the overall indicator value should represent all species. See section [Species list](https://aliciamstt.github.io/guidelines-genetic-diversity-indicators/docs/4_Species_list/Species_list.html#species-list) for advice on how to create a species list.

## Gather data

### Step 2: Define population boundaries in geographic space

For each focal species it is first necessary to define ‘populations’. Many local and national biodiversity monitoring programs (e.g. at species or ecosystem level) have already defined populations, or it may be straightforward to define them based on geographic isolation, occupying distinct habitats or ecoregions, association with a geographic feature like a mountain range or lake, etc. The goal is to have a discrete count, e.g. 4 populations. However, the indicator can accommodate uncertainty, such that different numbers of populations may be assumed. Full guidance on defining populations for a wide variety of organisms are provided in the [How to define populations](https://aliciamstt.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#how-to-define-populations) section. See also. [What is a population?](https://aliciamstt.github.io/guidelines-genetic-diversity-indicators/docs/2_Theoretical_background/What-is-a-population.html#what-is-a-population-a-first-simple-answer) in the background section.

### Step 3. Count the number of extant and extinct populations

Once population boundaries have been defined, it is necessary to count how many populations currently exist (extant populations) and, if possible, count the number of populations that have been lost (extinct populations). This data will be used to estimate the PM indicator. See section [How to count extant and extinct populations?](https://aliciamstt.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Extinct_extant_populations.html#extinct-and-extant-populations) for details and notes on the reference period.

{: .note } 
Note: If it is not possible to calculate the number of extinct populations, **it is still possible to proceed** to the next step (the Ne 500 indicator). 

### Step 4. Compile data on census size (Nc) or effective population size (Ne)

After defining populations, it is necessary to collect data on census population sizes (Nc) or, if available, Ne estimated from genetic data. Many biodiversity monitoring programs for priority species will have Nc data available - in some cases in a centralized national database, while in other cases, it may be scattered among different national reports, assessments, and other knowledge. "Other knowledge" should be considered broadly and it includes citizen science, local knowledge, indigenous knowledge, and informal data held by small NGOs and similar groups. Ne estimated from genetic data is less frequent, but it is already available for hundreds of species globally. See [Data sources]() in the Data collection section.


### Step 5: For populations with Nc data, calculate Ne based on an Ne:Nc ratio (skip if you obtained Ne directly from a genetic study)

To convert Nc to Ne it is important to choose a ratio of effective-to-census size and then multiplying the population’s census size by this ratio to obtain the population’s effective size. As mentioned in the [Ne 500 indicator background](https://github.com/AliciaMstt/guidelines-genetic-diversity-indicators/blob/main/docs/2_Theoretical_background/Ne-500.md#ne-500-indicator) the default ratio, which is slightly conservative, is 1/10th or 0.1 (thus the minimum Nc would be 5000). Alternatively, a taxon-specific ratio can be obtained several ways. See How to estimate population sizes? in the How to guides. To incorporate uncertainty in calculations, the calculation can be repeated using multiple Ne/Nc ratios.  But it is acceptable and useful to use the well-recognized 0.1 ratio. See section [Calculations and reporting](https://github.com/AliciaMstt/guidelines-genetic-diversity-indicators/blob/main/docs/6_Calculations_and_reporting/Calculations_and_reporting.md#calculations-and-reporting) for details, equations and R scripts to help with the calculations.


## Use data to calculate indicators

### Step 6. Calculate the proportion of maintained populations (PM indicator)

For each species, divide the number of populations currently existing (“extant populations”) by the number of populations that previously existed (“extinct populations”). Values for this indicator range from 0 to 1, with 0 indicating no populations exist (the species is extinct within the country) and 1 indicating that no populations have been lost. See section [Calculations and reporting](https://github.com/AliciaMstt/guidelines-genetic-diversity-indicators/blob/main/docs/6_Calculations_and_reporting/Calculations_and_reporting.md#calculations-and-reporting) for details, equations and R scripts to help with the calculations.

### Step 7: Calculate the proportion of populations above the 500 Ne threshold (Ne 500 indicator)

For each species, divide the number of populations with Ne above 500 by the total number of populations. The indicator is then the proportion (from 0 to 1) of all populations that are above 500. See section [Calculations and reporting](https://github.com/AliciaMstt/guidelines-genetic-diversity-indicators/blob/main/docs/6_Calculations_and_reporting/Calculations_and_reporting.md#calculations-and-reporting) for details, equations and R scripts to help with the calculations.

### Step 8. Indicators summary and reports
 
To combine the indicator values across species in a given country or geographic location, a simple average of the proportion for all the relevant species should be performed. If taxonomic groups are not represented evenly, the indicator value is the mean of each taxonomic group’s means, which down-weights overly represented taxonomic groups, e.g. mammals. Additionally, each species can be weighted by the proportion of its geographic range in the country, from 0 to 1, to reflect national responsibility, with full weight for endemic species. Transboundary/ transnational populations can be weighted similarly (e.g. by the proportion of that population falling within the Parties borders). The indicator would range between 0 and 1 (with 1 being the desired state - all populations above an effective size of 500). In addition, subsets of the indicator can be calculated for different species types e.g. pollinators, threatened species, etc., by repeating indicator calculations for only species in that type. Equations for indicator calculation are given in [Hoban et al (2023b)](https://doi.org/10.1111/conl.12953) and section [Calculations and reporting](https://github.com/AliciaMstt/guidelines-genetic-diversity-indicators/blob/main/docs/6_Calculations_and_reporting/Calculations_and_reporting.md#calculations-and-reporting). See also R scripts to help with the summary and reports.

## Use data to measure change and for management decisions

### Step 9: Measure temporal change in the indicators  

Temporal change can be calculated using multiple time point values of the indicators. For the Ne 500 indicator, any population that goes extinct after the country’s baseline year (each country is directed by the CBD in the [monitoring framework](https://www.cbd.int/doc/decisions/cop-15/cop-15-dec-05-en.pdf) to choose a baseline, which defaults to 2010-2020 but which may be adjusted to country context) is assigned an Ne of 0 and are therefore below Ne 500. These populations must be retained in the calculation in order to avoid the perverse incentive to “raise” the indicator value through population extinction. See Measure temporal change for details and other considerations.

### Step 10. Management based on the indicators

The indicators are designed for use in practical biodiversity management – not just for reporting to the CBD.  For example, either indicator value at a single time point or over time can be used for: raising alarm in regions or taxonomic groups with low indicator values, prioritizing which species and populations are most in need of management to halt genetic erosion, designing management strategies and goals (e.g. reintroduction, population supplementation to increase Ne), tracking the consequences or effectiveness of management (e.g. if the indicator value improves), and communicating to the public about genetic diversity conservation. 
