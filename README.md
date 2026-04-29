Hello everyone!

This notebook is part of my undergraduate thesis in Chemistry at Universidad Industrial de Santander (2024). 
The goal is to build a machine learning model that can help detect Chagas disease using MALDI-TOF mass spectra from blood serum samples.

IMPORTANT!!!

Before running the notebook:

-Update the spectra and classification folder path.

-Make sure the sample order matches between spectra and labels.

Required packages:

pip install numpy pandas matplotlib scikit-learn xgboost yellowbrick 
joblib networkx tabulate openpyxl

---

Here is what the notebook does, step by step:

Reading the data: The spectra are loaded from .txt files, each one representing a single patient sample with its m/z and intensity values.

Preprocessing: All spectra are combined into a single matrix and normalized so they can be compared fairly across samples.

Labels: The class labels Asymptomatic (A), Negative (N), and Symptomatic (S), are converted to numbers so the classifiers can work with them.

Dimensionality reduction: PCA is applied to reduce noise and explore whether the three groups show any natural separation. LDA is also used to visualize how well the classes can be distinguished.

Model training: The data is split 80/20 into training and test sets. Eleven different classifiers are trained, including SVM, Random Forest, XGBoost, neural networks, and others.

Evaluation: Each model is evaluated using accuracy, confusion matrices, ROC curves, and AUC scores.

Graph ML: A sample similarity network is built using cosine similarity and PCA scores, just to explore the structure of the data from a graph perspective.

Saving the models: The best models are saved as .pkl files so they can be reused without retraining.


Last Update:2026-April-4






