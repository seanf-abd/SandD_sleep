# README:How Variable is Sleep Timing Variability? A Longitudinal Analysis in a Sample of Children and Adolescents
>This document has been structured to mirror templates published in Zieliński, T., Hodge, J. J. L., & Millar, A. J. (2023). Keep It Simple: Using README Files to Advance Standardization in Chronobiology. Clocks & Sleep, 5(3), 499-506. https://doi.org/10.3390/clockssleep5030033

## General Information on Dataset utilised
  ### Summary/Abstract
  >The goal of this is to provide clear resources to access data used in this manuscript, should a researcher want to obtain access. Similarly, this document provides a        brief overview of analysis scripts, as well as instructions for utilising them appropriately. 

 ### Title of Dataset         
  The Alcohol, Sleep, and Circadian Rhythms in Young Humans Study [Sleep and Development (SandD) study] 

  ### Author(s)/Contributor(s)
    For information pertaining to the dataset, follow this link https://pubmed.ncbi.nlm.nih.gov/25380248/
    Alternatively, you can contact the National Sleep Research Resource (NSRR) at https://sleepdata.org/pages/about

  ### Date of Creation
    2025-01-01
    
  ### Digitial Object Identifier (DOI)
    https://doi.org/10.25822/g6s2-7v68
    
## Dataset Overview
### Description
This is a secondary data source, freely-obtained from [https://sleepdata.org/datasets/sandd]. Researchers must create an NSRR account and submit a data request in order to gain access to the repository. All analysis code is avaialable from SandD_Github.Rmd

## Usage and Access 
  ### Licence
The SandD dataset is only available for non-commercial use. Permission is hereby granted, free of charge, to any person obtaining a copy of this analysis code   and associated documentation files (the "analysis code"), to deal in the the analysis without restriction, including without limitation the rights to use,               copy,modify,merge, publish, distribute, sublicense, and/or sell copies of the analysis code, and to permit persons to whom the analysis code is furnished to do so, subject to the following conditions. All I ask is that if you use some of the analysis code for your own research, please cite the original paper. 

## Analysis Code
### Summary/Abstract
>More information on the dataset is available at [https://sleepdata.org/datasets/sandd]
>The aim of this section is to provide an overview of the analysis code utilised in the manuscript, avaialable as SandD_Github.Rmd. 

  ### Purpose (Research hypothesis)
  This study sought to investigate the intra-individual consistency of actigraphy-derived measures of sleep timing variability, estimates of circadian phase (DLMO) and        subjective assessements in a cohort of adolescents and young adults across four study study sessions. 
  Further, we derive a novel measure (Phase Angle SD) to encapsualte weekly variation in phase angle, this was compared to Composite Phase Deviation (an established marker    of misalignment between behaviourally driven sleep-wake cycles and circadian phase)
  Lastly, we sought to examine inter and intra-individual determinants of greater Phase Angle SD (to assess what factors contributed to change in an indice assessing          variability, a kind of 'meta-variable' approach)

## Data Pre-Processing
  ### 1. Data loading and eligibility
   >This code screens valid group of participants for study inclusion. Following this, actigraphy data is cleaned and compiled into a dataframe for downstream analysis. 
  ### 2. Metric derivation
   >This chunk converts clock times to minutes/hours. After this cohorts are assigned. All STV measures are computed, no SRI/CPD was included due to lack of epoch data.

 ## Data Analysis
  ### 3. Descriptive information
   >Returns demographic information for each cohort in the analysis sample.
  ### 4. Mixed-effects model
   >Returns output from model using standardised predictors and outcomes, 
   >Model as here: standardised phase-angle SD ~ age (between) + sex + RCMAS (within/between) + Smith (within/between)
   >Random intercept and wave slope per participant included. 
   >Model diagnostics: singularity, ranova, residual QQ plot, VIF, marginal/conditional R², collinearity, profile CIs.
  ### 5. Intra-individual stability
   >Intra-Class Correlation (ICC) score for each outcome of interest. 
   >Run separately for SD-based and Absolute metrics 
  ### 6. Figure generation
   >Returns figures from manuscript. 
  ### 7. Group comparison 
   >Mann-Whitney U test to assess if there are significant differences in sex/age between cohorts with 3/4 valid testing sessions (there are not and so I opted to use 4.) 
   
## Citing the Dataset
>This is where I'd put my citation, if I had a citation that is.
>If there are any issues/bugs, please feel free to create an issue or send me an email!

## Acknowledgements   
>Special thanks to the administrators of the National Sleep Research Resource for the amazing work they do. 
>The Alcohol, Sleep and Circadian Rhythms in Young Humans Study (SandD) study was supported by the National Institute on Alcohol Abuse and Alcoholism grant AA13252. Data sharing was facilitated by the COBRE Center for Sleep and Circadian Rhythms in Child and Adolescent Mental Health (P20GM139743). The National Sleep Research Resource was supported by the U.S. National Institutes of Health, National Heart Lung and Blood Institute (R24 HL114473, 75N92019R002).

