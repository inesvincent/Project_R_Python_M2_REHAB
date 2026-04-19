# R and Python project for Master’s internship 

----------

# Handgrip Strength and Functionnal Performance in Patients with Interstitial Lung Disease (ILD)

## 1. Scientific problem
### 1.1. Context

Interstitial lung diseases (ILDs) constitute a heterogeneous group of lung disorders characterized by diffuse damage to the pulmonary interstitium, leading to impaired gas exchange, dyspnea, and reduced exercise tolerance. These conditions have a significant impact on physical capacity and daily life (College of Pulmonology Educators, 2023). Beyond respiratory symptoms, IPDs can contribute to reduced physical activity and general deconditioning.
Grip strength can serve as a simple measure of muscle strength and provide predictive information on short- and long-term mortality and morbidity (Bohannon, 2019; Norman et al., 2011). However, its ability to reflect overall muscle strength remains controversial (Szaflik et al., 2024). Functional performance can be assessed using clinical tests such as walking speed and the “five-time sit-to-stand” (5STS) test, which evaluate mobility, lower limb strength, and overall functional capacity (Jones et al., 1999).

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

- `handgrip_strength`: upper-limb muscle strength  
- `walk_time_4m`: time (in seconds) to complete the 4-meter walk test  
- `time_5_raise_chair`: time (in seconds) to perform the five-times sit-to-stand (5STS) test  

Derived variable:

- **Walking speed (m/s)** calculated as:  
  `walking_speed = 4 / walk_time_4m`  

---

### 2.3. Notebook

#### main.ipynb

**Aim:**  
Clean the dataset and compute derived variables.

**Input:**  
`frapid_base.xlsx`  

**Output:**  
`frapid_data_clean.csv` (generated during execution)  

**Additional steps:**  
Basic exploratory analysis, including population description and visualization of variable distributions.

---

## 3. R project

### 3.1. Aim

The objective of this analysis is to assess the association between handgrip strength and functional performance (walking speed and 5STS) in patients with ILD.

---

### 3.2. Data analysis

Statistical analyses were performed using R:

- Descriptive statistics of the study population  
- Assessment of variable distribution (QQ-plots and Shapiro-Wilk test)  
- Correlation analysis between handgrip strength and functional performance (Pearson or Spearman, depending on distribution)  
- Adjusted analysis using linear regression models including age and sex  
- Visualization of relationships between variables  

---

### 3.3. Script

#### ines.vincent.Rmd

**Aim:**  
Perform statistical analyses and generate results.

**Input:**  
`frapid_data_clean.csv`  

**Content:**

- Data import and preparation  
- Descriptive statistics  
- Normality assessment  
- Correlation analysis (handgrip strength vs walking speed and 5STS)  
- Adjusted analysis using linear regression models (age and sex)  
- Graphical visualization  

**Output:**  
Statistical results and figures included in the final report  

 