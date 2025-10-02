---
layout: default
title: How to define populations
parent: How to - guides 
nav_order: 1
---

# How to define populations 

A population is a group of individual organisms that can mate with each other  and have low or no connectivity with other populations (see What is a population? section ) . This definition aligns with the IUCN Red List Guidelines definition of a “subpopulation” - geographically or otherwise distinct groups between which there is little demographic or genetic exchange (typically less than one successful migrant individual or gamete per year; [IUCN 2001](https://portals.iucn.org/library/sites/library/files/documents/RL-2001-001.pdf)). 

Genetic differences mostly arise as a product of spatial and temporal isolation over time due to random processes (genetic drift) and as an effect of population size. Populations separated by more time can have more differences. Designation of populations should also consider human induced gene flow (e.g. reintroductions, translocations). 

Many species’ populations are fairly easy to designate: a population may consist of a cluster of individuals in a discrete location like an island, lake, river catchment or forest preserve, separated from other discrete locations.  

Based on the knowledge of biodiversity and taxonomic experts, definitions of populations will be available in some biodiversity databases, published reports, or expert consultations.  Designating populations may be performed by taxonomic experts, local knowledge holders, or these groups working together.  In other cases, the reports or databases may not clearly designate population boundaries and will require interpretation.  Visual examination of maps may result in ‘merging’ occurrences that are likely to experience extensive gene flow (i.e. within the dispersal distance of the species, lack of clear barriers such as mountains, fences, or rivers).

**There are different methods for determining if a population is distinct. Short definitions are provided here, followed by more details below.**

{: .important } 
Methods to define population can be combined. For instance, populations can be defined using geographic boundaries and traits, or genetic differences and ecological or biogeographic proxies.

* **[Geographic boundaries](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#geographic-boundaries)**: when groups of individuals are separated by some uninhabited area which cannot easily be traversed (e.g. river, mountain, different habitat type, or other habitat types which can´t be crossed by the species). This includes human made barriers that likely disrupt movement of organisms for several of their generations (e.g. urbanization, dams).

* **[Dispersal buffer](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#dispersal-buffer)**: when dispersal distances are available for a given species one can create buffer polygons around observation points (occurrence points). Polygons that overlap are fused together, and the resulting polygon, along with the points falling within its area, are considered a single population.

* **[Ecological or biogeographic proxies](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#ecological-or-biogeographic-proxies)**: differences in ecological conditions represent a proxy for potential local adaptations across a species’ range. This may be especially useful for designating populations when groups of individuals occur in continuous fashion across multiple ecological zones, as there may be different local adaptations even in what seems to be a continuous distribution. In management this may be referred to as ecoregions, seed zones, proxies of genetic differentiation or similar terminology.

* **[Traits](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#traits)** (e.g., behavioral, morphological, physiological): when groups of individuals have different traits that may represent adaptations or may prevent interbreeding (such as type of song in birds or whales, adaptation to drier environments etc). 

* **[Genetic differences/clades/groups](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#genetic-differencesclades)**: when a genetic (DNA-based) study has been performed which shows either (a) no gene flow between groups of individuals, and/or (b) a long period of time in which groups are separated (implying genetic divergence). In this case populations are normally delineated by identified genetic differences, e.g., mtDNA differences, population genetic clustering (STRUCTURE and similar), strong population division (FST), unique alleles, and other methods.

* **[Evolutionary significant units (ESUs)](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#evolutionary-significant-units-esus)**: an ESU is a genetic unit present within a species. More specificallys it is a “lineage demonstrating highly restricted gene flow from other such lineages within the higher organizational level (lineage) of the species" ([Fraser and Bernatchez, 2002](https://onlinelibrary.wiley.com/doi/full/10.1046/j.0962-1083.2001.01411.x)). It can consist of a single population or a group of them.

* **[Management Units](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#management-units)** (demography/migration): when biologists at a management agency have identified boundaries in an otherwise continuous species range, while recognizing that management (and adaptation) require some kind of delineation. Note that these defined units are often demographically distinct, but may sometimes just represent political or other boundaries.



## Methods to define populations

### Geographic boundaries

This is the most easily observed definition of a population, when a species’ range map or satellite photos are available. It may be possible to distinguish groups of individuals separated by some uninhabited area which cannot easily be traversed (river, mountain, different habitat type, or simply a span of unoccupied habitat). This includes human-made barriers that likely disrupt movement of organisms for several of their generations (e.g. urbanization, dams).

This method focuses mostly on discrete populations separated by barriers that cannot be crossed e.g. a deep canyon or river. For example, the Mexican montane juniper (*Juniperus monticola*) grows in isolated mountaintops above 3,000 meters above sea level. Each mountaintop can be considered a single population. 

![](Define_pop_Fig1.png) 
###### **Example of using geographic boundaries to define populations.** In the Mexican mountain juniper, populations can be defined as a mountain or group of mountains isolated by lowlands below 3,000 meters above sea level. Occurrence data can come from herbaria (purple dots) and citizen science efforts (orange dots). Before assigning an occurrence point to a mountain, it is important to check the taxonomic and georeference data of each occurrence. For instance, the point marked with a white “!” lacks accurate geographic information, and thus could belong to any of the nearby mountains, instead of the location where it appears. 
{: .no_toc }


### Dispersal buffer

Populations can be defined using dispersal buffers, where the distance between groups of organisms obtained from occurrence data can be used to determine if they are likely to be genetically connected. When the edge of a group is within a reasonable dispersal distance (for instance, a distance within which 95--99% of realized dispersal occurs) of another group’s edge, and there are no known physical barriers impeding dispersal, the groups can be considered connected and part of the same population (sometimes called a [metapopulation](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#metapopulations)). This approach assumes that the boundaries of each population are accurately defined, and that individuals within each population have the potential to interact and mate with one another.

{: .note }
When seeds, pollen or spores can disperse the organism's genes, the longest dispersal distance of these (often but not always pollen) should be used. 

![](Define_pop_Fig2.png)
###### **Example of using dispersal buffers to define populations.** For the *Hyla arborea* populations in Belgium, occurrence points were derived from [citizen science data](waarnemingen.be), and polygons were generated based on the reported dispersal range (4 km). These polygons were evaluated by experts, and those where physical barriers affected individual dispersal, as well as polygons derived from a single observation within the period analyzed, were excluded from further analysis.
{: .no_toc }


### Ecological or biogeographic proxies

Ecoregions or other biogeographic proxies for ecological or seed zones can be used to delineate populations, especially in widespread or continuously distributed species. Differences in ecological conditions represent a proxy for potential local adaptations across a species’ range. This reflects the fact that genetic exchange is limited across the range; in such cases, the use of ecological maps may be the only way to designate populations. In practice, the species’ range map can be overlaid on a map of ecoregions, with modifications as needed to reflect the underlying biology or management of the species.

![](Define_pop_Fig3.png)
###### **Example of using ecological or biogeographic proxies to define populations.** Whitebark pine (*Pinus albicaulis*) has an extensive range across western North America (bright green polygons) that spans multiple ecoregions (other colored and labeled polygons), which are defined by similarities in ecosystems, topography, geology, soils, and climate. For the whitebark pine indicators assessment, ecoregion polygons were slightly modified to reflect whitebark pine biology (defined by experts) and political delineations (U.S. vs. Canadian jurisdiction).
{: .no_toc }


### Traits 

Traits are observed physical differences (e.g. size, color patterns), or other differences between populations, such as timing of migration, or different mating calls, that have been recognized by experts on the taxon. Groups of individuals may be continuous in space, but some groups of individuals have different traits that may represent adaptations or may prevent interbreeding.  

### Genetic differences/clades

A genetic (DNA-based) study may be used to demonstrate either (a) no gene flow between groups of individuals, and/or (b) shows a long period of time in which groups are separated (implying genetic divergence). This conclusion should be based on a genetic study that covers the relevant area in question, with sufficient sampling (e.g. all relevant populations are sampled) and with appropriate genetic markers. Examples of significant genetic differences include large FST values (not just ‘significant’ FST, since very small differences can still be statistically significant) or diverged mitochondrial DNA. We note that not all genetic clusters are distinct populations (because again, even small differences can now be detected due to genomic sequencing); when clarification is needed on this topic, a population geneticist should be consulted. We argue that one should consider the  threshold of roughly less than 1 migrant per generation (on average) as sufficient for defining a population.  Older [genetic markers](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/7_Glossary/Glossary.html#genetic-markers), such as chloroplast and mitochondrial DNA sequences, are useful in identifying genetically distinct populations (though an absence of differences using these markers is not evidence of lack of population barriers).

![](Define_pop_Fig4.png)
###### **Example of using genetic differences/clades to define populations.** Populations of Brown bear (*Ursus arctos*) in Sweden were defined based on genetic clusters recovered in several studies. Both microsatellite and single nucleotide polymorphism (SNP) data indicate three genetic clusters that correspond to previously identified areas of brown bear concentration. In the late 1800s the species was pushed back into four separate areas and declined to approximately 100 individuals due to intense hunting. Since being protected in 1927 they have expanded from these areas. 
{: .no_toc }


### Evolutionary significant units (ESUs)

An ESU is a genetic unit present within a species, defined as a “lineage demonstrating highly restricted gene flow from other such lineages within the higher organizational level (lineage) of the species" ([Fraser and Bernatchez, 2002](https://onlinelibrary.wiley.com/doi/full/10.1046/j.0962-1083.2001.01411.x)). It can consist of a single population or group of them; therefore, in some instances, the number of ESUs and the number of populations can be the same. ESUs normally are established using several sources of evidence, including genetic and ecological distinctiveness ([Funk et al. 2012](https://pmc.ncbi.nlm.nih.gov/articles/PMC4185076/)). ESUs are sometimes reported in scientific papers or management reports, and can be used to define populations. However, keep in mind that ESUs tend to represent a higher level of clustering, and for the purpose of genetic monitoring, some of them could be split.

![](Define_pop_Fig5.png)
###### **Example of using ESUs to define populations.** *Juniperus blancoi* populations were defined based on ESUs previously described from several lines of evidence. Genetic studies ([Mastretta-Yanes et al. 2012](https://link.springer.com/article/10.1007/s10592-011-0277-y); [Moreno-Letelier et al. 2014](https://nph.onlinelibrary.wiley.com/doi/full/10.1111/nph.12761)) found strong population structure based on short DNA sequences. There are also three taxonomic varieties (*blancoi, mucronata* and *huehuentensis*) that do not match the former structure. Mastretta-Yanes et al. (2012) delimited five conservation units (equivalent to ESUs) based on historical, genetic and ecological exchangeability. To define populations for the indicators, the conservation units of Mastretta-Yanes et al. (2012) were used, but isolated (> 150 km apart) geographic localities within them were subdivided, due to genetic evidence of low gene flow. The newly discovered population of Cerro Gordo (Durango) for which there is no genetic data was also considered as distinct from the rest of the species, due to its geographic isolation. The newly discovered population Coscomate for which there is also no genetic data was grouped with El Salto due to its geographic proximity and similar habitat.
{: .no_toc }

 
### Management Units 

This category should be avoided if possible, as it may align sometimes more with agency needs or political boundaries, but may be useful and necessary if other methods cannot be applied, and sometimes it does align with demographic distinction (e.g. no migration, [Palsboll et al., 2007](https://doi.org/10.1016/j.tree.2006.09.003)). For managed species, biologists at a management agency may have identified boundaries based on an intuition of adaptation or lack of mating among groups. These units could simply recognize that management takes place at certain spatial scales and some practical boundaries are needed for logistics--for instance, within different protected areas (e.g. National Parks) or wildlife enclosures. But notice that if units are surrounded by human-made barriers, like lands converted to agriculture, other methods to define population may also be used.

![](Define_pop_Fig6.png)
###### **Example of using Management Units to define populations.** The Harbour porpoise (*Phocoena phocoena*) is a highly mobile marine mammal. However, genetic and morphological studies indicate that the individuals in the Baltic Sea are differentiated from individuals in the Belt Sea and North sea. Harbour porpoise is monitored and managed through international cooperation based on identified stocks and different areas of assessment. In Sweden, there is a national action plan for Harbour porpoise that identifies three management units within Swedish waters.  
{: .no_toc }


## Metapopulations

A [metapopulation](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/7_Glossary/Glossary.html#metapopulations) consists of numerous small localities (ponds, prairies, etc.) that are separated but not very far apart (hundreds of meters to several kilometers, depending on the species dispersal capacity), and are thus capable of exchanging, on average, at least 1 migrant (one reproductive adult moving between patches) per generation per year. In such cases,

* the population size should be considered **the sum of the individual localities** (subpopulations), which may cover tens or hundreds of kilometers, and should be assessed using the Ne 500 indicator
* it is likely **inappropriate for subpopulations to be individually assessed at the Ne 500 level**

Determining whether or not a data source is describing a species at the **metapopulation level** (i.e. appropriate for the Ne 500 indicator) may require difficult interpretations about migration possibilities between occupied patches of landscape. See the ["How to account for uncertainty" section](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/uncertainty.html#how-to-account-for-uncertainty-in-the-number-of-populations-population-size-or-nenc-ratio) for more details.

### When locations change over time
Metapopulations should represent stable spatial and temporal units. Many species have ephemeral subpopulations in dynamic source-sink metapopulations--a sink being a spatial location receiving high immigration from adjacent areas, which would not persist on its own without immigration. Sinks are not distinct populations; the conglomerate of connected subpopulations should be evaluated as a population.

## *Ex situ* Collections
[*Ex situ* collections](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/7_Glossary/Glossary.html#metapopulations) are collections of living organisms (or their seeds or tissue) that are maintained outside the natural habitats of those organisms for the purpose of ensuring their survival and future propagation. Because the genetic diversity indicators are meant to provide an assessment of the genetic status of wild populations, ***ex situ*** **collections (and the individuals within them) should generally not be included in indicator calculations**. 

In some instances, it may be challenging to distinguish between an *ex situ* collection and an introduced or reintroduced population: for instance, when large numbers of individuals are maintained (e.g. in large fenced areas, gardens, or managed wild areas) to provide redundancy or to produce offspring for periodically stocking existing populations. In these cases, assessors are asked to use their best judgement in determining whether or not a given collection of individuals should be considered a population (or as actively contributing to a wild population) to include in indicator calculations. 

For instance, if there is evidence of gene flow from such collections into wild populations, or if there is an intent to eventually manage the collection as a wild population, then it may be appropriate to include such groups in indicator calculations (for example, by summing the Nc of the ex situ collection with the Nc of the in situ population for determining the Nc of the population as a whole, before converting to Ne for the Ne 500 indicator).

## Considerations when defining populations for some taxonomic groups

For **freshwater species**, the riverscape structure can help define populations or units that can be conglomerated into populations/metapopulations using GIS and existing databases (which may include Nc data; for instance, see such some useful databases like [RivFishTIME](https://par.nsf.gov/servlets/purl/10298619) and [SERS](https://www.slu.se/en/departments/aquatic-resources1/databases/database-for-testfishing-in-streams/) for fish). Individuals inhabiting separate lakes can be considered separate populations, especially for lakes that are disconnected from the hydrographical network. Riverscape (meta)populations can also be defined through their level of connection/disconnection; for instance, it may be a good idea to consider distinct river basins or hydrographical systems as distinct populations. Similarly, groups of individuals located in river stretches separated by huge dams or by abiotic or hydromorphological characteristics limiting species’ dispersal (e.g. changes in river slope, river substrates, water velocity, etc.) could be considered separate populations.

For **trees**, aspects such as pollination mode and commonness is important.  Trees which are wind pollinated can have continuous populations extending greater than tens of kilometers.  Trees which are insect pollinated generally have less gene flow (though not always--for instance, when see dispersal is far ranging).  For uncommon species, distinct geographic clusters separated by several to tens of kilometers may be considered distinct populations.  For common trees, a distinct population may not be easily apparent (e.g. trees that extend across much of a continent in a continuous fashion).  In such cases, a “population” may be considered at approximately the level of a state, country, or ecoregion (hundreds of kilometers across), meaning the [ecological approach](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Howto_define_populations.html#ecological-or-biogeographic-proxies) noted above may be useful.

For **amphibians**, dispersal capability may vary greatly between species. Some toads, for example, are known to be long distance dispersers: provided they have access to resources (such as water bodies to breed), a single metapopulation may span hundreds of kilometers. Salamanders, on the other hand, tend to have lower dispersal capabilities, with dispersal often less than 1.5 km. As such, wetlands within 1 km from each other are likely to constitute a metapopulation. Because amphibians must live in or around freshwater, their dispersal can be constrained when water sources are distant from each other or separated by barriers (e.g. mountain ranges, valleys, or highways). 

For **small mammals**, habitat specialization and structure are determining factors. Specialized species tend to be strongly affected by habitat fragmentation, whereas generalist species can more easily disperse between suitable habitat patches in an otherwise unsuitable landscape can lead to large contiguous populations, despite restrictions on individual movements that may be limited to at most tens of kilometers. Some species also display strong sex-biased dispersal.

For **large mammals**, many species show habitat specialization (despite greater dispersal ability).  Therefore, populations can be connected to different degrees depending on barriers to dispersal. Some habitats are naturally or anthropogenically fragmented (e.g. dense forest separated by agriculture). Fences can also disrupt natural movement patterns. Some species solely exist in fenced areas; where good records exist, all remnants can together be considered a single population.

Defining populations for **marine species** can be challenging due to environmental barriers found in open or pelagic ocean environments, and due to migration to and from breeding areas. Barriers are often related to temperature, current or depth. Marine species range from very small to large and their dispersal likewise ranges from local to planktonic dispersal (i.e. movement for many days on currents traversing the length of a hemisphere). It is important to understand breeding/spawning areas, dispersal patterns/capabilities, and environmental covariates to help determine genetically related populations. These distinctions may not be easily defined and some populations may have more or less continuous distributions.  In such cases, a “population” may be considered at approximately the level of a state, country, or biogeographic region (hundreds of kilometers across).


[Previous: Species list](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/4_Species_list/Species_list.html#species-list){: .btn .btn-blue .mr-4 }
[Next: How to establish a reference period](https://ccgenetics.github.io/guidelines-genetic-diversity-indicators/docs/3_Howto_guides_examples/Reference_period.html#how-to-establish-a-reference-period){: .btn .btn-green }
