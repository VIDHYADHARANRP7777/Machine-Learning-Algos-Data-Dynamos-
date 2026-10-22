# ML Capstone Lab — Clustering, Classification & Regression
### 23CSE301 | Academic Year 2026–27

An interactive machine learning capstone project featuring **Regression, Classification, and Clustering** through a Streamlit web application and Jupyter notebooks.

The application allows users to explore machine learning algorithms, compare model performance, adjust parameters, and visualize results. Numerical results are generated using scikit-learn and SciPy based on the selected settings. Ground-truth labels are not used to fit clustering models.

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
├── Classification/
│   └── Classification_PartA/
│       └── notebooks/
│           ├── 01_logistic_regression.ipynb
│           ├── 02_knn.ipynb
│           ├── 03_naive_bayes.ipynb
│           ├── 04_decision_tree.ipynb
│           ├── 05_svc.ipynb
│           ├── 07_random_forest.ipynb
│           ├── 08_adaboost.ipynb
│           ├── 09_gradient_boosting.ipynb
│           ├── 10_bagging.ipynb
│           ├── 11_mlp.ipynb
│           └── 12_final_comparison.ipynb
│
├── Clustering/
│   ├── 11_KMeans_Clustering.ipynb
│   └── 12_Agglomerative_Clustering.ipynb
│
├── Regression/
│   ├── 01_linear_regression.ipynb
│   ├── 02_ridge_regression.ipynb
│   ├── 03_lasso_regression.ipynb
│   ├── 04_elasticnet_regression.ipynb
│   ├── 05_polynomial_regression.ipynb
│   ├── 06_decision_tree_regression.ipynb
│   ├── 07_random_forest_regression.ipynb
│   ├── 08_gradient_boosting_regression.ipynb
│   ├── 09_svr.ipynb
│   └── 10_knn_regression.ipynb
│
├── UI/
│   ├── app.py
│   ├── supervised_pages.py
│   ├── supervised.py
│   └── utils.py
│
├── LICENSE
├── README.md
├── UPDATE_INSTRUCTIONS.md
└── requirements.txt
```

*Note: The tree reflects the repository's top-level structure shown in GitHub. Verify the internal filenames against your actual repository before submission.*

## 📁 Directory Description

- **`Classification/`** — Classification notebooks organized under `Classification_PartA/`.
- **`Clustering/`** — Notebooks for K-Means and Agglomerative Clustering.
- **`Regression/`** — Notebooks for the regression algorithms.
- **`UI/`** — Streamlit application and supporting supervised-learning modules.
- **`requirements.txt`** — Python dependencies required to run the project.
- **`UPDATE_INSTRUCTIONS.md`** — Instructions related to updating the application.
- **`LICENSE`** — Project licensing information.

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
streamlit run UI/app.py
```

Streamlit will display a local URL in the terminal, usually:

```text
http://localhost:8501
```

Open the URL in your browser to use the application locally.

Alternatively, access the deployed application:

