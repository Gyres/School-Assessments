# Study: Propofol and Delirium in ARDS ICU Patients

#### Date: 2024-04-14

## Introduction

**Brief Overview:**
This descriptive analysis project is part of a larger study that investigates the association between the duration of propofol infusion and the incidence of delirium in ICU patients suffering from Acute Respiratory Distress Syndrome (ARDS). This project includes the key variables related to the study and provides visualisations and statistical insights into the factors influencing delirium risk.

The larger study is an assessment for a course at NUS Saw Swee Hock School of Public Health (SSHSPH), which aims to explore the factors contributing to delirium among ICU patients and to understand if the duration of propofol, a common sedative, plays a significant role in the development of delirium, particularly in ARDS patients.

The repository for the larger study is available at https://github.com/xuqianyi/SPH5104

**Objectives:**
- To determine the relationship between the duration of propofol use and delirium incidence.
- To assess whether other factors, such as age and ICU stay, influence delirium rates.

## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Data](#data)
- [Methodology](#methodology)
- [Results](#results)
- [Project Structure](#project-structure)
- [License](#license)
- [Contact Information](#contact-information)

---

## Installation
**Prerequisites:**
- R: Version 4.0 or later
- RStudio
<!--
**Environment Setup:**
1. Clone this repository to your local machine using:
```bash
git clone https://github.com/Gyres/School-Assessments.git
```
2. Navigate to the `Propofol-Delirium-Study` directory:
```bash
cd Propofol-Delirium-Study
```
-->
**Dependencies:**
Install necessary R packages:
```r
install.packages(c("tidyverse", "skimr", "ggplot2"))
```

## Usage
**Instructions:**
1. Access [Descriptive-Analysis-Propofol-Delirium.md](Descriptive-Analysis-Propofol-Delirium.md) to view the pre-run analysis.

    or

2. Open the R Markdown file (`Descriptive-Analysis-Propofol-Delirium.rmd`) in RStudio.
3. Run the code chunks to execute the descriptive analysis and generate visualizations.

## Data
**Data Sources:**
The dataset, `cohort_w_confounders.csv`, was extracted and modified from the MIMIC-IV relational database using SQL queries.

**Data Description:**
- **3862 rows** and **40 columns**
- Variables include demographic data, ICU stay details, propofol duration, and delirium status.

**Data Processing:**
- Variables were converted into appropriate types (`character`, `logical`, `numeric`).
- Missing values were handled, and some variables were mapped to categorical factors.

## Methodology
**Techniques Used:**
- Descriptive statistics (e.g., mean, median)
- Bivariate analysis (t-tests and visual comparisons)
- Statistical tests to assess differences between delirium and non-delirium groups

**Tools:**
- **R:** for data analysis and visualization
- **MIMIC-IV:** as the primary data source

## Results
**Findings:**
- Approximately **33.4%** of patients were diagnosed with delirium.
- **Older patients** and those with **longer ICU stays** had higher rates of delirium.
- Prolonged propofol infusion was associated with increased delirium risk.

**Visualisations:**
- Pie chart: Delirium incidence in ARDS patients.
- Histogram: Propofol Infusion Duration.
- Box plots: Age, ICU length of stay, Propofol Duration by delirium status.
- Scatter plots: Propofol duration vs. APACHE III score.

**Interpretation:**
The findings suggest that while propofol duration correlates with delirium, other factors such as age and illness severity also contribute to this risk, indicating the need for comprehensive sedation protocols.

## Project Structure
```markdown
Propofol-Delirium-Study/
│
├── README.md                                                 # Project overview and instructions
├── Descriptive-Analysis-Propofol-Delirium.md                 # Main analysis report
├── Descriptive-Analysis-Propofol-Delirium.rmd                # Main analysis script
├── cohort_w_confounders.csv                                  # Dataset derived from MIMIC-IV database
└── Descriptive-Analysis-Propofol-Delirium_files/figure-gfm/  # Directory to store generated plots
```

## License

This project is intended for submission as part of a technical assessment. The content and code are not intended for public distribution, reproduction, or commercial use without explicit permission from the Author.

## Contact Information

**Author:** Ou Yang Yu
