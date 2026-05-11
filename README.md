# Clinicopathological Profile and Psychosocial Experiences of Nigerian Breast Cancer Survivors

## Citation

Wuraola FO, Olasehinde O, Di Bernardo M, Aderounmu AA, Adisa AO, Omoyiola OZ, Omisore AD, Kingham TP, Mango V, Alatise OI. **Five-Year Breast Cancer Survivors in a Nigerian Tertiary Hospital: Clinicopathological Profile and Psychosocial Experiences.** *JCO Glob Oncol.* 2023 Jul;9:e2300022. doi: [10.1200/GO.23.00022](https://ascopubs.org/doi/full/10.1200/GO.23.00022). PMID: 37406205.

## Project Description

This repository contains the statistical analysis code for a retrospective cohort study examining the clinicopathological characteristics and outcomes of breast cancer patients who achieved 5-year survival at a Nigerian tertiary hospital. The study compares survivors with non-survivors to identify factors associated with long-term survival in a resource-limited setting.

### Key Features of the Analysis

1. **Descriptive Statistics**: Comprehensive characterization of survivors and non-survivors
2. **Statistical Comparisons**: Two-proportion tests, t-tests, and Wilcoxon rank sum tests comparing groups
3. **Survival Analysis**: Univariate Cox proportional hazards regression to identify prognostic factors
4. **Kaplan-Meier Curves**: Survival probability visualization stratified by clinical stage
5. **Median Survival Analysis**: Assessment of median survival times by clinical and treatment variables

### Study Population

- **Setting**: Obafemi Awolowo University Teaching Hospitals Complex (OAUTHC), Ile-Ife, Nigeria
- **Period**: Patients treated between January 2005 and December 2014
- **Participants**: 355 breast cancer patients (163 five-year survivors, 192 non-survivors)
- **Follow-up**: Minimum 5-year follow-up period

### Main Findings

The study found that advanced clinical stage (Stage III/IV) at presentation was significantly associated with worse survival outcomes. Five-year survivors were more likely to have received surgical intervention and adjuvant chemotherapy compared to non-survivors, highlighting the importance of multimodal treatment approaches even in resource-limited settings.

## Repository Structure

```
.
├── README.md                    # This file
├── analysis.R                   # Main analysis script with comprehensive documentation
├── data.csv                     # De-identified patient data
├── results/                     # Output directory for analysis results
│   ├── univariate_cox_regression.csv
│   ├── median_survival_univariate.csv
│   ├── cox_regression_clinical_stage.txt
│   └── kaplan_meier_clinical_stage.pdf
└── .gitignore                   # Git ignore file for R projects
```

## Requirements

### R Version
- R ≥ 4.0.0 recommended

### R Package Dependencies

```r
# Data manipulation
dplyr
lubridate

# Survival analysis
survival
survminer

# Data import and formatting
haven          # For SPSS/Stata/SAS files
sjlabelled     # For working with labelled data
finalfit       # For clinical data tables
```

### Installation

Install required packages using the following R commands:

```r
install.packages(c("dplyr", "survminer", "survival", "lubridate",
                   "finalfit", "haven", "sjlabelled"))
```

## Usage

### Running the Analysis

1. Clone this repository or download the files
2. Ensure all required R packages are installed (see Requirements above)
3. Set your working directory to the repository folder:
   ```r
   setwd("/path/to/git_repo")
   ```
4. Run the analysis script:
   ```r
   source("analysis.R")
   ```

### Expected Outputs

The analysis will generate the following files in the `results/` directory:

1. **univariate_cox_regression.csv**: Hazard ratios, confidence intervals, and p-values for all covariates
2. **median_survival_univariate.csv**: Median survival times stratified by each clinical variable
3. **cox_regression_clinical_stage.txt**: Detailed Cox regression output for clinical stage
4. **kaplan_meier_clinical_stage.pdf**: Survival curves comparing early (I/II) vs advanced (III/IV) stage

## Data Dictionary

### Key Variables

| Variable | Description | Values/Units |
|----------|-------------|--------------|
| `age` | Patient age at diagnosis | Years |
| `age_grouped` | Age categories | 1: <40, 2: 40-64, 3: ≥65 |
| `mass_size` | Tumor size | Centimeters |
| `complaint_duration` | Duration of symptoms before presentation | Months |
| `overall_clinical_stage` | TNM clinical stage | 1: Stage I, 2: Stage II, 3: Stage III, 4: Stage IV |
| `overall_clinical_stage_grouped` | Grouped clinical stage | 1: Stage I/II, 2: Stage III/IV |
| `grade` | Nottingham histologic grade | 1: Well differentiated, 2: Moderately differentiated, 3: Poorly differentiated |
| `ihc_er` | Estrogen receptor status | 0: Negative, 1: Positive |
| `ihc_pr` | Progesterone receptor status | 0: Negative, 1: Positive |
| `ihc_her2` | HER2 status | 0: Negative, 1: Positive |
| `ihc_triple_neg` | Triple negative status | 0: No, 1: Yes (ER-/PR-/HER2-) |
| `neoadjuvant` | Received neoadjuvant chemotherapy | 0: No, 1: Yes |
| `adjuvant` | Received adjuvant chemotherapy | 0: No, 1: Yes |
| `surgery` | Received surgical treatment | 0: No, 1: Yes |
| `radiotherapy` | Received radiotherapy | 0: No, 1: Yes |
| `multimodal` | Received multimodal treatment (surgery + radiotherapy + chemotherapy) | 0: No, 1: Yes |
| `status` | Follow-up status | 1: Alive, 2: Lost to follow-up, 3: Deceased |
| `time` | Survival time | Months from diagnosis to death or last follow-up |

## Statistical Methods

### Descriptive Analysis
- Continuous variables: Mean ± SD, median (IQR)
- Categorical variables: Frequencies and percentages

### Comparative Analysis
- **Binary variables**: Two-proportion z-tests
- **Continuous variables**: Two-sample t-tests (assuming unequal variances)
- **Ordinal variables**: Wilcoxon rank sum tests

### Survival Analysis
- **Univariate Cox regression**: Separate models for each covariate
- **Kaplan-Meier curves**: Survival probability estimation with log-rank tests
- **Proportional hazards assumption**: Tested using Schoenfeld residuals

## Ethics

This study was approved by the Ethics and Research Committee of Obafemi Awolowo University Teaching Hospitals Complex (OAUTHC). All data have been de-identified to protect patient privacy.

## Authors

- **Funmilola Olanike Wuraola** (Principal Investigator)
- Olalekan Olasehinde
- Matteo Di Bernardo
- Adewale Abdulwasiu Aderounmu
- Adewale Oluseye Adisa
- Oluwatosin Zaniab Omoyiola
- Adeleye Dorcas Omisore
- Thomas Peter Kingham
- Victoria Mango
- Olusegun Isaac Alatise

## License

This code is provided for research and educational purposes. Please cite the original publication when using this code or data.

## Contact

For questions about the analysis or data, please contact the corresponding author through the journal publication.

## Acknowledgments

This research was conducted at Obafemi Awolowo University Teaching Hospitals Complex (OAUTHC), Ile-Ife, Nigeria. We thank all patients who participated in this study and the healthcare providers who contributed to their care.
