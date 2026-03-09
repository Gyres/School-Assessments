# Airline Passenger Satisfaction Clustering

This project analyses airline passenger satisfaction data to uncover the key factors that influence customer experience. It combines exploratory data analysis (EDA) with K-means clustering to segment passengers into meaningful groups and generate targeted business recommendations for improving satisfaction and operational efficiency.

## Project Overview
- **Institution:** Singapore University of Social Sciences (SUSS)
- **Project Type:** Individual
- **Academic Term:** Jan 2025
- **Status:** Completed

## Problem Statement
Airlines operate in a highly competitive environment where customer satisfaction is a key differentiator. This project explores passenger demographics, travel characteristics, service quality ratings, and delay variables to better understand satisfaction patterns and identify passenger segments that can support more targeted service, marketing, and operational improvements.

## Objectives
- Explore and analyse passenger data to understand customer behaviour and the key drivers of satisfaction.
- Identify patterns and relationships among flight characteristics, service ratings, and demographic factors.
- Apply K-means clustering to segment passengers into distinct groups.
- Generate insights and recommendations to improve passenger experience and airline performance.

## Dataset

### Source
- Airline Passenger Satisfaction dataset used for the project

### Description
- **Number of rows:** 103,904
- **Number of features:** 25 original variables
- **Target variable:** `satisfaction`
- **Data type:** Tabular

### Key Variables
- **Demographics:** Gender, Age, Customer Type
- **Travel Details:** Type of Travel, Class, Flight Distance
- **Service Ratings:** Inflight Wi-Fi, Departure/Arrival Time Convenient, Ease of Online Booking, Gate Location, Food and Drink, Online Boarding, Seat Comfort, Inflight Entertainment, On-board Service, Leg Room Service, Baggage Handling, Check-in Service, Inflight Service, Cleanliness
- **Operational Variables:** Departure Delay in Minutes, Arrival Delay in Minutes
- **Outcome Variable:** Satisfaction

### Notes
- `Arrival Delay in Minutes` contained 310 missing values.
- Missing values were handled using mean imputation to retain all observations.
- Numeric variables were standardised before clustering.
- Categorical variables were label-encoded to make them suitable for K-means clustering.
- The dataset includes both passenger profile variables and service-experience variables, making it suitable for segmentation analysis.

## Tools and Technologies
- **Programming Language:** Python
- **Environment:** Jupyter Notebook
- **Libraries / Frameworks:** pandas, numpy, matplotlib, seaborn, scikit-learn
- **Methods Used:** Data cleaning, mean imputation, standardisation, label encoding, correlation analysis, K-means clustering, Elbow Method, Silhouette Score, PCA
- **Other Tools:** Git, GitHub, Microsoft Word

## Methodology
1. Loaded and reviewed the airline passenger satisfaction dataset.
2. Performed data cleaning and handled missing values using mean imputation.
3. Conducted exploratory data analysis on categorical and numeric variables.
4. Examined relationships using visualisations and correlation analysis.
5. Standardised numeric features using `StandardScaler`.
6. Encoded categorical variables using `LabelEncoder`.
7. Combined scaled numeric and encoded categorical features into a numeric matrix for clustering.
8. Evaluated candidate values of `k` using the Elbow Method and Silhouette Score.
9. Selected `k = 6` and applied K-means clustering.
10. Interpreted cluster profiles and translated the findings into business insights and recommendations.

