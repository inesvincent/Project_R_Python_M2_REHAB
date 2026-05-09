# R and Python project for Master’s internship 

----------

# Association between Handgrip Strength and Functionnal Performance in Patients with Interstitial Lung Disease (ILD)

## 1. Scientific problem
### 1.1. Context

Interstitial lung diseases (ILD) constitute a heterogeneous group of lung disorders characterized by diffuse damage to the pulmonary interstitium, leading to impaired gas exchange, dyspnea, and reduced exercise tolerance. 
These conditions have a significant impact on physical capacity and daily life (Collège des Enseignants de Pneumologie, 2023).
Beyond respiratory symptoms, ILD may contribute to reduced physical activity and general physical deconditioning, which can alter mobility and overall functional performance (Bloem et al., 2020).

Functional performance can be assessed using simple clinical tests such as walking speed and the five-times sit-to-stand (5STS) test, which reflect mobility, lower-limb strength, and functional capacity (Jones et al., 1999).
Handgrip strength is commonly used as a simple and rapid indicator of muscle strength and has been associated with functional performance and health outcomes in older adults (Bohannon, 2019; Norman et al., 2011). 
However, its ability to reflect overall muscle strength and global functional performance remains debated depending on the populations and methodologies studied (Szaflik et al., 2025).

**Research question:**
Is handgrip strength associated with walking speed and five-times sit-to-stand (5STS) performance in patients with ILD?

### 1.2. Aim
The aim of this study is to investigate the association between handgrip strength and functional performance in patients with ILD aged over 65 years, using walking speed and the five-times sit-to-stand (5STS) test as clinical measures.

### 1.2.1 Hypothesis
Higher handgrip strength is associated with higher walking speed and shorter completion time on the 5STS test in patients with ILD.

### 1.3. Method
This monocentric study is based on a clinical database of 47 patients with ILD.
Data were collected during routine pulmonology consultations.
Handgrip strength was used to assess upper-limb muscle strength. Functional performance was evaluated using the 4-meter walk test and the five-times sit-to-stand (5STS) test. 
Walking speed was derives from the 4-meter walk test using the following formula :

$$walking\ speed\ (m/s) = \frac{4}{walk\_time\_4m}$$

### 1.4. Participants
The study included 47 patients aged over 65 years diagnosed with ILD after a multidisciplinary discussion.

### 1.5. Outcome measure
Handgrip strength was considered the main explanatory variable.
The primary outcome was walking speed derived from the 4-meter walk test, while the secondary outcome was performance on the five-times sit-to-stand (5STS) test.

### 1.6. Project organization
## 2. Project organization

```text
Project_R_Python_M2_REHAB/
│
├── VINCENT.INES.Rproj                  R project configuration file
│   
│
├── vincent.ines.ipynb                  Python notebook used for data cleaning
│   
│   
├── vincent.ines.Rmd                    R Markdown file used for statistical analyses
│   
│
├── vincent.ines_Python.html            HTML export of the Python notebook
│   
│
├── vincent.ines_RStudio.html           HTML export of the R Markdown analysis
│   
│
├── readme.md                           General presentation of the project
│   
│
├── LICENSE                             Project license
│   
│
├── data/                               Data folder  
│   ├── raw/                            Raw data folder
│   │   └── frapid_base.xlsx            Data file to be analyzed
│   │       
│   │
│   └── clean/                          Clean data folder
│       └── frapid_data_clean.csv       Cleaned dataset used for analyses
│           
│
└── results/                            Results folder
    ├── tables/                         Results tables
    │   ├── frapid_data_clean.csv       Clean dataset obtained after cleaning in Python
    │   └── descriptive_statistics.csv  Descriptive statistics of the study population
    │
    └── figures/                        Folder of figures obtained during the analysis
        ├── walking_speed_distribution.png
        ├── handgrip_strength_distribution.png
        ├── 5sts_time_distribution.png
        ├── handgrip_vs_walking_speed_scatterplot.png
        └── handgrip_vs_5sts_scatterplot.png
```
----------

## 2. Python project

### 2.1. Aim
The objective of the Python project was to clean, structure, and preprocess the clinical dataset before statistical analysis.
Python was used to create a reproducible workflow for data preparation, management of missing values, variable formatting, and generation of derived variables such as walking speed.

### 2.2. Data

Input dataset :
- **frapid_base.xlsx**: raw clinical dataset including patient characteristics and functional test results  

Output dataset :
- **frapid_data_clean.csv**: cleaned dataset generated during preprocessing and used for statistical analysis in R. 

The dataset includes the following variables:

- `patient_id`: unique identifier for each participant  
- `age`: age of the participant (years)  
- `gender`: sex of the participant 
- `handgrip_strength`: upper-limb muscle strength (kg)
- `walk_time_4m`: time (in seconds) to complete the 4-meter walk test  
- `time_5_raise_chair`: time (in seconds) to perform the five-times sit-to-stand (5STS) test  
- `walking_speed_mps`: walking speed (m/s) derived from the 4-meter walk test test

