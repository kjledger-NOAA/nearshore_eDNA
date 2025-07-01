# A case for multi-gear assessments: catchability of nearshore fish varies among habitat and species when sampling with eDNA and nets  

## Overview 

This repo contains metabarcoding analyses of mock community and environmental samples

### 1. mifish metabarcoding data generation 

amplicon sequences were generated across three MiSeq runs: 
* 2021 and 2022 field samples: july 1 2024
* mock communities 1 thru 10: august 20 2024
* mock communities 11 thru 13: october 16 2024

FAIR eDNA metadata: https://docs.google.com/spreadsheets/d/1YoPY652Eie5Y-KFF-er4L-sFThxsS1SDf6gcAWQVhos/edit?usp=sharing

### 2. pre-processing 

step 1: combined all raw sequencing reads (mock communities and eDNA samples) into a single folder and created sample sheet. uploaded folder to HPCC.

step 2: processed samples using dadasnake (config.nearshore.mifish.yaml) and saved output in 'dadasnake/nearshore_w_mock_mifish_updated_20241106'

step 3: ran blastn against the ncbi nt db on sedna and stored output in 'blast/nearshore_mifish_20241106'

### 3. R code 

* *1_taxonomic_assignment_blastn.Rmd* - This code takes the blastn output and determines the taxonomic assignment of each ASV    
* *2_decontamination.Rmd* - This code accounts for tag-jumping, removes ASVs without taxonomic assignment, removes ASVs that don't show up in non-controls, and discards low read depth replicates based on ASV accumulation curve (for eDNA samples only)   
* *3_mockcommunities.Rmd* - This code formats expected mock community species compositions with the observed species proportions and makes some exploratory plots of mock community samples   
* *4_qm_mock_testing_efficiencies.Rmd* - This code runs the quantitative metabarcoding model from Shelton et al. 2023 to calculate each mock communities' species specific amplification efficiencies 
* *5_ind_alpha.Rmd* - This code pulls out alpha from each qm mock community model and plots   
* *6_qm_fieldsamples.Rmd* - This code runs the quantitative metabarcoding model from Shelton et al. 2023 using all mock communities as known inputs to adjust read proportions of environmental samples   
* *7_qm_field_plots.Rmd* - This code plots amplification efficiency estimates when all mock communities are known inputs. Also makes some exploratory plots looking at read proportions   
* *8_fieldsample_summary.Rmd* - This code converts decontaminated ASV table to taxon table for field samples and calculates simple mean proportions across technical replicates    