## Repository Structure
```text
school-assessments/
└── da-airline-passenger-clustering/
    ├── Airline-Passenger-Satisfaction-Dataset.csv   # Dataset
    ├── airline-passenger-clustering.ipynb           # Main notebook for EDA and clustering
    └── README.md                                    # Project documentation
```

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Gyres/school-assessments.git
   ```

2. Open the project folder:
   ```bash
   cd school-assessments/da-airline-passenger-clustering
   ```

3. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

5. Open `airline-passenger-clustering.ipynb` and run the notebook cells in sequence.

## Results

### Key Findings
- Passenger satisfaction is strongly associated with digital touchpoints such as online boarding, inflight Wi-Fi, and ease of online booking.
- Comfort-related features such as seat comfort, leg room, cleanliness, and inflight entertainment are important contributors to satisfaction.
- K-means clustering identified **6 distinct passenger segments**, enabling more targeted service and marketing strategies.
- One small cluster was heavily affected by extreme delays, highlighting an important operational pain point.
- Business-class and loyal passengers tended to appear more frequently in the highly satisfied clusters.

### Performance Metrics
| Metric | Value |
|--------|------:|
| Number of observations | 103,904 |
| Number of original variables | 25 |
| Missing values imputed (`Arrival Delay in Minutes`) | 310 |
| Selected number of clusters (`k`) | 6 |
| Largest cluster size | 23,840 |
| Smallest cluster size | 3,351 |
| Approximate silhouette score for viable solutions | 0.11–0.12 |

### Cluster Summary
- **Cluster 0:** Mostly economy-class travellers with below-average online booking and online boarding ratings, but relatively better food, entertainment, and cleanliness scores. Most passengers in this cluster are neutral or dissatisfied.
- **Cluster 1:** Lower-satisfaction segment with weak ratings in food and drink, seat comfort, inflight entertainment, and cleanliness.
- **Cluster 2:** Mostly loyal customers but with low ratings for inflight entertainment, on-board service, leg room, baggage handling, and inflight service, suggesting persistent service issues.
- **Cluster 3:** Highly satisfied, tech-oriented, and convenience-focused segment with strong ratings for inflight Wi-Fi, online booking, gate location, and online boarding.
- **Cluster 4:** Highest satisfaction cluster, dominated by business-class passengers on longer flights with strong comfort and service ratings.
- **Cluster 5:** Smallest cluster, characterised by extremely high departure and arrival delays.

## Visualisations / Outputs
Refer to `airline-passenger-clustering.ipynb` for visualisations and outputs.

## Business Insights and Recommendations
- **Retain high-value satisfied passengers:** Clusters 3 and 4 represent highly satisfied travellers, many of whom are loyal and business-oriented. Loyalty perks, upgrades, and personalised promotions can help retain them.
- **Improve onboard service for loyal but dissatisfied passengers:** Cluster 2 highlights an opportunity to improve leg room, baggage handling, entertainment, and inflight service for customers who already fly repeatedly with the airline.
- **Enhance economy-class experience:** Clusters 0 and 1 suggest that improvements in seat comfort, cleanliness, online boarding, and food quality could raise satisfaction in lower-performing segments.
- **Strengthen digital experience:** Better booking systems, smoother online boarding, and stronger inflight Wi-Fi could create broad satisfaction gains.
- **Reduce operational disruptions:** Cluster 5 points to severe delay issues that may require route-level or operational investigation, together with better service recovery measures such as vouchers or clearer communication.

## Limitations
- K-means requires the number of clusters to be chosen in advance.
- Label encoding for categorical variables may impose numeric relationships that do not naturally exist.
- Some clusters are much larger than others, which may affect interpretation.
- The analysis identifies patterns and segments, but it does not establish causation.
- Additional business variables such as route, booking channel, or seat upgrades were not included.

## Future Improvements
- Compare K-means with other clustering methods such as DBSCAN or hierarchical clustering.
- Add richer business variables such as route information, booking channels, and ancillary purchases.
- Combine clustering with predictive modelling to estimate satisfaction more directly.
- Use A/B testing or causal analysis to validate which service improvements have the greatest impact.
- Export notebook charts into an `images/` folder to improve GitHub presentation.

## Note
This repository is shared for portfolio purposes only.

Please do not copy, reuse, or submit this work as your own academic assignment.

## Contact
- **Name:** Ou Yang Yu
- **GitHub:** https://github.com/Gyres
- **Linktree:** https://linktr.ee/yuouyang
