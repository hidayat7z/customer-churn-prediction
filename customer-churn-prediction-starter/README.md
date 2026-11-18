# Customer Churn Prediction Using Machine Learning

A machine learning project that explores customer churn in the telecommunications industry using customer account, demographic, and service data. The project covers data preprocessing, exploratory data analysis, class-imbalance handling, model training, and performance evaluation.

## Project Overview

Customer churn occurs when a customer stops using a company's services. Predicting which customers are likely to leave can help businesses better understand churn patterns and make informed customer-retention decisions.

This project uses the **Telco Customer Churn** dataset from Kaggle, containing **7,043 customer records and 21 attributes**. The target variable is `Churn`, which indicates whether a customer left the service.

## Objectives

- Explore customer, account, and service attributes associated with churn.
- Prepare and transform the dataset for machine learning.
- Address class imbalance before model training.
- Train and compare classification models.
- Evaluate model performance using accuracy, precision, recall, and F1-score.

## Dataset

- **Source:** [Telco Customer Churn - Kaggle](https://www.kaggle.com/blastchar/telco-customer-churn)
- **Records:** 7,043 customers
- **Attributes:** 21
- **Target:** `Churn` (`Yes` / `No`)

The dataset includes customer demographics, subscribed services, account information, contract details, payment methods, and charges.

The dataset is not included in this repository. See [`data/README.md`](data/README.md) for instructions on obtaining and placing it locally.

## Methodology

1. **Data preparation:** Converted `TotalCharges` to a numeric field, handled 11 missing `TotalCharges` records, created tenure groups, removed the `customerID` and original `tenure` fields used during feature preparation, and encoded the target and categorical variables.
2. **Exploratory data analysis:** Examined customer characteristics, service usage, charges, and relationships between features and churn.
3. **Class-imbalance handling:** Split the data into training and test sets using an 80:20 split while preserving the original class proportions. Applied SMOTEENN to the training data to address class imbalance.
4. **Model training:** Trained and compared three supervised classification models.
5. **Evaluation:** Compared the models using accuracy, precision, recall, and F1-score.

## Models Compared

- Decision Tree Classifier
- Random Forest Classifier
- Gaussian Naive Bayes Classifier

## Results

The following results are taken from the project's final-year report:

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Decision Tree | 93.0% | 95.6% | 92.2% | 93.8% |
| Random Forest | **93.1%** | 92.5% | **95.8%** | **94.1%** |
| Gaussian Naive Bayes | 90.4% | 91.3% | 92.1% | 91.7% |

The Random Forest classifier achieved the highest reported recall and F1-score, making it the strongest-performing model in this project based on the selected evaluation metrics.

## Tech Stack

- **Language:** Python
- **Data handling:** NumPy, Pandas
- **Visualization:** Matplotlib, Seaborn, Plotly
- **Machine learning:** scikit-learn
- **Imbalance handling:** SMOTEENN (commonly provided by imbalanced-learn)
- **Environment:** Jupyter Notebook

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/customer-churn-prediction.git
cd customer-churn-prediction
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

 macOS / Linux:

```bash
source .venv/bin/activate
```

Windows:

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the dataset

Download the dataset from Kaggle and place the CSV file in `data/raw/`. Update the file path in the notebook or script if the downloaded filename differs from the path used by the code.

### 5. Run the analysis

Place the project notebook in `notebooks/`, then launch Jupyter:

```bash
jupyter notebook
```

> **Repository note:** This starter README and folder structure are prepared from the submitted project report. Add the original Jupyter notebook or Python source files before presenting the repository as an executable, reproducible implementation. The report does not specify exact package versions, so the dependency list is unpinned.

## Project Structure

```text
customer-churn-prediction/
├── data/
│   ├── raw/                  # Downloaded dataset (not committed)
│   └── README.md             # Dataset source and setup instructions
├── notebooks/
│   └── README.md             # Place the analysis notebook here
├── results/
│   └── README.md             # Place generated charts and result exports here
├── .gitignore
├── requirements.txt
└── README.md
```

## Team and Acknowledgements

This was a group academic project completed as part of the B.Tech in Computer Science and Engineering at MCKV Institute of Engineering, affiliated with Maulana Abul Kalam Azad University of Technology.

**Project contributors:**
- Md Hidayat Rasool
- Sk Ezaz Ahamed
- Syed Shalish Raza
- Md Seraj Khan
- Pushpak Damani

**Project guide:** Ms. Soma Bandyopadhyay

## Future Scope

The project report identifies further model comparisons, implementing selected algorithms from scratch, and developing a web interface for visualizing the results as possible future improvements.
