# **Occupancy Detection using PIR Sensors and Machine Learning**

This project develops and evaluates machine learning models for detecting human presence and motion in an office environment using Passive Infrared (PIR) sensor data. The primary goal is to accurately classify the state of a room into one of three categories: vacant, occupied by a stationary person, or occupied by a moving person.

## **Project Overview**

PIR sensors are a cost-effective and common technology for detecting motion. However, raw sensor data can be noisy and challenging to interpret. This project leverages data from a grid of 55 PIR sensors to train and compare two supervised machine learning models: **K-Nearest Neighbors (KNN)** and **Decision Tree Classifier**.

The analysis includes comprehensive data preprocessing to handle sensor-specific issues, model training with hyperparameter tuning, and a thorough evaluation to determine the most effective model for this classification task. A detailed report outlining the methodology and findings is included in report.pdf.

## **Dataset**

The project utilizes the "PIR-based Occupancy Detection (PIRVision)" dataset from the UCI Machine Learning Repository. It consists of readings from 55 PIR sensors, temperature data, and a corresponding label for the room's state.

* **Label 0:** Vacant  
* **Label 1:** Occupied (Stationary)  
* **Label 2:** Occupied (Motion)

The data is provided in two separate CSV files, pirvision\_office\_dataset1.csv and pirvision\_office\_dataset2.csv, which are merged for the analysis.

## **Key Features**

* **Data Cleaning:** Implemented procedures to handle sensor saturation (values of 16383\) by replacing them with NaN and using forward-fill to impute missing values.  
* **Feature Engineering:** Utilized the 55 PIR sensor readings and temperature as features for the classification models.  
* **Model Implementation:** Built, trained, and evaluated KNN and Decision Tree classifiers from scratch using scikit-learn.  
* **Hyperparameter Tuning:** Employed GridSearchCV to find the optimal hyperparameters for the KNN model, significantly improving its performance.  
* **Performance Evaluation:** Assessed models using accuracy, confusion matrices, and detailed classification reports.

## **Final Results**

The K-Nearest Neighbors (KNN) model emerged as the superior classifier for this task after hyperparameter optimization.

| Model | Accuracy |
| :---- | :---- |
| Decision Tree | 95.39% |
| **Optimized KNN (k=1)** | **96.76%** |

The optimized KNN model demonstrated a higher capability to accurately distinguish between vacant, stationary, and motion states, making it a reliable solution for this occupancy detection scenario.

## **How to Run This Project**

### **Prerequisites**

* Python 3.8+  
* Jupyter Notebook or JupyterLab  
* Required Python libraries: pandas, numpy, scikit-learn, matplotlib.

You can install the necessary libraries using pip:

pip install pandas numpy scikit-learn matplotlib

### **Instructions**

1. **Clone the repository:**  
   git clone \<your-repository-url\>  
   cd \<your-repository-directory\>

2. **Place the data files** (pirvision\_office\_dataset1.csv and pirvision\_office\_dataset2.csv) in the root directory.  
3. **Launch Jupyter:**  
   jupyter lab

4. Open and run the Assignment2.ipynb notebook to see the full analysis, from data loading and preprocessing to model training and evaluation.

## **Repository Contents**

* Assignment2.ipynb: The main Jupyter Notebook containing all the code and analysis.  
* pirvision\_office\_dataset1.csv: The first part of the training dataset.  
* pirvision\_office\_dataset2.csv: The second part of the training dataset.  
* report.pdf: A detailed report discussing the project's methodology, results, and conclusions.  
* README.md: This file.