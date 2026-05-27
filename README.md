# 🇦🇪 UAE Property Valuator - R Reproducibility Project

![R](https://img.shields.io/badge/R-4.0+-276DC3?logo=r&logoColor=white)
![RStudio](https://img.shields.io/badge/RStudio-IDE-75AADB?logo=rstudio&logoColor=white)

This project is a reproduction of the UAE Property Valuator machine learning pipeline. The original project was built using Python (Jupyter Notebooks) as an end-to-end MLOps pipeline. As part of a reproducible research initiative, we successfully recreated the exploratory data analysis (EDA) and machine learning modeling stages entirely in **R**.

---

##  Team Members

| Name | Student Number |
| :--- | :--- |
| [Mukhammadkodir Abdusalomov] | [474664] |
| [Mirzakalonboy Khamidov] | [474561] |
| [Elbek Majidov] | [474***] |

---

##  Language Translation (Python to R)

**Original Implementation:** Python
- Used libraries: `pandas`, `scikit-learn`, `xgboost`, `lightgbm`, `matplotlib`, `seaborn`
- Environment: Jupyter Notebooks (`.ipynb`)

**Reproduced Implementation:** R
- Used libraries: `tidyverse` (`dplyr`, `ggplot2`), `caret`, `xgboost`, `lightgbm`, `randomForest`, `glmnet`
- Environment: R Markdown (`.Rmd`)

The primary goal was to validate the reproducibility of the original Python-based ML results using the R programming ecosystem. We successfully translated the data manipulation, statistical modeling, and model evaluation components from Python to R.

---

##  Dependencies and Requirements

To run this reproducible pipeline, you must have the following dependencies installed:

- **R Version:** 4.0 or higher
- **IDE:** RStudio (Recommended)
- **R Packages:**
  - Data Manipulation & I/O: `arrow`, `tidyverse`
  - EDA & Visualisation: `skimr`, `corrplot`, `scales`, `gridExtra`
  - Machine Learning & Modeling: `caret`, `glmnet`, `randomForest`, `xgboost`, `lightgbm`, `caretEnsemble`
  - Evaluation & Metrics: `Metrics`, `vip`
  - Parallel Processing: `doParallel`

*(Note: The first chunk in the `.Rmd` file includes an auto-install script that will automatically download and install any missing packages from CRAN).*

---

##  Project Scope and Goals

**What was successfully reproduced:**
- **Exploratory Data Analysis (EDA):** Recreated all major visualisations and data insights (Target distribution, Geographic spread, Correlation heatmaps, etc.).
- **Machine Learning Modeling:** Successfully trained, evaluated, and compared several models predicting property prices (log1p scale). 
  - *Models used:* OLS, Ridge, ElasticNet, Random Forest, XGBoost, LightGBM, and a Stacking Ensemble.
  - *Outcome:* We managed to reproduce the same high-quality results and predictive performance as the original Python implementation.

**What was excluded (Out of Scope):**
- **Feature Engineering:** The original feature engineering pipeline was heavily reliant on specific Python spatial libraries and was excluded due to time constraints. We used the pre-processed data for our R modeling pipeline.
- **Deployment & MLOps:** The deployment components (FastAPI backend, Streamlit frontend, Docker containerisation, MLflow tracking, and GCP Cloud Run) were not translated to R.

---

##  Repository Structure

```text
MLOps-GCP-RR/
├── Data/               # Processed datasets (parquet format)
├── Notebooks/          
│   ├── dubai_houses_ml.Rmd   # Main R Markdown file containing the reproduced pipeline
│   ├── dubai_houses_ml.html  # Knitted HTML report of the Rmd file
│   └── models/               # Saved R models (.rds, .model, .txt)
└── README.md           # Project documentation (this file)
```

---

##  Getting Started

### Running the R Pipeline

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Mukhammadkodir27/MLOps-GCP-RR.git
   cd MLOps-GCP-RR
   ```

2. **Open the R Markdown file:**
   Open `Notebooks/dubai_houses_ml.Rmd` in RStudio.

3. **Install Dependencies:**
   Run the setup chunk in the notebook, which handles the `install.packages()` logic automatically.

4. **Knit the Document:**
   Click the **Knit** button in RStudio to run the entire pipeline and generate the HTML report, or run the chunks sequentially to explore the data and models interactively.
