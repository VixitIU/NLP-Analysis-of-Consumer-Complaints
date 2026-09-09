# Topic Analysis of CFPB Student Loan Complaints

NLP analysis of unstructured consumer complaint texts — development phase of the course
**Project: Data Analysis (DLBDSEDA02)**, IU International University of Applied Sciences.

The project extracts the most frequently addressed topics from ~6,500 student-loan
complaint narratives submitted to the U.S. Consumer Financial Protection Bureau (CFPB)
between July 2025 and June 2026, as a structural analogue to citizen complaints received
by a municipality.

**Pipeline:** data loading → preprocessing (clean text) → vectorization (Bag of Words
and TF-IDF) → topic extraction (LSA and LDA) → validation against pre-labeled issue
categories.

**Libraries** (course curriculum only): `pandas`, `re`, `nltk`, `scikit-learn`.

## Repository structure

```
├── topic_analysis.ipynb   # the complete analysis (run top to bottom)
├── requirements.txt       # Python dependencies
├── data/                  # dataset location (CSV not committed, see below)
└── README.md
```

## Setup

Requires Python 3.10 or newer.

```bash
# 1. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate          # Windows
source venv/bin/activate       # macOS / Linux

# 2. Install the dependencies
pip install -r requirements.txt
```

## Data

The dataset is **not** committed to the repository. Two options:

1. **Automatic (default):** simply run the notebook. If `data/complaints.csv` does not
   exist, it is downloaded once from the official CFPB complaint-search API with the
   filters *product = Student loan*, *narratives only*, *received 2025-07-01 to
   2026-06-30*, and saved locally.
2. **Manual:** on [consumerfinance.gov/data-research/consumer-complaints/search](https://www.consumerfinance.gov/data-research/consumer-complaints/search/),
   set the same filters, export as CSV and save the file as `data/complaints.csv`.

Note: narratives are published with a delay, so a fresh download may contain slightly
more records than the 6,475 available at the time of the conception phase.

## Run the analysis

```bash
jupyter notebook topic_analysis.ipynb
```

Then run all cells (menu: *Run → Run All Cells*). The full run takes a few minutes;
the preprocessing cell is the slowest. NLTK downloads its language resources
(tokenizer, stop words, WordNet) automatically on the first run.

Tested with Python 3.12, `pandas` 3.0.2, `nltk` 3.10.3, `scikit-learn` 1.8.0.
