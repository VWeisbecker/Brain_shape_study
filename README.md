# Marsupial Brain Shape Evolution 
Code authors: Emma Sherratt, Vera Weisbecker

This code runs all analyses for the manuscript "Global elongation and high shape flexibility as an evolutionary hypothesis of accommodating mammalian brains into skulls" by Weisbecker et al. (accepted at Evolution; an open-access pre-print is available on [Biorxiv](https://www.biorxiv.org/content/10.1101/2020.12.06.410928v1)).


*All scripts are in RMarkdown format (.Rmd) and can be opened in RStudio. There, you can edit and run code chunks as normal or use the Knit button to create HTML versions with both code and output. After cloning this repo, remember to either set your working directory to the Weisbecker_et_al_Brain_shape folder on your computer or open an RStudio project from that folder.*

*The code is commented out and explains where the various data and auxiliary files are needed. The following is just a brief overview.

## Data
**Raw data:**
* The [Raw Data](/Data/Raw/) folder in this repository contains shape coordinates, a specimen data file for information associated with each specimen, as well as auxiliary files for semi-landmark sliding for automatic and manual landmark placements as required by the code
* [Ply files for automatic landmark placement](http://10.6084/m9.figshare.12253409) is a figshare repository that needs to be pasted in to [Data/Raw](/Data/Raw) for automatic landmark placement to work *NB this doi link will start working upon acceptance of the manuscript*
* [Endocasts and endocast dissections](http://10.6084/m9.figshare.12284456) is a figshare repository containing endocast stl files (on which the fixed/curve and manual surface landmarks were placed) and dissected brain partition volumes. *NB this doi link will start working upon publication of the paper*


**Phylogenetic data:**
* [Phylogeny used](/Data/Raw/Phylogenies) contains the files for the three alternative trees used in the paper. 


## Analyses (Analysis folder)

* [01_1_Marsbrain_Place_Patches_Automatically.Rmd](Analyses/01_1_Marsbrain_Place_Patches_Automatically.Rmd) This script uses Morpho to place the surface semilandmarks on the endocasts, based on manually placed fixed and curve semilandmarks. Outputs an .rda file into the [Data/Processed](/Data/Processed) folder that can be fed into [01_2_Marsbrain_Read_in_Data_Compare_Patches.Rmd](/Analyses/01_2_Marsbrain_Read_in_Data_Compare_Patches.Rmd).

* [01_2_Marsbrain_Read_in_compute_neocortex_volumes.Rmd](/Analyses/01_2_Marsbrain_Read_in_compute_neocortex_volumes.Rmd) This file replicates the generation of log-shape ratios for histological cortex volumes from two publications.

* [01_3_Marsbrain_Read_in_Data_Compare_Patches.Rmd](/Analyses/01_2_Marsbrain_Read_in_Data_Compare_Patches.Rmd) This script compares automatic and manual surface landmark placement and prepares the landmark data for analysis. Outputs .rda file into the [Data/Processed](/Data/Processed) folder that can be used for [02_1_Marsbrain_Analyses](/Analyses/02_1_Marsbrain_Analyses.Rmd) and [02_2_marsbrain_Remove_round_outliers.Rmd](/Analyses/02_2_marsbrain_Remove_round_outliers.Rmd). 

* [02_1_Marsbrain_Analyses.Rmd](/Analyses/02_1_Marsbrain_Analyses.Rmd) Runs all analyses reported in the manuscript, outputs .rda file into the [Data/Processed](/Data/Processed) folder for use in [03_Marsbrain_Figures.Rmd](/Analyses/03_Marsbrain_Figures.Rmd). Note that, after running code once, this file can take a long time to open in Rstudio! This seems to be a cache problem that I have been unable to fix.

* [02_2_marsbrain_Remove_round_outliers.Rmd](/Analyses/02_2_marsbrain_Remove_round_outliers.Rmd) This script re-runs and compares several analyses to ensure that two species with extremely rounded brains do not overly impact on the ordinated shape variation.

* [03_Marsbrain_Figures.Rmd](/Analyses/03_Marsbrain_Figures.Rmd) Creates all plots for the manuscript.

## Figures (Figure folder)

The code in [03_Marsbrain_Figures.Rmd](/Analyses/03_Marsbrain_Figures.Rmd) outputs the plots and table into this folder. Note that this code may require a folder substructure to be built by the user as the figures are created.
