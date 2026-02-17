# Python Salary Analysis (NoFluffJobs)

## 📌 Project Goal

**Celem projektu jest analiza oraz predykcja wynagrodzeń programistów Python w Polsce na podstawie ofert pracy z jawnymi widełkami płacowymi.**

Projekt obejmuje pełny pipeline Data Science:

- Pozyskanie danych z REST API  
- Czyszczenie i deduplikację danych  
- Analizę eksploracyjną (EDA)  
- Feature engineering  
- Budowę i ewaluację modelu regresyjnego  

---

## 📊 Data Source

**Źródło danych:**
- NoFluffJobs REST API  
- Fraza wyszukiwania: `"python"`  
- Region: Poland  
- Waluta: PLN  
- Okres wynagrodzenia: monthly  

**Zakres danych:**
- `title`
- `city`
- `level` (seniority)
- `salary_from`
- `salary_to`
- `salary_avg`
- `currency`

Analiza obejmuje wyłącznie oferty zawierające jawne widełki płacowe.

---

## 🧹 Data Processing Pipeline

1. Scrapowanie danych z API  
2. Usunięcie duplikatów ofert  
3. Filtrowanie rekordów bez widełek wynagrodzenia  
4. Obliczenie `salary_avg`  
5. Kodowanie zmiennych kategorycznych (One-Hot Encoding)  
6. Przygotowanie zbiorów `X` (features) i `y` (target)  

---

## 📈 Exploratory Data Analysis (EDA)

**Kluczowe obserwacje:**

- Wynagrodzenia rosną wraz z poziomem doświadczenia  
- Segment Senior charakteryzuje się największym rozrzutem widełek płacowych  
- Oferty z jawnymi widełkami dotyczą głównie poziomów Mid i Senior  
- Rynek Juniorów jest słabo reprezentowany w ofertach z widełkami  
- Dominują oferty zdalne (Remote/Unknown)  

Notebook:  
`notebooks/03_eda_salary.ipynb`

---

## 🤖 Machine Learning

**Cel modelu:**  
Predykcja średniego wynagrodzenia (`salary_avg`) na podstawie cech oferty.

**Zastosowany model:**
- Random Forest Regressor

**Metody ewaluacji:**
- Train/Test Split  
- R² Score  
- MAE (Mean Absolute Error)  
- RMSE (Root Mean Squared Error)  

Notebook:  
`notebooks/04_ml_salary_models.ipynb`

---

## 📁 Project Structure

analiza-rynku-pracy-ml/
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
cd analiza-rynku-pracy-ml


2. Create virtual environment:

python -m venv .venv
source .venv/bin/activate


3. Install dependencies:
pip install -r requirements.txt

4. Run Jupyter Notebook:
jupyter notebook 


---

## ⚠️ Limitations

- Analiza obejmuje wyłącznie oferty z jawnymi widełkami płacowymi  
- Dane reprezentują wycinek rynku w określonym momencie czasowym  
- Brak informacji o rodzaju kontraktu (B2B / UoP), stacku technologicznym, benefitach  
- Duża część ofert oznaczona jako Remote/Unknown  

---

## 🔮 Future Improvements

- Uwzględnienie większej liczby stron (większy zbiór danych)  
- Dodanie analizy stacków technologicznych  
- Porównanie różnych modeli regresyjnych  
- Cross-validation  
- Deployment modelu jako API  




