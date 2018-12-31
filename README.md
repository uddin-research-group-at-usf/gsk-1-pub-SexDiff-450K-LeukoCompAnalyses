# Combined DNHS+GTP Leukocyte Composition Analyses  

This repository contains R notebooks used for analyses, figures, and tables in paper titled **Methylomic profiles reveal sex-specific shifts in leukocyte composition associated with post-traumatic stress disorder (PTSD)**.  Data QA and processing were done in separate repo, as mentioned below.  

***
### Input Data:  

Access to R notebooks used for QA and data processing (subdirectories in git repo: **gsk-0-Data-Processing**) are available upon request.  
**Platform** (for both datasets): Illumina HumanMethylation 450K BeadChip microarray  
There are 3 parts to the QA/data processing pipelines:  
1. Detroit Neighborhood Health Study: (/DNHS/DNAm_450K/)  
2. Grady Trauma Project: (/GTP/DNAm_450K/)  
3. Combined DNHS + GTP processing: (/DNHS/DNAm_450K/)  

More detailed description available in README file of each subdirectory.  
Final output files derived from last step of pipeline (**Combined_450K_BatchAdjsepwComBat_Estimates_2.Rmd**) are: 
- **Combined_450K_BatchAdjsepwComBat_Estimates.Rdata**
- **Combined_450K_AdjsepwComBat_DatMats.Rdata**

***
## Table of R notebooks:  
### Data Preparation
- **Combined_PhenoPrep_Transform_0.Rmd**: Additional preparation of phenotype data.  Generates data file used as input for other notebooks in this folder (output: **CombPheno2wcue2_incTuk.Rdata**).  
    + *Note*: Only *CombPheno2wcue2* data object used.  Tukey-transformed data object not used in final analyses.  

### Analyses
- **Combined_LeukoComp_450K_nonParametric_Init1.Rmd**: Initial/baseline non-parametric analyses of RPC and CP estimates with check tests, for:  
    + race/ancestry PCs (**not in submitted draft of paper**).  
    + lifetime PTSD  
    + Sex  
- **Combined_LeukoComp_450K_nonParametric_SexStrat.Rmd**: Sex-stratified non-parametric analyses for lifetime PTSD and PTSD status.  
- **Combined_LeukoCompLM_450K_sqrt_Mono100.Rmd**: 2-way ANCOVA and post-hoc emmeans tests 

### Tables
- **Combined_LeukoComp_450K_Tab1_DescriptiveStats.Rmd**: for Table 1 of paper (Key demographic characteristics of the DNHS and GTP)  
- **followUpCombined_LeukoCompLM_450K_sqrt_Mono100.Rmd**: follows up notebook for 2-way ANCOVA and post-hoc emmeans tests.  Outputs all tables (including supplementary) except Table 1, as html in R notebook.  This was copy/pasted to word docx for final formatting.

### Figures  
- **Combined_LeukoCompLM_450K_sqrt_Mono100.Rmd**: Outputs raw data files for Figure 4 (Interaction Plots)  
    + *Note:* Last run on 12/18/2018.  Raw files from this run used for submission  
        + Output sub-directory: **20181218_Combined_LeukoCompLM_450K_sqrt_Mono100_40369cb**
- **FigsPlots.Rmd**: Outputs raw data files for all figures (including supplementary), except Figure 4, as pdf in output folder.  
    + *Note:* Last run on 12/21/2018.  Raw files from this run used for submission  
        + Output sub-directory: **20181221_added_Figures_Plots_v3_40369cb**
- *Note:* Raw output files generated in R were arranged using Adobe InDesign.  Files were exported back to pdf and combined for submitted figure set.  Individual *.indd* and *.pdf* files available on request.  

***

**Title:** Methylomic profiles reveal sex-specific shifts in leukocyte composition associated with post-traumatic stress disorder (PTSD)  

**Contact:** Grace Kim &nbsp;&nbsp;(<gkim53@illinois.edu>)  
**PI:** Monica Uddin &nbsp;&nbsp;(<monica43@health.usf.edu>) 

**Institutions:**  
- University of Illinois at Urbana-Champaign  
    + Carl R. Woese Institute for Genomic Biology; Neuroscience Program; Medical Scholars Program
- University of South Florida  
    + Genomics Program, College of Public Health

***