# Combined DNHS+GTP Leukocyte Composition Analyses  

This repository contains R notebooks used for analyses, figures, and tables in paper titled **Methylomic profiles reveal sex-specific differences in leukocyte composition associated with post-traumatic stress disorder (PTSD)**, published in *Brain, Behavior, and Immunity* (available online June 19, 2019, [doi: 10.1016/j.bbi.2019.06.025](https://doi.org/10.1016/j.bbi.2019.06.025)).  Data QA and processing were done in separate repo, as mentioned below.  

***
### Input Data:  

Access to R notebooks used for QA and data processing (subdirectories in git repo: **gsk-0-Data-Processing**) are available upon request.  
**Platform** (for both datasets): Illumina HumanMethylation 450K BeadChip microarray  
There are 3 parts to the QA/data processing pipelines:  
1. Detroit Neighborhood Health Study: (/DNHS/DNAm_450K/)  
2. Grady Trauma Project: (/GTP/DNAm_450K/)  
3. Combined DNHS + GTP processing: (/Combined/DNAm_450K/)  

More detailed description available in README file of each subdirectory.  
Final output files derived from last step of combined pipeline (**Combined_450K_BatchAdjsepwComBat_Estimates_2.Rmd**) are: 
- **Combined_450K_BatchAdjsepwComBat_Estimates.Rdata**
- **Combined_450K_AdjsepwComBat_DatMats.Rdata**

***
## Table of R notebooks:  

### Data Preparation
- **Combined_PhenoPrep_Transform_0.Rmd**: Additional preparation of phenotype data.  Generates data file used as input for other notebooks in this folder (output: **CombPheno2wcue2_incTuk.Rdata**).  
    + *Note*: Only *CombPheno2wcue2* data object used.  Tukey-transformed data object not used in final analyses.  

### Analyses  
- **Combined_LeukoComp_450K_nonParametric_Init1.Rmd**: Initial/baseline non-parametric analyses of RPC and CP estimates with check tests, for: race/ancestry PCs (*not in submitted draft of paper*), lifetime PTSD, and Sex.  
- **Combined_LeukoComp_450K_nonParametric_SexStrat.Rmd**: Sex-stratified non-parametric analyses for lifetime PTSD across all leukocyte subtypes.  **NOTE:** Analyses for PTSD status deprecated, since coding of PTSD status was updated after author comments.  However, error was made and Figure 6, sex-stratified density plot of monocyte proportions by PTSD status, is based on this old coding... Results from this iteration of post-hoc Dunn test come to same conclusion, but is also significant for CP as well, though to a lesser degree.  In the paper, it was only nominally significant.  
- **Combined_LeukoComp_450K_nonParametric_Desc.Rmd**: Simple notebook containing sex-stratified IQR and median for each leukocyte subtype.  Re-run b/c wasn't saved earlier.  (Matches descriptive statistics in paper.)
- **Combined_LeukoComp_450K_nonParametric_SexStrat_PTSDStatus_MO.Rmd**: Sex-stratified non-parametric analyses for PTSD status in monocytes.  **NOTE:** As noted above, the statistics here does not match the coding of PTSD status used for Figure 6 in the paper.  The density plot that matches the statistics in the paper is only marginally different and available in output directory **20190121_FigRevisions_c274c97**, generated in **FigureRevisions_v2.Rmd**.  
- **Combined_LeukoCompLM_450K_sqrt_Mono100.Rmd**: 2-way ANCOVA and post-hoc emmeans tests with **followUpCombined_LeukoCompLM_450K_sqrt_Mono100.Rmd** used just to reformat tables for publication html output in R notebook.  This was copy/pasted to word docx for final formatting.  

#### Supplementary Analyses added after revisions: 
Section III. Comparison of leukocyte subtype proportions between participating cohorts: **Combined_LeukoComp_450K_nonParametric_Study_483.Rmd**.  
Section IV. Assessment of age effects: **FigureAddedPlots_rev1.Rmd**.  

*Note:* Due to minor changes in figures and tables between revisions (mostly aesthetic and figure numbers), multiple R notebooks were used to generate different iterations of figures.  The notebook used to generate final figures and tables in publication are identified below along with associated output directory.  Raw output files generated in R were arranged using Adobe InDesign.  Files were exported back to pdf and combined for submitted figure set.  Individual *.indd* and *.pdf* files available on request.  

### Tables  
- Table 1: **Combined_LeukoComp_450K_Tab1_DescriptiveStats_rev1.Rmd** (Key demographic characteristics, by Sex).  
    + Table was generated under subsection *Table 1 alt* and is revised v1.  The original submission for Table 1 was based on **Combined_LeukoComp_450K_Tab1_DescriptiveStats.Rmd** (Key demographic characteristics of the DNHS and GTP).  
- Tables 2 and 3: **followUpCombined_LeukoCompLM_450K_sqrt_Mono100.Rmd**  

### Figures  
- Figure 1, 2: **FigureRevisions_v2.Rmd** minor aesthetic revisions for (current) Figures 1, 2 and Supplementary Figure 1
    + Output sub-directory: **20190121_FigRevisions_c274c97**
- Figure 3: **FigsPlots.Rmd** for sex-stratified violin plot across leukocyte subtypes, by lifetime PTSD
    + Output sub-directory: **20181221_added_Figures_Plots_v3_40369cb**
- Figure 4: **Fig3_v2.Rmd** minor aesthetic revision for density plot of lifetime PTSD
    + Output sub-directory: **20190102_Fig3_revise_9ad48f8**
- Figure 5: **Combined_LeukoCompLM_450K_sqrt_Mono100.Rmd** outputs raw data files for interaction plots
    + Output sub-directory: **20181218_Combined_LeukoCompLM_450K_sqrt_Mono100_40369cb**
- Figure 6: **FigsPlots.Rmd** output raw data file for density of PTSD Status in monocytes.  
    + Output sub-directory: **20181221_added_Figures_Plots_v3_40369cb**
    + check notes above.  Figure corresponding to statistics is in **20190121_FigRevisions_c274c97**

### Supplementary Tables
- Supp Tables 1 and 2: **followUpCombined_LeukoCompLM_450K_sqrt_Mono100.Rmd**

### Supplementary Figures
- Supp Figure 1: **FigureRevisions_v2.Rmd** minor aesthetic revisions for (current) Figures 1, 2 and Supplementary Figure 1.  
    + Output sub-directory: **20190121_FigRevisions_c274c97**
- Supp Figure 2: **Fig3_v2.Rmd** minor aesthetic revision   for density plot of lifetime PTSD
    + Output sub-directory: **20190102_Fig3_revise_9ad48f8**
- Supp Figure 3: **Combined_LeukoCompLM_450K_sqrt_Mono100.Rmd**
    + Output sub-directory: **20181218_Combined_LeukoCompLM_450K_sqrt_Mono100_40369cb**
- Supp Figure 4: **FigsPlots.Rmd** output raw data file for density of PTSD Status in monocytes.  
    + Output sub-directory: **20181221_added_Figures_Plots_v3_40369cb**
    + check notes above.  Figure corresponding to statistics is in **20190121_FigRevisions_c274c97**
- Supp Figures 5-8: **FigureAddedPlots_rev1.Rmd**: Section IV. Assessment of age effects.  
    + Output sub-directory: **20190504_added_Figures_Plots_rev1_da93eb1**

***

**Title:** Methylomic profiles reveal sex-specific differences in leukocyte composition associated with post-traumatic stress disorder (PTSD)  

**Contact:** Grace Kim &nbsp;&nbsp;(<gkim53@illinois.edu>)  
**PI:** Monica Uddin &nbsp;&nbsp;(<monica43@health.usf.edu>) 

**Institutions:**  
- University of Illinois at Urbana-Champaign  
    + Carl R. Woese Institute for Genomic Biology; Neuroscience Program; Medical Scholars Program
- University of South Florida  
    + Genomics Program, College of Public Health

***