# Exoplanet Detection using Machine Learning

This repository contains the full pipeline for **machine learning-based exoplanet detection**, specifically for **F type stars**. The model is designed to predict the existence of exoplanets based on astrophysical parameters derived from **NASA's Exoplanet Archive**.

## Project Structure
```
├── create_train_file_improved_latest.ipynb        # Processes training data
├── create_test_file_improved_latest.ipynb         # Processes test data
├── exoplanet_prediction_improved_original.ipynb     # Machine learning model for prediction
├── final_train_file.csv                     # Preprocessed training data
├── final_test_file.csv                      # Preprocessed test data
├── exoplanet_archive_test_data.csv         # Raw exoplanet test data
├── exoplanet_archive_test_data_processed.csv # Processed test data
├── labelled_training_star_data_943_samples.csv         # Raw labelled training data
├── labelled_training_star_data_943_samples_processed.csv # Processed training data
├── constraints.txt                          # scipy version constraint
```

## Requirements
Make sure you have the necessary dependencies installed. You can install them using:
```bash
pip install lightkurve
pip install -r constraints.txt
```

## Package Versions
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

## How to Run the Project
### **1. Prepare the Data**
- Run `create_train_file_improved_latest.ipynb` to generate the training file with 'labelled_training_star_data_943_samples_processed.csv' as input.
- Run `create_test_file_improved.ipynb` to generate the testing file with 'exoplanet_archive_test_data_processed.csv' as input.

### **2. Train & Evaluate the Model**
- Run `exoplanet_prediction_improved_original.ipynb` to train and test the neural network model.
- The script will output various model performance metrics and generate predictions.

### **3. Predictions**
- The model will save predictions as `predictions.csv`, containing:
  - `Star_ID` (if applicable)
  - `Prediction` (1 = Exoplanet, 0 = Not an Exoplanet)

## Model Overview
The model used in this project is a deep learning based model built using TensorFlow/Keras. It includes:
- Fully connected layers with ReLU activations
- Binary classification with Sigmoid activation
- Optimized using AdamW optimizer
- Balanced dataset using SMOTE
  
The model has been trained on F, G and K-type star data.