**[https://datadynamos.streamlit.app/](https://datadynamos.streamlit.app/)**

> **Important:** The command above assumes that `app.py` is located inside `UI/`, as shown in the repository structure. If the entry-point file has a different name or location, update the command accordingly.

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

The dataset is not bundled with the project and must be supplied separately.

### Configure the Dataset

Choose one of the following options, depending on what the application supports:

- Place the CSV file in the expected data directory.
- Upload the CSV through the Regression page, if upload functionality is available.
- Set the `BOX_OFFICE_CSV` environment variable if supported by the application.

**Windows CMD example:**

```bash
set BOX_OFFICE_CSV=D:\path\to\enhanced_box_office_data_2000-2024.csv
streamlit run UI/app.py
```

Replace the example path with the actual location of the dataset.

### Modelling Approach

- Leakage-prone features are removed.
- The target variable is transformed using `log1p`.
- An 80:20 train-test split is used with `random_state=42`.
- Missing values are handled through imputation.
- Numerical features are scaled where required.
- Categorical features are encoded within pipelines.
- Preprocessing is fitted on training data only, including within cross-validation folds.

Evaluation includes R², RMSE, and MAE. Revenue errors are reported in USD, and R² on the log-transformed target is reported where applicable.

## 🧠 Track 2 — Classification

The classification track predicts obesity-related categories using features from the obesity dataset.

### Dataset

`ObesityDataSet_raw_and_data_sinthetic.csv`

This dataset is described as bundled with the project.

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

### Evaluation Metrics

Classification models can be compared using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix
- Cross-validation scores, where implemented

The confusion matrix compares actual class labels with predicted class labels. Precision, recall, and F1-score provide additional insight into performance for individual categories.

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

- Elbow curve analysis.
- Silhouette-based evaluation.
- Cluster-size comparisons.
- Cluster profile analysis.
- PCA-based visualization.
- t-SNE-based visualization.
- Hierarchical clustering and dendrogram analysis.
- Cluster evaluation metrics.

The World Happiness panel is aggregated to one row per country before clustering. `Regional Indicator` is used only for post-hoc Adjusted Rand Index (ARI) validation and is not used to fit the clustering models.

### Run the Clustering Notebooks

The repository includes the following notebooks:

- `11_KMeans_Clustering.ipynb`
- `12_Agglomerative_Clustering.ipynb`

Open them in Jupyter Notebook or JupyterLab to execute the cells and inspect the outputs.

If both notebooks are located in `Clustering/`, you can execute them from the repository root with:

```bash
jupyter nbconvert --to notebook --execute --inplace Clustering/11_KMeans_Clustering.ipynb Clustering/12_Agglomerative_Clustering.ipynb
```

Ensure that Jupyter and the project's dependencies are installed before running the command.

## ⚙️ Important Modelling Notes

### Regression

- The target is log-transformed using `log1p`.
- Leakage-prone columns are excluded.
- An 80:20 split is used with `random_state=42`.
- Imputation, scaling, and encoding are handled through pipelines.
- Cross-validation preprocessing is fitted within the relevant training folds.

**Known notebook issue:** Running `01_linear_regression.ipynb` from a clean kernel previously raised `NameError: name 'ordinal_features' is not defined`.

The feature-set cell should define:

```python
categorical_features = ['Primary_Genre', 'Language_Grouped']
ordinal_features = ['Decade']
```

Execute the notebook from top to bottom after fixing the issue to verify that all outputs are generated correctly. Saved outputs from an earlier kernel state do not guarantee that a notebook runs successfully from a clean kernel.

### Classification

- The application is intended to reproduce the notebook preprocessing.
- Classification models use labelled data for training and evaluation.
- Model performance should be compared using appropriate classification metrics.

### Clustering

- Clustering models are fitted without ground-truth class labels.
- Country-level observations are created by aggregating the happiness panel.
- Regional indicators are used only for post-hoc ARI validation.
- PCA and t-SNE support visualization and do not independently assign the original K-Means cluster labels.

## 🧪 Testing

Run the notebooks and test scripts that are present in your repository.

For example, if your project contains dedicated test scripts:

```bash
python tests/test_app.py
python tests/test_supervised_ui.py
```

**Note:** These commands require the corresponding files to exist. The repository screenshot does not show a `tests/` directory, so add or adjust these commands only if those test files are available in your actual project.

## 🌐 Deployment

The application is deployed using Streamlit Community Cloud.

**Live application:** [Data Dynamos — ML Capstone Lab](https://datadynamos.streamlit.app/)

To deploy another version:

1. Push the project to GitHub.
2. Open [Streamlit Community Cloud](https://share.streamlit.io/).
3. Connect your GitHub account if necessary.
4. Select the repository.
5. Choose the Streamlit entry-point file.
6. Configure required datasets and environment variables.
7. Deploy the application.

The regression page requires the actual box-office CSV. Ensure that the deployed application can access this dataset through the supported upload or configuration method. Do not commit passwords, API keys, or other secrets to GitHub.

## 🤖 AI Assistance Disclosure

Code scaffolding for the notebooks, application, and tests was generated with Claude (Anthropic).

The analysis and interpretation of results must be completed by the project authors in accordance with the course guidelines. All team members should review the implementation, understand the algorithms and preprocessing steps, independently interpret the outputs, and be prepared to explain the project during the viva.

## 🎯 Project Objectives

- Implement and compare multiple machine learning algorithms.
- Explore supervised and unsupervised learning techniques.
- Evaluate model performance using suitable metrics.
- Visualize model results and data patterns.
- Build an interactive Streamlit application.
- Provide reproducible notebooks and testing workflows.
- Demonstrate understanding of model behavior, limitations, and evaluation.

---

**Repository:** [Machine-Learning-Algos-Data-Dynamos-](https://github.com/VIDHYADHARANRP7777/Machine-Learning-Algos-Data-Dynamos-)

**Live Demo:** [Data Dynamos — ML Capstone Lab](https://datadynamos.streamlit.app/)
