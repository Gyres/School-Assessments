# NLP Analysis of SROI Reports

This project applies Natural Language Processing (NLP) to analyse Social Return on Investment (SROI) reports and compare how key impact-adjustment factors are discussed across documents. It automates text extraction, preprocessing, keyword-based factor identification, sentiment analysis, topic exploration, and comparative reporting to support a more systematic and scalable review of social value reports.

## Project Overview
- **Institution:** Singapore University of Social Sciences (SUSS)
- **Project Type:** Individual
- **Academic Term:** Jan 2025
- **Status:** Completed

## Problem Statement
Manual review of SROI reports is time-consuming and difficult to scale, especially when analysts need to compare how key impact-adjustment factors such as **deadweight**, **displacement**, **attribution**, and **drop-off** are reported across multiple documents. This project addresses that challenge by building an NLP workflow to automatically extract, quantify, and compare these factors from textual SROI reports, improving efficiency, consistency, and transparency in social impact analysis.

## Objectives
- Build an NLP pipeline to extract and preprocess text from multiple SROI report PDFs.
- Identify and compare the frequency of key impact factors: deadweight, displacement, attribution, and drop-off.
- Extract reported SROI values and explore relationships between report content, sentiment, and impact-factor reporting.

## Dataset
### Source
- Five Social Return on Investment (SROI) reports provided as PDF documents.

### Description
- **Number of files:** 5 PDF reports
- **Primary features:** Raw text, cleaned text, tokens, word counts, sentiment scores, TF-IDF features, named entities
- **Target variables / extracted variables:** Impact factor mentions (deadweight, displacement, attribution, drop-off) and reported SROI metric
- **Data type:** Text documents (PDF reports)

### Reports Analysed
- CTBC Baseball Sponsorship Report
- CTBC Foundation for Arts and Culture Report
- Six-Level Redevelopment Project for Traditional Fishing Villages Report
- Type 2 Diabetes Prevention and Management Programme Report
- Food for Life Report

### Notes
- The dataset is small and document-based, consisting of only five reports.
- Extraction quality depends on the text readability and formatting consistency of the source PDFs.
- Impact-factor detection in the current implementation relies mainly on keyword and regular-expression matching, so semantically similar phrasing may be missed.

## Tools and Technologies
- **Programming Language:** Python
- **Environment:** Jupyter Notebook
- **Libraries / Frameworks:** PyPDF2, NLTK, pandas, NumPy, matplotlib, seaborn, scikit-learn, spaCy, transformers
- **Other Tools:** Git, GitHub

## Methodology
1. Extract raw text from SROI report PDFs using `PyPDF2`.
2. Clean and preprocess the text through lowercasing, punctuation removal, tokenization, and stop-word removal.
3. Use regular expressions to extract reported SROI values and count mentions of deadweight, displacement, attribution, and drop-off.
4. Generate document-level features such as word counts, TF-IDF vectors, sentiment scores, and named-entity summaries.
5. Explore document structure and relationships using Truncated SVD, NMF topic modelling, cosine similarity, correlation analysis, and visualisations.

## Repository Structure
```text
school-assessments/
└── nlp-sroi-reports/
    ├── nlp-sroi-reports.ipynb              # Main notebook for preprocessing, analysis, and visualisation
    ├── data/                               # Source SROI PDF reports
    └── README.md                           # Project documentation
```

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Gyres/school-assessments.git
   ```
2. Navigate to the project folder:
   ```bash
   cd school-assessments/nlp-sroi-reports
   ```
3. Install the required Python libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn nltk scikit-learn PyPDF2 spacy transformers torch
   ```
4. Download the required NLP resources if prompted by the notebook:
   - NLTK resources: `punkt`, `stopwords`, `wordnet`, `vader_lexicon`
   - spaCy model: `en_core_web_lg`
5. Ensure the SROI PDF files are placed inside the `data/` folder.
6. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
7. Open and run `nlp-sroi-reports.ipynb` in Jupyter Notebook.

## Results
### Key Findings
- The project successfully extracted and compared key impact-factor mentions across five SROI reports.
- **Deadweight** and **attribution** appeared frequently across most reports, while **drop-off** was explicitly identified only in the Fishing Village Report.
- The extracted SROI values varied substantially across reports, with the Baseball Sponsorship Report showing the highest reported SROI.
- A moderate positive correlation was observed between total impact-factor mention count and the reported SROI metric, suggesting that reports with more discussion of adjustment factors may also report higher SROI values.

### Analytical Outputs
| Metric | Value |
|--------|------:|
| Number of SROI reports analysed | 5 |
| TF-IDF feature space | 1000 features |
| Reduced TF-IDF dimensions | 2 components |
| Highest extracted SROI value | 17.59 |
| Lowest extracted SROI value | 1.91 |
| Correlation: total impact-factor count vs SROI | 0.49 |

### Extracted SROI Metrics
| Report | SROI |
|--------|-----:|
| Baseball Sponsorship Report | 17.59 |
| Arts & Culture Report | 4.18 |
| Fishing Village Report | 1.91 |
| Diabetes Prevention Report | 5.80 |
| Food for Life Report | 4.40 |

### Impact Factor Counts
| Report | Deadweight | Displacement | Attribution | Drop-off |
|--------|-----------:|-------------:|------------:|---------:|
| Baseball Sponsorship Report | 30 | 15 | 31 | 0 |
| Arts & Culture Report | 40 | 8 | 35 | 0 |
| Fishing Village Report | 15 | 6 | 13 | 16 |
| Diabetes Prevention Report | 26 | 9 | 21 | 0 |
| Food for Life Report | 20 | 18 | 20 | 0 |

## Visualisations / Outputs
Refer to `nlp-sroi-reports.ipynb` for visualisations and outputs.

## Limitations
- The corpus is small, with only five reports, limiting generalisability.
- Keyword and regex-based extraction may miss implicit, paraphrased, or context-dependent mentions of impact factors.
- SROI metric extraction assumes relatively consistent report formatting and may require adjustment for other document styles.
- Sentiment analysis provides supplementary insight, but its practical relevance to SROI interpretation is limited and may not directly reflect methodological quality.

## Future Improvements
- Replace simple keyword matching with more advanced semantic NLP methods such as NER, relation extraction, or embedding-based search.
- Expand the dataset to include a larger and more diverse set of SROI reports for stronger comparative analysis.
- Build a more robust extraction module that can handle varied SROI formatting and terminology.
- Develop an interactive dashboard or reporting interface for stakeholders to explore report comparisons visually.

## License
This repository is shared for portfolio purposes only.

Please do not copy, reproduce, or submit this work as your own academic assignment.

## Contact
- **Name:** Ou Yang Yu
- **GitHub:** https://github.com/Gyres
- **Linktree:** https://linktr.ee/yuouyang