Derived variable:
$$ walking\ speed\ (m/s) = \frac{4}{walk\_time\_4m}$$ 

---

### 2.3. Notebook organization

#### vincent.ines.ipynb

**Aim:**  
Clean and preprocess the clinical dataset, and create derived variables for statistical analysis.

**Input:**  
`data/raw/frapid_base.xlsx`

**Output:**  
`data/clean/frapid_data_clean.csv`

**Content:**
  - Data import and initial inspection  
  - Data cleaning (handling missing values, formatting variables)  
  - Creation of derived variables (walking speed)  
  - Descriptive statistics and exploratory visualizations

---

## 3. R project

### 3.1. Aim

The objective of the R analysis was to assess the association between handgrip strength and functional performance in patients with ILD.

---

### 3.2. Data organization

The cleaned dataset used for statistical analysis included:

  - `patient_id`: unique identifier for each participant  
  - `age`: age of the participant (years)  
  - `gender`: sex of the participant 
  - `handgrip_strength`: upper-limb muscle strength  
  - `walk_time_4m`: time (in seconds) to complete the 4-meter walk test  
  - `time_5_raise_chair`: time (in seconds) to perform the five-times sit-to-stand (5STS) test
  - `walking_speed_mps`: walking speed (m/s), calculated as 4 / walk_time_4m  


### 3.3. Statistical analysis

Statistical analyses were performed using the R.

The normality of the variables was assessed using QQ plots and the Shapiro-Wilk test.

Depending on the data distribution, the correlation analyses were adapted:

  - Pearson’s correlation can be used for normally distributed variables
  - Spearman’s correlation is preferred when the assumptions of normality are not fully met.

Because normality assumptions were not fully met for all variables, 
Spearman correlations were preferred to ensure robustness and methodological consistency.

The following analyses were conducted:

  - Descriptive statistics of the study population
  - Assessment of normality using QQ plots and Shapiro-Wilk tests
  - Correlation analyses between handgrip strength and functional performance
  - Visualization of associations using scatterplots and LOESS curves
  - Adjusted analyses using linear regression models including age and sex as covariates

---

### 3.4. Script

#### vincent.ines.Rmd

**Aim:**  
Perform statistical analyses and generate figures and results.

**Input:**  
`data/clean/frapid_data_clean.csv`

**Content:**

  - Data import and preprocessing  
  - Descriptive statistics of the study population  
  - Assessment of normality (QQ-plots and Shapiro-Wilk test)  
  - Correlation analysis using Spearman correlation (handgrip strength vs walking speed and 5STS)  
  - Adjusted analysis using linear regression models including age and sex  
  - Interpretation of statistical results.

**Output:**  
Statistical results and figures used in the final report

## 4. Conclusion

This project highlights an association between handgrip strength and functional performance in patients with ILD. Higher grip strength is associated with better performance, particularly for walking speed.
After adjustment for age and sex, the association with walking speed remains significant, suggesting an independent effect of muscle strength. In contrast, the association with the 5STS test is no longer significant after adjustment, indicating a potential influence of age.
Overall, these findings suggest that handgrip strength may be a relevant indicator of functional performance, while age appears to be a key determinant of physical capacity in this population.

## 5. Tools and assistance

Artificial intelligence tools such as ChatGPT were occasionally used as methodological and programming support, particularly for debugging, code clarification.

## 6. References

1.	Collège des Enseignants de Pneumologie, 2023, item_210_PNEUMOPATHIES INTERSTITIELLES DIFFUSES.
2.  Bloem AEM, Veltkamp M, Spruit MA, Custers JWH, Bakker EWP, Dolk HM, et al. Validation of 4-meter-gait-speed test and 5-repetitions-sit-to-stand test in patients with pulmonary fbrosis: A clinimetric validation study. Sarcoidosis Vasc Diffuse Lung Dis. 2018 Jan 1;35(4):317–26. doi:10.36141/svdld.v35i4.7035
3.	Jones CJ, Rikli RE, Beam WC. A 30-s chair-stand test as a measure of lower body strength in community-residing older adults. Res Q Exerc Sport. 1999 Jun;70(2):113–9. doi:10.1080/02701367.1999.10608028 PubMed PMID: 10380242.
4.	Bohannon RW. Grip Strength: An Indispensable Biomarker For Older Adults. Clin Interv Aging. 2019 Oct 1;14:1681–91. doi:10.2147/CIA.S194543 PubMed PMID: 31631989; PubMed Central PMCID: PMC6778477.
5.	Norman K, Stobäus N, Gonzalez MC, Schulzke JD, Pirlich M. Hand grip strength: Outcome predictor and marker of nutritional status. Clin Nutr. 2011 Apr;30(2):135–42. doi:10.1016/j.clnu.2010.09.010
6.	Szaflik P, Zadoń H, Michnik R, Nowakowska-Lipiec K. Handgrip Strength as an Indicator of Overall Strength and Functional Performance—Systematic Review. Appl Sci. 2025 Jan;15(4):1847. doi:10.3390/app15041847


