# EPL Match Winner Predictor

## Overview

This project focuses on predicting the winner of a particular premier league match using machine learning. A **Random Forest classifier** is trained to predict whether a team wins a match based on factors such as match context and recent team performance. The project involves feature engineering, baseline modeling, evaluation, and iterative improvement.

---

## Dataset

**Notes on data completeness:**

* Some matches are missing due to mid-season scraping
* Promoted and relegated teams naturally have fewer matches
* One full season of matches is missing for Liverpool

---

## Data Preparation

Key preprocessing steps include:

* Converting date strings to datetime format
* Inspecting missing and inconsistent records
* Validating match counts by team and matchweek

---

## Feature Engineering

Several features were engineered to make the data suitable for modeling:

* **Venue encoding** (home vs away)
* **Opponent encoding** (categorical team IDs)
* **Target variable**:

  * Win = 1
  * Draw / Loss = 0

### Rolling Averages

To capture short-term team form, rolling averages over the **previous 3 matches** were calculated for:

* Goals for / against
* Shots & shots on target
* Shot distance
* Free kicks, penalties, and penalty attempts

---

## Modeling Approach

### Baseline Model

* **Model:** Random Forest Classifier
* **Accuracy:** ~61%
* **Precision:** ~47%

### Improved Model

After adding rolling-average features:

* **Accuracy:** ~66%
* **Precision:** ~62.5%

---

## Code

**File overview:**

* `matches.ipynb` – Data cleaning, feature engineering, rolling averages, model training, and evaluation
* `matches.csv` – Scraped EPL match data used for training and testing

---

## Technologies Used

* Python
* pandas & NumPy
* scikit-learn
* Matplotlib
* Jupyter Notebook
