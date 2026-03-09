# NLP Analysis of Annual Report vs. Marketing Brochure

This project applies natural language processing (NLP) techniques to compare an Annual Report and a Marketing Brochure, with the goal of assessing how consistently a company communicates its priorities across different business documents. The analysis focuses on semantic similarity, key concept extraction, named entities, topics, sentiment, and business interpretation.

## Project Overview
- **Institution:** Singapore University of Social Sciences (SUSS)
- **Project Type:** Group
- **Submission Date:** Jan 2025
- **Status:** Completed

## Problem Statement
Organizations often communicate with different audiences through different document types, such as annual reports and marketing brochures. If those documents are inconsistent in language, emphasis, or tone, stakeholders may receive mixed signals about the company’s priorities and identity. This project uses NLP to evaluate whether the two documents are aligned in messaging and to extract insights that support stronger business communication strategy.

## Objectives
- Compare the semantic similarity between an Annual Report and a Marketing Brochure.
- Extract shared and unique keywords, entities, and topics from both documents.
- Interpret how the findings support communication consistency, branding, and stakeholder trust.

## Dataset

### Source
- Two business text documents used in the assignment:
  - **Annual Report**
  - **Marketing Brochure**

### Description
- **Number of documents:** 2
- **Number of features/classes:** Not applicable
- **Target variable:** None
- **Data type:** Text
- **Task type:** Unsupervised / exploratory NLP analysis

### Notes
- This is a small-scale document comparison task rather than a large labeled NLP dataset.
- The project is designed to demonstrate an end-to-end NLP workflow for business communication analysis.
- Findings are interpretive and intended to support communication auditing rather than prediction.

## Tools and Technologies
- **Programming Language:** Python
- **Environment:** Jupyter Notebook
- **Libraries / Frameworks:** NLTK, spaCy, scikit-learn, PyTorch, Hugging Face Transformers
- **Techniques / Models:** Regex cleaning, tokenization, lemmatization, stopword removal, DistilBERT embeddings, TF-IDF, Named Entity Recognition (NER), K-Means clustering, LDA, NMF, transformer-based sentiment analysis
- **Other Tools:** Git, GitHub

## Methodology
1. Prepare and preprocess the Annual Report and Marketing Brochure text using cleaning, tokenization, lemmatization, and stopword removal.
2. Generate vector representations using DistilBERT embeddings.
3. Measure semantic alignment using cosine similarity and Euclidean distance.
4. Extract common and unique terms using TF-IDF.
5. Identify important entities using spaCy and compare outputs from multiple pre-trained NER models.
6. Group semantic patterns with K-Means clustering.
7. Discover recurring themes using LDA and NMF topic modeling.
8. Evaluate overall tone using transformer-based sentiment analysis.
9. Interpret the outputs from a business communication perspective.

## Repository Structure
```text
school-assessments/
└── nlp-annual-report-brochure/
    ├── nlp-annual-report-brochure.ipynb   # Main notebook containing the NLP workflow
    └── README.md                          # Project documentation
```

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Gyres/school-assessments.git
   ```
2. Open the project folder:
   ```bash
   cd school-assessments/nlp-annual-report-brochure
   ```
3. Install the required dependencies:
   ```bash
   pip install nltk spacy scikit-learn torch transformers
   ```
4. Download the English spaCy model if needed:
   ```bash
   python -m spacy download en_core_web_sm
   ```
5. Launch Jupyter Notebook and open:
   ```bash
   jupyter notebook
   ```
6. Run `nlp-annual-report-brochure.ipynb` cells to reproduce the preprocessing, similarity analysis, topic modeling, NER, clustering, sentiment analysis, and business interpretation.

## Results

### Key Findings
- The two documents show **strong semantic alignment**, indicating cohesive messaging across internal and external communication.
- The **cosine similarity score is 0.96**, suggesting substantial conceptual overlap between the documents.
- Shared recurring themes include **sustainability, innovation, digital transformation, operational efficiency, and growth**.
- TF-IDF highlights overlapping priorities while also showing audience-specific emphasis: the Annual Report is more strategy/performance-oriented, while the Brochure emphasizes innovation and customer-facing messaging.
- Common entities include **2023, 10%, 25%, Company, and NextUs**.

### Performance Metrics
| Metric | Value |
|--------|------:|
| Cosine Similarity | 0.96 |
| Optimal K-Means Clusters | 5 |
| Number of Documents | 2 |
| Topic Modeling Methods | 2 (LDA, NMF) |

## Visualisations / Outputs
Refer to `nlp-annual-report-brochure.ipynb` for visualisations and outputs.

## Limitations
- The analysis is based on only **two documents**, so findings are not broadly generalizable.
- High similarity scores may mask subtle differences in tone, emphasis, or audience targeting.
- TF-IDF may miss important multi-word business phrases if tokenization is limited.
- High-level sentiment analysis can overlook nuanced concerns, risks, or criticisms.

## Future Improvements
- Expand the analysis to more corporate communication documents, such as sustainability reports, press releases, and investor presentations.
- Use aspect-based or domain-specific sentiment analysis for deeper business insight.
- Improve phrase-level extraction for multi-word business concepts.
- Build an automated communication-audit workflow for ongoing message consistency monitoring.

## License
This repository is shared for portfolio purposes only.

Please do not copy or submit this work as your own academic assignment.

## Contact
- **Name:** Ou Yang Yu
- **GitHub:** https://github.com/Gyres
- **Linktree:** https://linktr.ee/yuouyang
