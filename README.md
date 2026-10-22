## Asteroid Orbit Classification with Machine Learning (ReDI School)

This project was developed as a final project for the ReDI School Data Science course in spring 2021.

It combines exploratory data analysis with machine learning to classify near-Earth asteroids using orbital parameters and absolute magnitude.

## Project Overview

The goal of this project is to:

* Explore astronomical data and orbital properties
* Check missing values, duplicates and outliers
* Visualize feature distributions and relationships
* Investigate class imbalance
* Train a Decision Tree classifier
* Evaluate predictions using accuracy and per-class metrics
* Interpret feature importance and visualize the decision tree

## Dataset

The project uses the Orbit Classification dataset shared on Kaggle:

https://www.kaggle.com/brsdincer/orbitclassification

The target contains six labels:

* AMO*
* APO
* APO*
* ATE
* ATE*
* IEO*

The original data includes 11 numerical features describing orbital properties and absolute magnitude.

The final model uses four features:

* `a (AU)` — semi-major axis
* `q (AU)` — perihelion distance
* `Q (AU)` — aphelion distance
* `H (mag)` — absolute visual magnitude

## Tech Stack

* Python
* Pandas & NumPy
* Matplotlib & Seaborn
* Scikit-learn
* Decision Tree
* Jupyter Notebook / Google Colab

## Workflow

Data → Exploration → Outlier Inspection → Class Sampling → Feature Selection → Model Training → Evaluation → Interpretation

## Approach

### 1. Explore and inspect the data

* Inspect numerical summaries and data types
* Check for missing values and duplicate rows
* Examine the distribution of target classes
* Investigate an extreme observation and remove it

### 2. Visualize relationships

* Plot feature values by class
* Explore pairwise relationships
* Compare feature distributions with histograms
* Examine relationships between orbital parameters

### 3. Address class imbalance

The notebook limits each class to its first 150 observations.

This reduces the dominant class while retaining the smaller classes. The resulting dataset contains 421 observations and remains imbalanced.

Alternative sampling methods are included as commented experiments.

### 4. Train the classifier

The active model is a Decision Tree using the entropy criterion.

The notebook uses a stratified train/test split with:

* Test size: 33%
* Random state: 123
* Training observations: 282
* Test observations: 139

### 5. Evaluate and interpret

The notebook includes:

* Accuracy score
* Confusion matrix
* Precision, recall and F1-score by class
* Feature importance visualization
* A plot of the fitted decision tree

## Results

The saved notebook reports 100% accuracy on the 139-observation test split.

This is a result from the original educational experiment, not a new verification. Some classes have only two test observations, and no independent external evaluation is included.

Orbital classes are closely connected to orbital properties, so this task can partly reflect learning existing classification boundaries. The result should not be interpreted as general asteroid discovery or impact prediction.

## How to Run

### 1. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

The notebook uses older library APIs. In particular, `plot_confusion_matrix` may need to be replaced with `ConfusionMatrixDisplay.from_estimator` in a current scikit-learn environment.

### 2. Prepare the dataset

Download the dataset from Kaggle and place the CSV alongside the notebook using the expected filename:

```text
classast - pha.csv
```

The dataset is not included in this repository.

### 3. Open the notebook

```bash
jupyter notebook
```

Open:

```text
Project_Orbit_Classification_Yuliya_Goncharuk.ipynb
```

Review the saved outputs or run the cells sequentially after preparing the data and compatible dependencies.

## Project Files

* `Project_Orbit_Classification_Yuliya_Goncharuk.ipynb` — analysis, modeling, evaluation and visualizations
* `AsteroidRediPresentation.pptx` — final project presentation
* `README.md` — project overview

## Use Cases

* Applying data science to astronomical datasets
* Exploring imbalanced multiclass classification
* Understanding interpretable tree-based models
* Communicating scientific analysis through visualizations

## Learning Outcomes

Through this project I practiced:

* Exploring scientific data with Pandas
* Checking data quality and investigating outliers
* Visualizing feature relationships
* Examining class imbalance
* Preparing stratified train/test splits
* Training and interpreting a Decision Tree
* Evaluating predictions with multiple classification metrics
* Presenting technical findings

## Acknowledgments

Developed as a final project for the ReDI School Data Science course, spring 2021.

Dataset source:

https://www.kaggle.com/brsdincer/orbitclassification
