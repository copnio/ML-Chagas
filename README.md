This notebook builds and evaluates 11 machine learning classifiers to distinguish three patient groups from MALDI-TOF mass spectrometry data of serum samples filtered below 3 kDa.
Requirements:

Install all dependencies with a single command:
pip install numpy pandas matplotlib scikit-learn xgboost yellowbrick joblib 
networkx tabulate openpyxl

Expected folder structure:
paper ML chagas/
└── chagas/
    └── chagas/
        ├── all spectra/  ← .txt files, one per sample
        └── clasificacion.xlsx  ← sample labels (A, N, S)
Each .txt file contains two columns: m/z values and intensity values separated by a space. Each spectrum contains approximately 23,040 data points.
Update the file paths in Cell 4 (spectra folder) and Cell 16 (Excel labels) before running.

Pipeline
Raw spectra (.txt)
      ↓
Load & concatenate  →  Dataint (23040 x n_samples)
      ↓
StandardScaler  →  x_scaled
      ↓
OrdinalEncoder  →  Y1_code  (A=0, N=1, S=2)
      ↓
PCA (10 components)  →  visualization + model input
      ↓
LDA (2 components)  →  supervised class separation plot
      ↓
Train / Test split 80:20
      ↓
11 classifiers  →  accuracy + confusion matrix + ROC/AUC
      ↓
Graph ML PoC  →  sample similarity network
      ↓
Save best models  →  .pkl files





