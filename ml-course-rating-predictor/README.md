# SkillsFuture Healthcare Course Rating Predictor

This project applies machine learning to analyse SkillsFuture Singapore (SSG) healthcare courses and predict whether a course is likely to receive a high learner rating. It combines data cleaning, exploratory data analysis, regression, and classification to generate both predictive performance and interpretable business insights.

## Project Overview
- **Institution:** Singapore University of Social Sciences (SUSS)
- **Project Type:** Group
- **Academic Term:** Jul 2025
- **Status:** Completed

## Problem Statement
SkillsFuture Singapore offers a large number of healthcare-related courses, but it is not always clear which course characteristics are associated with stronger learner satisfaction. This project addresses that gap by building predictive and interpretable machine learning models to identify whether factors such as course fee, course hours, duration, and training provider are linked to high learner ratings.

## Objectives
- Clean and prepare the SSG healthcare course dataset for analysis and modelling.
- Explore relationships between course attributes and learner ratings.
- Build predictive models to classify whether a course is likely to receive a high rating.
- Compare model performance across regression and classification approaches.
- Extract interpretable insights that can support provider optimisation and policy decisions.

## Dataset

### Source
- SkillsFuture Singapore (SSG) Healthcare Courses Dataset used for academic coursework.

### Description
- **Number of rows:** 1,703 course records in the raw dataset
- **Rows with valid ratings for modelling:** 538
- **Number of columns:** 13 original variables
- **Target variable:** `High_Rating_Label` where `1 = rating >= 4` and `0 = rating < 4`
- **Data type:** Tabular

### Notes
- Significant missing values were present in learner-related columns:
  - `No. of Learners`: 1,063 missing
  - `No. of Learners who Rated`: 1,165 missing
  - `Ratings out of 5`: 1,165 missing
- `Course Fee after Maximum Subsidiy` required numeric conversion and missing-value handling.
- `Course Type` values such as `Part Time` and `Part time` were standardised.
- 46 rows showed inconsistent learner counts where the number who rated exceeded the number of learners.
- The dataset is highly imbalanced for classification, with about 86% of rated courses labelled as high-rated.

## Tools and Technologies
- **Programming Language:** Python
- **Environment:** Jupyter Notebook
- **Libraries / Frameworks:** pandas, numpy, matplotlib, seaborn, scikit-learn
- **Other Tools:** GitHub

## Methodology
1. Load the raw healthcare course dataset and inspect structure, data types, and missing values.
2. Clean the data by correcting column types, fixing categorical inconsistencies, and handling null values.
3. Perform exploratory data analysis on distributions, outliers, correlations, and provider-level patterns.
4. Create a binary target label for high ratings using the threshold `rating >= 4`.
5. Select features such as course fee, course hours, course type, course duration, training company, and year introduced.
6. Encode categorical variables for modelling.
7. Split the modelling dataset into training and testing sets.
8. Train a Linear Regression model for continuous rating prediction as a baseline.
9. Train Logistic Regression and Decision Tree Classifier models for high-rating prediction.
10. Evaluate models using regression and classification metrics, confusion matrices, and feature importance.

## Repository Structure
```text
school-assessments/
└── ml-course-rating-predictor/
    ├── 01_data_preprocessing_health_courses.ipynb   # Data loading, cleaning, and preprocessing
    ├── 02_eda_and_rating_prediction_model.ipynb     # EDA, feature engineering, and modelling
    ├── SSG_Healthcare_Courses_Dataset.csv           # Dataset
    └── README.md                                    # Project documentation
```

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Gyres/school-assessments.git
   ```
2. Move into the project folder:
   ```bash
   cd school-assessments/ml-course-rating-predictor
   ```
3. Install the required packages:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```
4. Ensure the dataset files used by the notebooks are available in the working directory:
   - `SSG_Healthcare_Courses_Dataset.csv`
   - `SSG_Healthcare_Courses_Cleaned.csv` (Generated from the code)
5. Run the notebooks in sequence:
   - `01_data_preprocessing_health_courses.ipynb`
   - `02_eda_and_rating_prediction_model.ipynb`

## Results

### Key Findings
- Learner ratings were generally high, with a mean rating of **4.29 / 5** among rated courses.
- Course fee and course hours showed weak negative relationships with ratings, suggesting that higher cost or longer duration did not guarantee higher satisfaction.
- Logistic Regression achieved the strongest overall accuracy and perfect recall for the majority high-rating class, but struggled with the minority low-rating class.
- Decision Tree delivered slightly lower accuracy but provided better interpretability through feature importance.
- The most influential factors for predicting high ratings were **Course Fee**, **Course Hours**, and **Training Company**.

### Performance Metrics
| Model | Metric | Value |
|------|------|------:|
| Linear Regression | R² | 0.0015 |
| Linear Regression | MAE | 0.2875 |
| Linear Regression | RMSE | 0.4589 |
| Logistic Regression | Accuracy | 0.8642 |
| Logistic Regression | Precision (High Rating) | 0.8642 |
| Logistic Regression | Recall (High Rating) | 1.0000 |
| Logistic Regression | F1-score (High Rating) | 0.93 |
| Decision Tree Classifier | Accuracy | 0.8210 |
| Decision Tree Classifier | Precision (High Rating) | 0.88 |
| Decision Tree Classifier | Recall (High Rating) | 0.91 |
| Decision Tree Classifier | F1-score (High Rating) | 0.90 |

## Visualisations / Outputs
Refer to `01_data_preprocessing_health_courses.ipynb` and `02_eda_and_rating_prediction_model.ipynb` for visualisations and outputs.

## Limitations
- Only 538 out of 1,703 courses had valid ratings, reducing the effective sample size for modelling.
- Strong class imbalance limited the ability to identify low-rated courses accurately.
- Several learner-related fields contained missing or inconsistent values.
- Important qualitative factors such as instructor quality, course relevance, and written learner feedback were not available.
- Results may change as new courses are introduced or policies evolve.

## Future Improvements
- Address class imbalance using resampling, class weighting, or alternative evaluation strategies.
- Add more advanced models such as Random Forest, XGBoost, or other ensemble methods.
- Incorporate text analytics or sentiment analysis from learner reviews if available.
- Improve feature engineering around subsidy levels, provider reputation, and course categories.
- Package the workflow into reusable scripts and add a `requirements.txt` file for easier reproducibility.

## License
This repository is shared for portfolio purposes only.

Please do not copy, submit, or present this work as your own academic assignment.

## Contact
- **Name:** Ou Yang Yu
- **GitHub:** https://github.com/Gyres
- **Linktree:** https://linktr.ee/yuouyang
