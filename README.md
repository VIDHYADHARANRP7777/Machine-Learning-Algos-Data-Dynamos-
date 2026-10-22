# ML Capstone Lab — Clustering, Classification & Regression
### 23CSE301 | Academic Year 2026–27

An interactive machine learning capstone project featuring **Regression, Classification, and Clustering** through a Streamlit web application and executed Jupyter notebooks.

The application allows users to explore machine learning algorithms, compare model performance, adjust parameters, and visualize results. Numerical results are generated using actual scikit-learn and SciPy execution based on the selected settings. Ground-truth labels are not used to fit clustering models.

## 🚀 Live Demo

**Explore the deployed application:**

### [Data Dynamos — ML Capstone Lab](https://datadynamos.streamlit.app/)

The interactive application includes three machine learning tracks:

- **Regression:** Compare 10 regression algorithms and evaluate their performance.
- **Classification:** Explore 10 classification algorithms across Part A and Part B.
- **Clustering:** Experiment with K-Means and Agglomerative Clustering, including four linkage methods.

## 📌 Project Overview

| Track | Algorithms | Dataset |
|---|---|---|
| Regression | Linear Regression, Ridge, Lasso, ElasticNet, Polynomial Regression, Decision Tree, Random Forest, Gradient Boosting, SVR, KNN | `enhanced_box_office_data_2000-2024.csv` |
| Classification — Part A | Logistic Regression, KNN, Gaussian Naive Bayes, Decision Tree, SVC | `ObesityDataSet_raw_and_data_sinthetic.csv` |
| Classification — Part B | Random Forest, AdaBoost, Gradient Boosting, Bagging, MLP | `ObesityDataSet_raw_and_data_sinthetic.csv` |
| Clustering | K-Means, Agglomerative Clustering with Ward, Complete, Average, and Single linkage | World Happiness Report dataset |

**Dataset availability:** The obesity and World Happiness datasets are bundled with the project. The box-office dataset is not bundled and must be provided separately for regression.

## 📂 Repository Structure

```text
Machine-Learning-Algos-Data-Dynamos-/
│
├── app/
│   ├── app.py
│   ├── supervised_pages.py
│   ├── supervised.py
│   └── utils.py
│
├── notebooks/
│   ├── 11_KMeans_Clustering.ipynb
│   └── 12_Agglomerative_Clustering.ipynb
│
├── data/
│   ├── world_happiness_report.csv
│   └── ObesityDataSet_raw_and_data_sinthetic.csv
│
├── tests/
│   ├── test_app.py
│   ├── test_supervised_ui.py
│   └── make_box_office_fixture.py
│
├── tools/
│   └── build_notebooks.py
│
├── requirements.txt
├── RUBRIC_CHECKLIST.md
└── README.md
```

### Directory Description

- **`app/`** — Streamlit application, supervised-learning pages, model pipelines, and clustering utilities.
- **`notebooks/`** — Executed Jupyter notebooks for K-Means and Agglomerative Clustering, with outputs visible.
- **`data/`** — Datasets used by the classification and clustering tracks.
- **`tests/`** — Tests for clustering, regression, and classification interfaces.
- **`tools/`** — Utility scripts for regenerating the clustering notebooks.
- **`RUBRIC_CHECKLIST.md`** — Checklist for verifying project requirements.

## 🛠️ Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/VIDHYADHARANRP7777/Machine-Learning-Algos-Data-Dynamos-.git
cd Machine-Learning-Algos-Data-Dynamos-
```

### 2. Create a virtual environment

**Windows — Command Prompt:**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**Linux or macOS:**

```bash
python -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## ▶️ Run the Streamlit Application

From the repository root, execute:

```bash
streamlit run app/app.py
```

Streamlit will display a local URL in the terminal, usually:

```text
http://localhost:8501
```

Open that URL in your browser to use the application locally.

Alternatively, access the deployed application directly:

