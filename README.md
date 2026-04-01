Before running the notebook:

-Update the spectra folder path.
-Update the classification file path.
-Make sure the sample order matches between spectra and labels.

Required packages:

pip install numpy pandas matplotlib scikit-learn xgboost yellowbrick 
joblib networkx tabulate openpyxl


This notebook contains the machine learning workflow used to analyze MALDI-TOF 
blood serum samples spectra and classify three patient groups. The goal is to 
test multiple classifiers and compare their performance.

The analysis includes:

1. Data loading: The notebook reads spectra stored as .txt files. Each file corresponds to one sample and contains m/z and intensity values.
2. Data preprocessing: All spectra are combined into one matrix and normalized so samples can be compared properly.
3. Label processing: Sample classes (A, N, S) are converted into numeric values so they can be used in machine learning models.
4. Dimensionality reduction: PCA is used to reduce noise and visualize patterns. LDA is used to visualize class separation.
5. Model training: The dataset is split into training data (80%) and testing data (20%). Eleven classifiers are trained and compared.
6. Model evaluation: Performance is measured using accuracy, confusion matrices, ROC curves, and AUC scores.
7. Graph analysis: A similarity network is created to visualize relationships between samples.
8. Model saving: The best performing models are saved as .pkl files for later use.


Last Update:2026-March-31






