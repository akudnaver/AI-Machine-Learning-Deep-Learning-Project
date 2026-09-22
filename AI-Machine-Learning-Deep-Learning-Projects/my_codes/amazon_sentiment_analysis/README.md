# Amazon Sentiment Analysis

This project performs sentiment analysis on Amazon product reviews. It applies an LSTM model to the review text to predict review ratings and to surface positive and negative feedback trends across products.

## Goal

This dataset is a collection of customer feedback across Amazon-branded products. The idea is to gain insight into customer reviews for these products and identify areas for improvement.

## Project Structure

```
amazon_sentiment_analysis/
├── README.md
├── requirements.txt
├── amazon_sentimental_analysis_github.ipynb   # main notebook: EDA, preprocessing, LSTM model
└── review-details.xlsx                        # dataset (not included yet, see below)
```

## Prerequisites

- Python 3.9+
- pip
- Jupyter Notebook or JupyterLab

## Clone the Repository

```bash
git clone https://github.com/akudnaver/AI-Machine-Learning-Deep-Learning-Project.git
cd AI-Machine-Learning-Deep-Learning-Project/AI-Machine-Learning-Deep-Learning-Projects/my_codes/amazon_sentiment_analysis
```

## Setup

Create and activate a virtual environment, then install the dependencies:

```bash
python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

pip install -r requirements.txt
```

The notebook uses NLTK's stopword corpus, which needs to be downloaded once:

```bash
python -c "import nltk; nltk.download('stopwords'); nltk.download('wordnet')"
```

## Dataset

The notebook expects an Excel file named `review-details.xlsx` one directory above the notebook (i.e. in `my_codes/`).

> **Note:** The dataset is not yet included in this repository. It will be added later. Until then, the notebook cannot be run end-to-end — skip this step for now.

## How to Run

With the dataset in place, launch Jupyter and run the notebook top to bottom:

```bash
jupyter notebook amazon_sentimental_analysis_github.ipynb
```

The notebook will:
1. Load and clean the review data.
2. Explore review categories and rating distributions.
3. Preprocess review text (tokenization, stopword removal, stemming/lemmatization).
4. Vectorize text (Count/TF-IDF) and encode labels.
5. Train an LSTM model to classify/predict review ratings.
6. Evaluate the model (accuracy, classification report).

## How to Refactor

If you're extending or refactoring this project:

1. Create a feature branch: `git checkout -b feature/<your-change>`.
2. Keep data loading, preprocessing, model definition, and evaluation as separate, reusable functions/cells rather than inline script logic — this makes it easier to later extract them into standalone `.py` modules.
3. If you add new dependencies, update `requirements.txt`.
4. Re-run the full notebook to confirm it still executes cleanly end-to-end before committing.
5. Commit with a clear message describing the change, then open a pull request against `main`.

## Content

This dataset consists of the following columns:

```
['reportdate', 'onlinestore', 'upc', 'retailerproductcode', 'brand',
'category', 'subcategory', 'productdescription', 'reviewdate', 'reviewrating', 'reviewtitle', 'reviewtext', 'iscompetitor', 'manufacturer', 'market', 'matchedkeywords', 'timeofpublication',
'url', 'reviewtype', 'parentreview', 'manufacturersresponse', 'dimension1', 'dimension2', 'dimension3', 'dimension4', 'dimension5', 'dimension6', 'dimension7', 'dimension8', 'verifiedpurchase',
'helpfulreviewcount', 'reviewhashid']
```

## Acknowledgements

I would like to thank all the contributors to ML and the various channels through which they share their knowledge of CNN/LSTM/NLP technologies.

## Inspiration

Although I am aiming to achieve sentiment analysis from the reviews, the scope isn't limited to that. My initial goal was to work with this dataset to understand how well Amazon's products are performing and how we can improve their sales, but this approach can be applied across any industry depending on its business needs.

1. One of the things I am targeting next is improving my LSTM vocabulary to make the model more intelligent in capturing context across all the words when analyzing feedback.
2. Along with point one, I am also planning to create a model that can suggest the best solutions to improve sales.
3. The approaches and expectations discussed here can be leveraged in any field to improve business outcomes.
