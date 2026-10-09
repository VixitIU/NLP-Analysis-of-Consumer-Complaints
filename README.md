# Topic Analysis of CFPB Student Loan Complaints

NLP analysis of unstructured consumer complaint texts — development phase of the course
**Project: Data Analysis (DLBDSEDA02)**, IU International University of Applied Sciences.

The project extracts the most frequently addressed topics from ~6,500 student-loan
complaint narratives submitted to the U.S. Consumer Financial Protection Bureau (CFPB)
between July 2025 and June 2026.

**Pipeline:** data loading → preprocessing (clean text) → vectorization (Bag of Words
and TF-IDF) → topic extraction (LSA and LDA) → validation against pre-labeled issue
categories.

**Libraries** (course curriculum only): `pandas`, `re`, `nltk`, `scikit-learn`.

## Repository structure

```
├── topic_analysis.ipynb   # the complete analysis (run top to bottom)
├── requirements.txt       # Python dependencies
├── data/complaints.csv    # the dataset (6,475 complaints)
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

The dataset is committed to the repository as `data/complaints.csv`: 6,475 student loan
complaints with a narrative, received between 2025-07-01 and 2026-06-30, exported from
the CFPB Consumer Complaint Database during the conception phase.

Note: since 14 August 2026 the CFPB no longer publishes complaint narratives, so the data
can no longer be downloaded from the CFPB website or API.

## Run the analysis

```bash
jupyter notebook topic_analysis.ipynb
```

Then run all cells (menu: *Run → Run All Cells*).

Tested with Python 3.13.9, `pandas` 3.0.5, `nltk` 3.10.3, `scikit-learn` 1.9.0.
