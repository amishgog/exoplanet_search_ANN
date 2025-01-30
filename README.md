# Exoplanet Detection using Machine Learning

This repository contains the full pipeline for **machine learning-based exoplanet detection**, specifically for **F and A-type stars**. The model is designed to predict the existence of exoplanets based on astrophysical parameters derived from **NASA's Exoplanet Archive**.

## 📂 Project Structure
```
├── create_train_file_improved.ipynb        # Processes training data
├── create_test_file_improved.ipynb         # Processes test data
├── exoplanet_prediction_improved.ipynb     # Machine learning model for prediction
├── final_train_file.csv                     # Preprocessed training data
├── final_test_file.csv                      # Preprocessed test data
├── exoplanet_archive_test_data.csv         # Raw exoplanet test data
├── exoplanet_archive_test_data_processed.csv # Processed test data
├── labelled_training_star_data.csv         # Raw labelled training data
├── labelled_training_star_data_processed.csv # Processed training data
├── constraints.txt                          # scipy version constraint
```

## 📌 Requirements
Make sure you have the necessary dependencies installed. You can install them using:
```bash
pip install lightkurve
pip install -r constraints.txt
```

## 📦 Package Versions
This project was built using the following package versions:
```
- Python 3.x
- TensorFlow 2.x
- Keras 2.x
- NumPy 1.x
- Pandas 1.x
- Matplotlib 3.x
- Imbalanced-learn 0.x
- SciPy 1.14.0
- Lightkurve 2.5.0
- Tsfresh 0.20.3
```

## 🚀 How to Run the Project
### **1. Prepare the Data**
- Run `create_train_file_improved.ipynb` to generate `final_train_file.csv`.
- Run `create_test_file_improved.ipynb` to generate `final_test_file.csv`.

### **2. Train & Evaluate the Model**
- Run `exoplanet_prediction_improved.ipynb` to train and test the neural network model.
- The script will output model accuracy and generate predictions.

### **3. Predictions**
- The model will save predictions as `predictions.csv`, containing:
  - `Star_ID` (if applicable)
  - `Prediction` (1 = Exoplanet, 0 = Not an Exoplanet)

## 📊 Model Overview
The model used in this project is a **Neural Network** built using TensorFlow/Keras. It includes:
- Fully connected layers with ReLU activations
- Binary classification with Sigmoid activation
- Optimized using Adam optimizer
- Balanced dataset using SMOTE

## 🔍 Dataset Details
- **Source:** NASA Exoplanet Archive
- **Star Types:** F and A-type stars
- **Training Data:** `final_train_file.csv` (processed from `labelled_training_star_data.csv`)
- **Test Data:** `final_test_file.csv` (processed from `exoplanet_archive_test_data.csv`)
- Features include multiple astrophysical parameters that influence exoplanet detection.

## ✅ Results
The trained model achieves a validation accuracy of **82.81%**.

