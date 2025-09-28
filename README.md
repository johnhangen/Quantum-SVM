# Quantum SVM for Spotify Churn Prediction

This project implements and compares classical Support Vector Machine (SVM) and Quantum Support Vector Machine (QSVM) algorithms for predicting customer churn using a Spotify dataset.

## Project Overview

Customer churn prediction is a critical business problem where companies need to identify customers likely to discontinue their service. This project explores both classical and quantum machine learning approaches to solve this classification problem.

## Dataset

The project uses the **Spotify Churn Dataset** which includes features such as:
- Customer demographics (gender, age, country)
- Subscription details (type, listening time, songs per day)
- Behavioral metrics (skip rate, ads listened, offline listening)
- Target variable: `is_churned` (binary classification)

## Implementation Details

### Data Preprocessing
1. **Encoding**: Categorical variables converted using LabelEncoder
2. **Scaling**: Features standardized using StandardScaler
3. **Dimensionality Reduction**: Principal Component Analysis (PCA) applied
4. **Class Balancing**: Weighted classes to handle imbalanced dataset

### Classical SVM
- **Algorithm**: Support Vector Classifier with RBF kernel
- **Optimization**: Grid search for hyperparameter tuning
- **Parameters**: C=1, gamma='scale', kernel='rbf'
- **Performance**: ~52% accuracy on test set

### Quantum SVM (QSVM)
- **Quantum Backend**: Qiskit StatevectorSampler
- **Feature Map**: PauliFeatureMap with Z and ZZ gates
- **Kernel**: FidelityQuantumKernel using ComputeUncompute fidelity
- **Limitation**: Computationally intensive, tested on subset of data

## Installation and Setup

1. Clone the repository:
```bash
git clone https://github.com/johnhangen/Quantum-SVM.git
cd Quantum-SVM
```

2. Create a virtual environment:
```bash
python -m venv Quantum-SVM
source Quantum-SVM\Scripts\activate
```

3. Install required packages:
```bash
pip install -r requirements.txt
```

4. Launch Jupyter Notebook:
```bash
jupyter notebook "Quantum SVM.ipynb"
```

## Usage

The main notebook is structured in the following sections:

1. **Data Import**: Download and load the Spotify dataset
2. **EDA**: Explore data characteristics and patterns  
3. **Preprocessing**: Clean and prepare data for modeling
4. **PCA**: Reduce dimensionality for quantum implementation
5. **Classical SVM**: Train and evaluate traditional SVM
6. **Quantum SVM**: Implement and compare QSVM performance

## Results Summary

| Model | Training Time | Test Accuracy | Key Insights |
|-------|---------------|---------------|--------------|
| Classical SVM | ~1.2 seconds | 52.1% | Baseline performance with full dataset |
| Quantum SVM | Limited subset | In progress | Computationally intensive, requires optimization |