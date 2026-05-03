# R and Python project for Master’s internship 

----------

# Handgrip Strength and Functionnal Performance in Patients with Interstitial Lung Disease (ILD)

## 1. Scientific problem
### 1.1. Context

Interstitial lung diseases (ILDs) constitute a heterogeneous group of lung disorders characterized by diffuse damage to the pulmonary interstitium, leading to impaired gas exchange, dyspnea, and reduced exercise tolerance. These conditions have a significant impact on physical capacity and daily life (College of Pulmonology Educators, 2023). Beyond respiratory symptoms, IPDs can contribute to reduced physical activity and general deconditioning (Bloem et al., 2020).

What we aim to determine: To evaluate whether handgrip strength is associated with functional performance in patients with ILD.

### 1.2. Aim
The aim of this study is to investigate the association between handgrip strength and functional performance in patients with ILD aged over 65 years, using walking speed and the five-times sit-to-stand (5STS) test as clinical measures.

### 1.3. Method
This monocentric study is based on a database of 48 patients with ILD, collected during routine pneumology consultations.
Handgrip strength was used to assess upper-limb muscle strength. Functional performance was evaluated using the 4-meter walk test and the five-times sit-to-stand (5STS) test. Walking speed was calculated as:
Walking speed (m/s) = 4 / walk_time_4m

### 1.4. Participants
The study included 48 patients aged over 65 years diagnosed with ILD after a multidisciplinary discussion.

### 1.5. Outcome measure
The main variables analyzed were handgrip strength, walking speed, and performance on the five-times sit-to-stand (5STS) test.

----------

## 2. Python project

### 2.1. Aim

The objective of this project is to clean and structure the clinical dataset and to compute derived variables such as walking speed from the 4-meter walk test.

---

### 2.2. Data

- **frapid_base.xlsx**: raw clinical dataset including patient characteristics and functional test results  
- **frapid_data_clean.csv**: cleaned dataset generated during preprocessing and used for statistical analysis  

The dataset includes the following variables:

- `patient_id`: unique identifier for each participant  
- `age`: age of the participant (years)  
- `gender`: sex of the participant 
- `handgrip_strength`: upper-limb muscle strength  
- `walk_time_4m`: time (in seconds) to complete the 4-meter walk test  
- `time_5_raise_chair`: time (in seconds) to perform the five-times sit-to-stand (5STS) test  

Derived variable:

- **Walking speed (m/s)** calculated as:  
  `walking_speed = 4 / walk_time_4m`  
  

---

### 2.3. Notebook

### 2.3. Notebook organization

#### vincent.ines.ipynb

**Aim:**  
Clean and preprocess the clinical dataset, and compute derived variables.

**Input:**  
`data/raw/frapid_base.xlsx`

**Output:**  
`data/clean/frapid_data_clean.csv`

**Content:**
- Data import and initial inspection  
- Data cleaning (handling missing values, formatting variables)  
- Creation of derived variables (walking speed)  
- Basic exploratory analysis (descriptive statistics and visualization)

---

## 3. R project

### 3.1. Aim

The objective of this analysis is to assess the association between handgrip strength and functional performance (walking speed and 5STS) in patients with ILD.

---

3.2. Data organization

- `patient_id`: unique identifier for each participant  
- `age`: age of the participant (years)  
- `gender`: sex of the participant 
- `handgrip_strength`: upper-limb muscle strength  
- `walk_time_4m`: time (in seconds) to complete the 4-meter walk test  
- `time_5_raise_chair`: time (in seconds) to perform the five-times sit-to-stand (5STS) test
- `walking_speed_mps`: walking speed (m/s), calculated as 4 / walk_time_4m  


### 3.2. Data analysis

Statistical analyses were performed using R:

- Descriptive statistics of the study population  
- Assessment of normality using QQ-plots and the Shapiro-Wilk test  
- Correlation analysis between handgrip strength and functional performance (Spearman correlation)  
- Adjusted analysis using linear regression models including age and sex  

---

### 3.3. Script

### 3.3. Script

#### vincent.ines.Rmd

**Aim:**  
Perform statistical analyses and generate results.

**Input:**  
`data/clean/frapid_data_clean.csv`

**Content:**

- Data import and preprocessing  
- Descriptive statistics of the study population  
- Assessment of normality (QQ-plots and Shapiro-Wilk test)  
- Correlation analysis using Spearman correlation (handgrip strength vs walking speed and 5STS)  
- Adjusted analysis using linear regression models including age and sex  
- Visualization of distributions and relationships between variables  

**Output:**  
Statistical results and figures used in the final report

## 4. Conclusion

This project highlights an association between handgrip strength and functional performance in patients with ILD. Higher grip strength is associated with better performance, particularly for walking speed.
After adjustment for age and sex, the association with walking speed remains significant, suggesting an independent effect of muscle strength. In contrast, the association with the 5STS test is no longer significant after adjustment, indicating a potential influence of age.
Overall, these findings suggest that handgrip strength may be a relevant indicator of functional performance, while age appears to be a key determinant of physical capacity in this population.
 
## 5. References

1.	item_210_PNEUMOPATHIES INTERSTITIELLES DIFFUSES.
2.	Szaflik P, Zadoń H, Michnik R, Nowakowska-Lipiec K. Handgrip Strength as an Indicator of Overall Strength and Functional Performance—Systematic Review. Appl Sci. 2025 Jan;15(4):1847. doi:10.3390/app15041847
3.	Bohannon RW. Grip Strength: An Indispensable Biomarker For Older Adults. Clin Interv Aging. 2019 Oct 1;14:1681–91. doi:10.2147/CIA.S194543 PubMed PMID: 31631989; PubMed Central PMCID: PMC6778477.
4.	Bloem AEM, Veltkamp M, Spruit MA, Custers JWH, Bakker EWP, Dolk HM, et al. Validation of 4-meter-gait-speed test and 5-repetitions-sit-to-stand test in patients with pulmonary fbrosis: A clinimetric validation study. Sarcoidosis Vasc Diffuse Lung Dis. 2018 Jan 1;35(4):317–26. doi:10.36141/svdld.v35i4.7035


