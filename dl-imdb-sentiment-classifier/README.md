# IMDB Sentiment Classifier with Wide & Deep Neural Networks

An end-to-end deep learning project for binary sentiment classification on IMDB movie reviews using a Wide + Deep multilayer perceptron in PyTorch. The pipeline covers data preparation, model training, evaluation, business interpretation, and deployment-oriented enhancements such as temperature scaling and dynamic quantisation.

## Project Overview
- **Institution:** Singapore University of Social Sciences (SUSS)
- **Project Type:** Individual
- **Academic Term:** Jul 2025
- **Status:** Completed

## Problem Statement
Sentiment analysis helps organisations automatically classify text feedback at scale, reducing manual review effort and improving responsiveness. This project builds a deep learning classifier to predict whether an IMDB movie review is positive or negative using a high-dimensional sparse bag-of-words representation, while also evaluating model reliability, business value, and deployment readiness.

## Objectives
- Build a robust deep learning pipeline for binary sentiment classification on IMDB reviews.
- Evaluate the model using discrimination, threshold-based, and calibration metrics.
- Interpret the model from an operational and business perspective, and propose practical deployment improvements.

## Dataset

### Source
- IMDB movie reviews dataset provided in CSV format for coursework use (`IMDB Movies.csv`).

### Description
- **Number of rows:** 10,000 original reviews
- **Rows after de-duplication:** 9,984
- **Number of features:** 5,000 binary input features originally, reduced to 4,997 after removing zero-variance features
- **Target variable:** Binary sentiment label (`0 = negative`, `1 = positive`)
- **Data type:** Text represented as tabular sparse bag-of-words / one-hot encoded features

### Notes
- 16 duplicate rows were removed.
- 3 constant features were removed.
- The class distribution is approximately balanced at about 50.2% positive.
- The dataset was split using stratified sampling into train (70%), validation (15%), and test (15%) sets.
- The notebook expects `IMDB Movies.csv` to be available in the project root before execution.

## Tools and Technologies
- **Programming Language:** Python
- **Environment:** Jupyter Notebook
- **Libraries / Frameworks:** PyTorch, scikit-learn, pandas, numpy, matplotlib, IPython
- **Other Tools:** Git, GitHub

## Methodology
1. Load and audit the IMDB dataset from CSV.
2. Remove duplicate rows and zero-variance features to reduce redundancy and noise.
3. Perform stratified train/validation/test splitting and convert data into PyTorch tensors and DataLoaders.
4. Build and train a Wide + Deep MLP with a linear wide branch and a deep branch using ReLU, dropout, AdamW, learning-rate scheduling, and early stopping.
5. Tune hyperparameters with random search across dropout, learning rate, weight decay, batch size, and training settings.
6. Evaluate the model using AUROC, Average Precision, Accuracy, Precision, Recall, F1-score, Balanced Accuracy, Brier Score, and calibration analysis.
7. Interpret results from a business perspective using threshold tuning, confusion matrix outcomes, and capacity-limited targeting.
8. Improve deployment readiness through temperature scaling and dynamic quantisation.

## Repository Structure
```text
school-assessments/
└── dl-imdb-sentiment-classifier/
    ├── imdb_sentiment_nn_pipeline.ipynb      # Main notebook for the full pipeline
    ├── requirements.txt                      # Python dependencies
    ├── IMDB Movies.csv                       # Dataset file (file too big to be uploaded on GitHub)
    └── README.md
```

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Gyres/school-assessments.git
   cd school-assessments/dl-imdb-sentiment-classifier
   ```

2. Ensure the dataset file is available in the project folder:
   ```text
   IMDB Movies.csv
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Launch Jupyter Notebook and open:
   ```bash
   jupyter notebook
   ```

5. Run the notebook `imdb_sentiment_nn_pipeline.ipynb` cells sequentially to preprocess the data, train and tune the model, evaluate performance, and generate figures and saved artifacts.

## Results

### Key Findings
- The Wide + Deep model achieved strong classification performance on the IMDB sentiment task, with test AUROC of about 0.945 and Average Precision of about 0.943.
- At the tuned threshold of approximately 0.57, the model achieved a strong balance between precision and recall, with F1-score around 0.883 and recall around 0.910.
- Dynamic quantisation reduced model size from 20.55 MB to 5.15 MB with negligible AUROC loss, improving deployment efficiency.
- Temperature scaling slightly improved calibration while preserving predictive performance.
- In a capacity-limited scenario, the top 10% highest-scoring reviews achieved 100% precision, showing strong triage value.

### Performance Metrics
| Metric | Value |
|--------|------:|
| AUROC | 0.945 |
| Average Precision | 0.943 |
| Accuracy | 0.879 |
| Precision | 0.857 |
| Recall | 0.910 |
| F1-score | 0.883 |
| Balanced Accuracy | 0.878 |
| Brier Score | 0.097 |
| ECE@10 | 0.056 |
| Tuned Threshold | 0.57 |

## Visualisations / Outputs
Refer to `imdb_sentiment_nn_pipeline.ipynb` for visualisations and outputs.

## Limitations
- The model uses one-hot bag-of-words features, so it does not capture word order or richer contextual semantics.
- Some overfitting risk remains despite dropout, weight decay, and early stopping.
- Probability calibration is acceptable but not perfect, requiring monitoring in production.
- Threshold performance depends on business cost trade-offs and may shift over time as data changes.

## Future Improvements
- Use contextual text representations such as word embeddings or transformer-based models.
- Add explainability techniques such as SHAP or integrated gradients for more interpretable predictions.
- Explore knowledge distillation to create a smaller deployment-friendly student model.
- Strengthen monitoring for calibration drift, threshold drift, fairness, and data distribution shift.

## License
This repository is shared for portfolio purposes only.

Please do not copy, reuse, or submit this work as your own academic assignment.

## Contact
- **Name:** Ou Yang Yu
- **GitHub:** https://github.com/Gyres
- **Linktree:** https://linktr.ee/yuouyang
