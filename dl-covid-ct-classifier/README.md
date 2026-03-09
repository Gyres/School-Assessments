# COVID-19 CT Scan Classifier

A deep learning and machine learning project for classifying chest CT scan images into **COVID-19** and **Non-COVID** classes. The notebook combines image preprocessing, baseline benchmarking, CNN experimentation, and deployment-oriented threshold analysis to explore how AI could support radiology triage and decision-making.

## Project Overview
- **Institution:** Singapore University of Social Sciences (SUSS)
- **Project Type:** Group
- **Academic Term:** Jul 2025
- **Status:** Completed

## Problem Statement
Distinguishing COVID-19 from non-COVID chest CT images can be difficult through visual inspection alone, especially for beginners in medical image analysis. This project explores whether machine learning and deep learning methods can support faster, more consistent CT image classification and provide practical insights for triage, workflow optimisation, and AI-assisted radiology support.

## Objectives
- Build a binary image-classification pipeline for **COVID-19 vs Non-COVID** CT scans.
- Compare a custom CNN against traditional machine learning baselines built on **HOG features**.
- Evaluate the model beyond accuracy using **ROC-AUC, PR-AUC, calibration, thresholding, and decision-curve analysis**.
- Explore how prediction probabilities can be translated into **triage buckets** and operational decision support.

## Dataset

### Source
- Public CT scan image dataset referenced from Kaggle: **“Covid detection by CT-scan images using CNN”**

### Description
- **Approximate image count detected in the notebook:** 1,492 CT images
  - **COVID:** 698
  - **Non-COVID:** 794
- **Classes:** 2
- **Target variable:** Binary class label (`COVID`, `Non-COVID`)
- **Data type:** Grayscale medical images (`.png`, `.jpg`, `.jpeg`, etc.)

### Notes
- The notebook uses a **stratified 70/15/15 split** for train/validation/test.
- In `FAST_MODE`, the working split is capped at:
  - **Train:** 800
  - **Validation:** 200
  - **Test:** 200
- The dataset is publicly sourced and appears limited in clinical metadata such as patient demographics and acquisition context.
- This project is intended for **academic experimentation and portfolio demonstration**, not clinical deployment.

## Tools and Technologies
- **Programming Language:** Python
- **Environment:** Jupyter Notebook
- **Libraries / Frameworks:** PyTorch, torchvision, scikit-learn, OpenCV, scikit-image, PIL, pandas, numpy, matplotlib, seaborn
- **Other Tools:** TensorBoard, Git, GitHub

## Methodology
1. Configure a reproducible, CPU-first notebook environment with centralized settings for batch size, epochs, and logging.
2. Resolve dataset paths, validate image files, and inspect class distribution.
3. Preprocess CT images using grayscale conversion, resizing, normalization, and light augmentation.
4. Split the dataset into train, validation, and test sets using **stratified sampling**.
5. Extract **HOG features** and train baseline models:
   - Logistic Regression
   - Decision Tree
6. Build a configurable **CNN classifier** with tunable activation, dropout, optimizer, scheduler, and loss function.
7. Run learning-rate exploration, grid-style tuning, early stopping, and retraining of the best configuration.
8. Evaluate models using:
   - Accuracy
   - Precision
   - Recall
   - F1-score
   - ROC-AUC
   - PR-AUC
   - Brier score
   - RMSE
9. Extend analysis with confusion matrices, calibration checks, triage thresholding, cost-sensitive threshold selection, and decision-curve analysis.

## Repository Structure
```text
school-assessments/
└── dl-covid-ct-classifier/
    ├── covid-ct-classification.ipynb   # Main project notebook
    └── README.md                       # Project documentation
```

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Gyres/school-assessments.git
   cd school-assessments/dl-covid-ct-classifier
   ```

2. Create and activate a Python environment.

3. Install the required packages:
   ```bash
   pip install torch torchvision torchaudio scikit-image scikit-learn opencv-python seaborn matplotlib tensorboard pandas numpy pillow
   ```

4. Download or prepare the CT image dataset and place it in the following structure: (image files are too big to upload on GitHub)
   ```text
   dl-covid-ct-classifier/
   └── CT-Scan-Images/
       ├── CT_COVID/
       └── CT_NonCOVID/
   ```

5. Launch Jupyter Notebook or JupyterLab:
   ```bash
   jupyter lab
   ```

6. Open:
   ```text
   covid-ct-classification.ipynb
   ```

7. Run the notebook from top to bottom.  
   - Keep `FAST_MODE = True` for quick CPU testing.
   - Set `FAST_MODE = False` for fuller experimentation.

## Results

### Key Findings
- The **HOG + Logistic Regression** baseline achieved the strongest benchmark performance in the main comparison section.
- The **Decision Tree** performed reasonably but lagged behind Logistic Regression.
- The notebook’s custom CNN underperformed in the main benchmark despite additional tuning, showing that simpler feature-based methods can still be competitive on smaller image datasets.
- Later sections of the notebook extend the work into **probability-based triage**, **cost-sensitive thresholding**, and **decision support analysis**.

### Benchmark Performance Metrics
| Model | Split | Accuracy | Precision | Recall | F1-score | ROC-AUC | PR-AUC |
|------|------:|---------:|----------:|-------:|---------:|--------:|-------:|
| Logistic Regression (HOG) | Test | 0.875 | 0.879 | 0.851 | 0.865 | 0.944 | 0.933 |
| Decision Tree (HOG) | Test | 0.800 | 0.787 | 0.787 | 0.787 | 0.799 | 0.720 |
| CNN (Best Notebook Run) | Test | 0.530 | 0.000 | 0.000 | 0.000 | 0.782 | 0.770 |

### Exploratory Triage / Operating-Point Analysis
The later part of the notebook also includes a deployment-oriented probability analysis on a smaller evaluation slice, reporting:

| Metric | Value |
|--------|------:|
| Accuracy | 0.899 |
| Precision | 0.883 |
| Recall | 0.971 |
| F1-score | 0.925 |
| ROC-AUC | 0.971 |

## Visualisations / Outputs
Refer to `covid-ct-classification.ipynb` for visualisations and outputs.

## Limitations
- The dataset is relatively small and based on public sources, which limits generalisability.
- The dataset lacks richer clinical context such as demographics, comorbidities, scanner differences, and site metadata.
- The CNN benchmark performance was weak compared with the classical baseline.
- The notebook mixes model benchmarking with exploratory business/triage analysis, so results should be interpreted cautiously.
- This project has **no external validation**, **no patient-level validation**, and should not be used for real clinical decision-making.

## Future Improvements
- Use a cleaner and fully consistent evaluation pipeline across all experiments.
- Test stronger transfer learning architectures such as **ResNet-18** or other medical-imaging-focused backbones in a controlled setup.
- Add k-fold cross-validation, external validation, and patient-level splitting.
- Improve augmentation, calibration, and threshold selection strategies.
- Refactor the notebook into reusable scripts with a `requirements.txt` file and clearer modular structure.
- Extend the work toward broader lung-disease classification or clinically relevant triage workflows.

## License
This repository is shared for portfolio purposes only.

Please do not copy, submit, or present this work as your own academic assignment.

## Contact
- **Name:** Ou Yang Yu
- **GitHub:** https://github.com/Gyres
- **Linktree:** https://linktr.ee/yuouyang
