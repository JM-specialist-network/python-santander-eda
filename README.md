# 🐍 Python – Santander Banking EDA (Exploratory Data Analysis)

This repository contains an exploratory data analysis (EDA) project on a real banking dataset from Santander, developed as part of a Master's degree in Data Science practical assignment.

Este repositorio contiene un proyecto de análisis exploratorio de datos (EDA) sobre un dataset bancario real de Santander, desarrollado como práctica de la asignatura de Máster en Ciencia de Datos.

---

## 📄 Files / Archivos

- `notebooks/Exploratorio_Santander_RED.ipynb` – Main Jupyter notebook with complete EDA workflow.  
- `data/` – Placeholder for dataset (not included due to size/privacy).

---

## 🎯 Objectives / Objetivos

- Understand the structure and quality of a real banking customer dataset (100,000 records, 49 variables).  
- Clean and transform data: handle missing values, type conversions, outlier detection.  
- Explore demographic patterns (age, gender, province distribution across Spain).  
- Analyse product adoption and customer segmentation (income, seniority, number of products).  
- Apply statistical techniques: descriptive statistics, confidence intervals, correlation analysis and clustering (K-Means).  
- Visualise distributions, relationships and clusters using Matplotlib and Seaborn.

- Comprender la estructura y calidad de un dataset bancario real de clientes (100.000 registros, 49 variables).  
- Limpiar y transformar datos: tratamiento de valores faltantes, conversión de tipos, detección de outliers.  
- Explorar patrones demográficos (edad, sexo, distribución provincial en España).  
- Analizar la adopción de productos y segmentación de clientes (renta, antigüedad, número de productos).  
- Aplicar técnicas estadísticas: estadísticos descriptivos, intervalos de confianza, análisis de correlaciones y clustering (K-Means).  
- Visualizar distribuciones, relaciones y clusters usando Matplotlib y Seaborn.

---

## 🧹 Main steps / Pasos principales

### 1. Data loading & initial exploration / Carga y exploración inicial

- Load CSV dataset with customer information and product indicators.  
- Identify data types, shape (100,000 rows × 49 columns) and missing values.  
- Review provincial distribution across Spain (52 unique provinces including autonomous cities).

### 2. Data cleaning / Limpieza de datos

- Convert variable types (e.g., `ind_viv_fin_ult1` to `float64`, `age` and `antiguedad` to numeric).  
- Handle missing values: replace "NA" strings with `np.NaN`, impute means where appropriate.  
- Correct errors: transform impossible values (e.g., seniority = 106 years → NaN).  
- Standardise categorical variables (e.g., unify gender codes).

### 3. Descriptive statistics / Estadística descriptiva

- Calculate mean, median, standard deviation, range, IQR, skewness and kurtosis for key variables (`age`, `renta`).  
- Detect outliers using pseudo-IQR method (percentiles 0.05 and 0.95 with 1.5×IQR thresholds).  
- Compute 95% confidence interval for average income using t-distribution.

### 4. Visualisation / Visualización

- Histograms and boxplots for age and income distributions.  
- Bar charts for client distribution by province (Madrid and Barcelona dominate).  
- Correlation heatmap between banking products (high correlation between payroll and pension products).  
- Scatter plots with linear regression (income vs number of products) and log-transformed axes.

### 5. Clustering & segmentation / Clustering y segmentación

- Apply K-Means clustering (k=3) on `age` and `renta` to identify customer segments.  
- Create derived variable `numero_productos` (sum of all contracted products per customer).  
- Visualise clusters in 2D scatter plots.

### 6. Statistical analysis / Análisis estadístico

- Correlation analysis between age and product adoption (strong positive correlation with deposit accounts and pension indicators, negative with current accounts).  
- Distribution fitting: income follows a log-normal distribution; number of products resembles a Poisson/negative binomial distribution.  
- Apply log and square-root transformations to reduce skewness.

---

## 🛠️ Tech stack / Tecnologías utilizadas

- **Python 3.x**  
- **Pandas** – Data manipulation and cleaning.  
- **NumPy** – Numerical operations and transformations.  
- **Matplotlib & Seaborn** – Data visualisation (histograms, boxplots, heatmaps, scatter plots).  
- **SciPy** – Statistical tests (skewness, kurtosis, t-distribution).  
- **scikit-learn** – K-Means clustering and train-test split.

---

## 🚀 How to run / Cómo ejecutar

1. Clone this repository:  

git clone https://github.com/JM-specialist-network/python-santander-eda.git
cd python-santander-eda

2. Install dependencies:  
pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter

3. Open the notebook:  
jupyter notebook notebooks/Exploratorio_Santander_RED.ipynb


4. Run all cells to reproduce the full EDA workflow.

> ⚠️ Note: The original dataset (`data_santander_red.csv`) is not included in this repository due to size and privacy considerations. The notebook includes all code and outputs for reference.

---

## 📊 Key findings / Hallazgos principales

- **Geographic concentration**: Madrid (16.1%) and Barcelona (11.1%) account for over a quarter of all customers.  
- **Age distribution**: Mean age ≈ 29 years, median 25, with positive skew (younger population dominant).  
- **Income**: Log-normal distribution with mean ≈115,559 €, high variance and outliers above 600,000 €.  
- **Product adoption**: Strong correlation between age and certain products (deposit accounts, pension plans); younger customers prefer current accounts.  
- **Customer segments**: K-Means clustering reveals three main groups based on age and income, with relatively uniform income distribution across age brackets (20–40 years).[web:2]

---

## 👤 Author / Autor

Created by **Jose Miguel Artiles** – Data Scientist & Economist-in-training.  

- GitHub: [JM-specialist-network](https://github.com/JM-specialist-network)  
- Email: joseartiles@g***l.com