**[https://datadynamos.streamlit.app/](https://datadynamos.streamlit.app/)**

## 📊 Track 1 — Regression

The regression track predicts worldwide box-office revenue using movie-related features.

### Algorithms

1. Linear Regression
2. Ridge Regression
3. Lasso Regression
4. ElasticNet Regression
5. Polynomial Regression
6. Decision Tree Regression
7. Random Forest Regression
8. Gradient Boosting Regression
9. Support Vector Regression (SVR)
10. K-Nearest Neighbors Regression

### Dataset

`enhanced_box_office_data_2000-2024.csv`

This dataset must be supplied separately because it is not bundled with the project.

### Configure the Dataset

Choose one of the following options:

- Place the CSV file inside the `data/` directory.
- Upload the CSV using the sidebar on the Regression page.
- Set the `BOX_OFFICE_CSV` environment variable to the file path.

**Windows CMD example:**

```bash
set BOX_OFFICE_CSV=D:\path\to\enhanced_box_office_data_2000-2024.csv
streamlit run app/app.py
```

Replace the example path with the actual location of your dataset.

### Modelling Approach

- Leakage-prone features are removed.
- The target variable is transformed using `log1p`.
- An 80:20 train-test split is used with `random_state=42`.
- Missing values are handled through imputation.
- Numerical features are scaled where required.
- Categorical features are encoded within pipelines.
- Preprocessing is fitted on training data only, including within cross-validation folds.

Evaluation includes regression metrics such as R², RMSE, and MAE, with revenue errors reported in USD. R² on the log-transformed target is also reported where applicable.

## 🧠 Track 2 — Classification

The classification track predicts obesity-related categories from demographic, lifestyle, and health-related features in the provided dataset.

### Dataset

`ObesityDataSet_raw_and_data_sinthetic.csv`

This dataset is bundled with the project.

### Part A Algorithms

1. Logistic Regression
2. K-Nearest Neighbors (KNN)
3. Gaussian Naive Bayes
4. Decision Tree Classifier
5. Support Vector Classifier (SVC)

### Part B Algorithms

6. Random Forest Classifier
7. AdaBoost Classifier
8. Gradient Boosting Classifier
9. Bagging Classifier
10. Multi-Layer Perceptron (MLP)

### Evaluation

Classification models can be compared using appropriate metrics, including:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix
- Cross-validation scores, where implemented

The application reproduces the notebook's classification preprocessing and saved Part A results.

## 🔍 Track 3 — Clustering

The clustering track explores patterns in country-level World Happiness Report indicators using unsupervised learning.

### Algorithms

**K-Means Clustering**
- Partitions observations into K clusters.
- Uses cluster evaluation metrics to help assess the choice of K.
- Supports cluster profiles and visualizations.

**Agglomerative Hierarchical Clustering**
- Ward linkage
- Complete linkage
- Average linkage
- Single linkage

### Analysis and Visualization

The clustering track includes:

- Cluster evaluation metrics.
- Elbow curve analysis.
- Silhouette-based evaluation.
- Cluster-size comparisons.
- Cluster profile analysis.
- PCA-based visualization.
- t-SNE-based visualization.
- Hierarchical clustering and dendrogram analysis.

The World Happiness panel is aggregated to one row per country before clustering. `Regional Indicator` is used only for post-hoc Adjusted Rand Index (ARI) validation and is not used to fit the clustering models.

## 📓 Run the Clustering Notebooks

The repository includes two executed notebooks with visible outputs:

- `11_KMeans_Clustering.ipynb`
- `12_Agglomerative_Clustering.ipynb`

To execute them from the repository root:

```bash
jupyter nbconvert --to notebook --execute --inplace notebooks/11_KMeans_Clustering.ipynb notebooks/12_Agglomerative_Clustering.ipynb
```

To regenerate the notebooks using the provided build script:

```bash
python tools/build_notebooks.py
```

## 🧪 Run the Tests

Run the clustering interface tests:

```bash
python tests/test_app.py
```

Run the regression and classification interface tests:

```bash
python tests/test_supervised_ui.py
```

The project includes checks for clustering UI behavior and supervised-learning interfaces. The synthetic box-office fixture is intended for testing only; it is not a replacement for the actual box-office dataset.

## ⚙️ Important Modelling Notes

### Regression

- The target is log-transformed using `log1p`.
- Leakage-prone columns are excluded.
- An 80:20 split is used with `random_state=42`.
- Imputation, scaling, and encoding are handled through pipelines.
- Cross-validation preprocessing is fitted within the relevant training folds.

**Known notebook issue:** Running `01_linear_regression.ipynb` from a clean kernel raises `NameError: name 'ordinal_features' is not defined`.

To fix the feature-set cell, define:

```python
categorical_features = ['Primary_Genre', 'Language_Grouped']
ordinal_features = ['Decade']
```

The notebook should then be executed from top to bottom to verify that all outputs are generated correctly.

The saved outputs may reflect a previous kernel state, so they should not be treated as proof that a notebook executes successfully from a clean kernel.

### Classification

- Notebook preprocessing is reproduced in the application.
- Train and test preprocessing matrices were verified to match the saved notebook workflow.
- The dataset's target labels are used for supervised model training and evaluation.

### Clustering

- Clustering models are fitted without using ground-truth class labels.
- Country-level observations are created by aggregating the happiness panel.
- Regional indicators are used only for post-hoc ARI validation.
- PCA and t-SNE support visualization and do not independently assign the original K-Means cluster labels.

## 🌐 Deployment

The application is deployed using Streamlit Community Cloud.

**Live application:** [https://datadynamos.streamlit.app/](https://datadynamos.streamlit.app/)

To deploy your own version:

1. Push the project repository to GitHub.
2. Open [Streamlit Community Cloud](https://share.streamlit.io/).
3. Connect your GitHub account if needed.
4. Select the repository.
5. Set the main application file to `app/app.py`.
6. Configure any required datasets and environment variables.
7. Deploy the application.

**Deployment note:** The regression page requires the actual box-office CSV. Ensure that the dataset is available to the deployed application through an appropriate file or upload mechanism. Do not commit sensitive information or credentials to GitHub.

## 🤖 AI Assistance Disclosure

Code scaffolding for the notebooks, application, and tests was generated with Claude (Anthropic).

The analysis and interpretation of results must be completed by the project authors in accordance with the course guidelines. All team members should review the implementation, understand the algorithms and preprocessing steps, independently interpret the outputs, and be prepared to explain the project during the viva.

## 🎯 Project Objectives

- Implement and compare multiple machine learning algorithms.
- Explore supervised and unsupervised learning techniques.
- Evaluate model performance using suitable metrics.
- Visualize model results and data patterns.
- Build an interactive Streamlit application.
- Provide reproducible notebooks and tests.
- Demonstrate understanding of model behavior, limitations, and evaluation.

---

**Repository:** [Machine-Learning-Algos-Data-Dynamos-](https://github.com/VIDHYADHARANRP7777/Machine-Learning-Algos-Data-Dynamos-)

**Live Demo:** [Data Dynamos — ML Capstone Lab](https://datadynamos.streamlit.app/)
