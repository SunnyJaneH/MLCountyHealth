# Predictive Analysis of Food Desert Effects on Public Health Outcomes
**Quantifying Socioeconomic & Lifestyle Impacts on 2,275 US Counties**

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![ML-Framework](https://img.shields.io/badge/ML-Scikit--learn-F7931E.svg)](https://scikit-learn.org/)
[![Dashboard](https://img.shields.io/badge/Live_Demo-Streamlit-FF4B4B.svg)](https://streamlit.io/)

## 📌 Project Overview
Developed as a core component of the **DATA-245 Machine Learning** course at SJSU, this study investigates the correlation between "Food Deserts" (inequality in food access) and chronic health conditions like obesity and diabetes. By analyzing data from **2,275 US counties**, our team identified **261 "Crisis Counties"** where socioeconomic factors and food insecurity create urgent public health risks.

## 👤 My Core Contributions (Jane Heng)
I spearheaded the research and technical implementation detailed in **Pages 16-25** of the project report, focusing on high-stakes data engineering and regression modeling:

* **Robust Data Quality Engineering**:
    * **Outlier Management**: Identified and strategically managed **29% outliers**. I implemented rigorous normalization protocols over synthetic oversampling (SMOTE) to preserve the statistical integrity of the 2,275 county records.
    * **Feature Engineering**: Conducted multi-collinearity checks and recursive feature selection to refine 20+ variables into a high-impact predictor set.
* **Regression Benchmarking & Discovery**:
    * Implemented and evaluated **OLS, Ridge, and Lasso Regression** models.
    * **Major Scientific Finding**: My analysis revealed that **Insufficient Sleep** is a significantly stronger predictor of obesity and diabetes than the Food Environment Index. This "Lifestyle-First" insight shifted the project’s final policy recommendations.
* **Statistical Inference & Interpretability**:
    * Utilized **Standardized Coefficients** to quantify the marginal effects of income inequality and education on health risks, providing actionable insights for public health resource allocation.
* **Interactive Analytics**: Co-developed the **Streamlit Dashboard**, specifically engineering the PCA visualization and model comparison modules.



---

## 🛠 ML Pipeline & Workflow
The project follows a comprehensive data science lifecycle, from unsupervised profiling to supervised risk prediction:

1.  **Supervised Learning**: 
    * *Regression*: OLS, Ridge, Lasso (Focused on factor quantification).
    * *Classification*: Logistic Regression, SVM, Random Forest, Extra Trees (Focused on high-risk county identification).
2.  **Unsupervised Learning**: 
    * *Clustering*: **K-Means (k=5)** used to profile counties based on rurality and food access.
    * *Dimensionality Reduction*: **PCA** applied to identify the primary socioeconomic variance components.



---

## 📈 Key Research Insights (Based on Final Report)
* **The Sleep Paradox**: Insufficient sleep emerged as the top predictor for metabolic health outcomes (Ref: Report Page 22, 38).
* **Crisis Identification**: Successfully pinpointed **261 counties** requiring immediate intervention, supporting a data-driven approach to a **$500B+** healthcare market.
* **Model Optimization**: Regularized regression models achieved the best balance between predictive power (low MAE) and real-world interpretability.

---

## 📂 Project Structure
```text
├── dashboards/             # 8-page Streamlit application (Live demo logic)
├── src/analysis/           # Core Python scripts for Regression, PCA, and Clustering
├── notebooks/              # Data Cleaning pipeline and K-Means experimental logs
├── docs/reports/           # IEEE format technical paper and Final PDF Presentation
└── requirements.txt        # Reproducible Python environment (3.9+)

## 👥 Team: DATA-245 Fall 2025

* **Jane Heng** — *Lead: Data Quality Engineering, Regression Analysis, PCA & Streamlit Dashboard*
* **Savitha Vijayarangan** — *Lead: Classification Modeling & Feature Selection*
* **Kapil Reddy** — *Lead: Data Sourcing & Geographic Visualization*
* **Rishi Boppana** — *Lead: Clustering Analysis & Documentation*

## 🔧 Installation & Usage

### 1. Clone the Repository
```bash
git clone [https://github.com/SunnyJaneH/MLCountyHealth.git](https://github.com/SunnyJaneH/MLCountyHealth.git)
cd MLCountyHealth

### 2. Set Up Environment
# Create a virtual environment
python -m venv .venv

# Activate the environment
# On Windows:
.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate

# Install required dependencies
pip install -r requirements.txt

### 3. Run Analysis Scripts
# Execute Regression Analysis
python src/analysis/Regression_analysis.py

# Execute PCA Analysis
python src/analysis/pcaanalysis.py

### 4. Launch Interactive Dashboard
cd dashboards
streamlit run main_dashboard.py
