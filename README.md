# Predictive Analysis of Food Desert Effects on Public Health Outcomes
**Quantifying Socioeconomic & Lifestyle Impacts on 2,275 US Counties**

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![ML-Framework](https://img.shields.io/badge/ML-Scikit--learn-F7931E.svg)](https://scikit-learn.org/)
[![Dashboard](https://img.shields.io/badge/Live_Demo-Streamlit-FF4B4B.svg)](https://streamlit.io/)

## 📌 Project Overview
Developed as a core component of the **DATA-245 Machine Learning** course at SJSU, this study investigates the correlation between "Food Deserts" (inequality in food access) and chronic health conditions like obesity and diabetes. By analyzing data from **2,275 US counties**, our team identified **261 "Crisis Counties"** where socioeconomic factors and food insecurity create urgent public health risks.

## 👤 My Core Contributions (Jane Heng)
I led the **Advanced Optimization & Feature Interpretation** phase (Pages 16-25), transitioning the project from a failed baseline to a robust predictive model with high interpretability.

### 🏆 1. Feature Importance & Hypothesis Validation 
*This is the core discovery: proving that food access is a unique, independent driver of health outcomes.*

![Feature Importance](docs/images/feature_importance.jpg)

* **Research Validation**: Proved that `Food_Access_Barrier_Index` is the **#3 most influential factor** (~12.2%), maintaining its impact even after controlling for income and education.
* **Key Insight**: Validated that food deserts are not merely proxies for poverty but require independent policy interventions.

---

### 🛠️ 2. Iterative Model Optimization
*I spearheaded a four-stage refinement process to overcome initial model failure.*

![Optimization Pipeline](docs/images/optimization_pipeline.jpg)

* **Problem Formulation**: Identified flaws in the initial "Three-Class Baseline" (55% accuracy) and reformulated the task into a more robust binary classification.
* **Performance Jump**: Achieved a progressive refinement in accuracy from **55% → 68.11%**.

---

### 🔬 3. Advanced Noise Filtering with DBSCAN 
*Utilized unsupervised learning to handle spatial data irregularities.*

![DBSCAN PCA Visualization](docs/images/dbscan_pca.jpg)

* **DBSCAN Implementation**: Used density-based clustering to isolate 46 high-leverage outliers (2.94% of data) through PCA-reduced spatial analysis.
* **Algorithmic Edge**: This precision cleaning enabled **Extra Trees** to reach its peak performance with a **2.52x training speedup**.

---

### 📊 4. Model Evaluation & Error Analysis
*Ensuring the model's reliability for public health decision-making.*

![Confusion Matrix](docs/images/confusion_matrix.jpg)

* **Metrics**: Leveraged **Confusion Matrices** to balance Precision and Recall, ensuring the model effectively captures "High-Risk" counties without excessive false alarms.

---

### 🗺️ 5. US-Wide Geospatial Validation 
*Demonstrating real-world applicability at a national scale.*

![US Prediction Map](docs/images/prediction_map.jpg)

* **Generalization**: Successfully mapped predictions for **2,236 US Counties**.
* **Reliability**: Maintained **67.1% accuracy** on a completely unseen test set (456 counties), proving the model's value for national health policy planning.

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
