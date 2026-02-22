# Python Salary Analysis (NoFluffJobs)

## 📌 Project Goal

**The aim of the project is to analyse and predict the salaries of Python programmers in Poland based on job offers with disclosed salary ranges.**

The project covers the full Data Science pipeline:

- Data acquisition from REST API  
- Data cleaning and deduplication  
- Exploratory data analysis (EDA)  
- Feature engineering  
- Regression model building and evaluation  

---

## 📊 Data Source

**Data source:**
- NoFluffJobs REST API  
- Search phrase: `‘python’`  
- Region: Poland  
- Currency: PLN  
- Salary period: monthly  

**Data scope:**
- `title`
- `city`
- `level` (seniority)
- `salary_from`
- `salary_to`
- `salary_avg`
- `currency`

The analysis only includes offers with explicit salary ranges.

---

## 🧹 Data Processing Pipeline

1. Scraping data from the API  
2. Removing duplicate offers  
3. Filtering records without salary ranges  
4. Calculating `salary_avg`  
5. Encoding categorical variables (One-Hot Encoding)  
6. Preparing sets `X` (features) and `y` (target)  

---

## 📈 Exploratory Data Analysis (EDA)

**Key observations:**

- Salaries increase with experience  
- The Senior segment is characterised by the widest salary range  
- Offers with explicit salary ranges mainly concern Mid and Senior levels  
- The Junior market is poorly represented in offers with salary ranges  
- Remote offers (Remote/Unknown) dominate  

Notebook:  
`notebooks/03_eda_sala

---

## 🤖 Machine Learning

**Model objective:**  
Predicting average salary (`salary_avg`) based on job offer characteristics.

**Model used:**
- Random Forest Regressor

**Evaluation methods:**
- Train/Test Split  
- R² Score  
- MAE (Mean Absolute Error)  
- RMSE (Root Mean Squared Error)  

Notebook:  
`notebooks/04_ml_salary_models.ipynb`

---

## 📁 Project Structure

labour-market-analysis-ml/
│
├── data/
│ ├── nfj_jobs_clean.csv
│ ├── nfj_jobs_features.csv
│ ├── X_features.csv
│ └── y_target.csv
│
├── notebooks/
│ ├── 03_eda_salary.ipynb
│ └── 04_ml_salary_models.ipynb
│
├── requirements.txt
└── README.md


---

## 🚀 How to Run

1. Clone repository:

git clone https://github.com/RafalRucki/analiza-rynku-pracy-ml.git
cd labour-market-analysis-ml


2. Create virtual environment:

python -m venv .venv
source .venv/bin/activate


3. Install dependencies:
pip install -r requirements.txt

4. Run Jupyter Notebook:
jupyter notebook 


---

## ⚠️ Limitations

- The analysis only includes offers with explicit salary ranges
- The data represents a snapshot of the market at a specific point in time
- No information about the type of contract (B2B/UoP), technology stack, or benefits  
- A large proportion of offers marked as Remote/Unknown  

---

## 🔮 Future Improvements

- Inclusion of more websites (larger data set)  
- Addition of technology stack analysis  
- Comparison of different regression models  
- Cross-validation  
- Deployment of the model as an API  




