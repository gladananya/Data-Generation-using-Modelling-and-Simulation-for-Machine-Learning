# Data Generation using Modelling and Simulation for Machine Learning  
**Author:** Ananya  
**Roll No:** 102303160  

##  Objective

The objective of this assignment is to generate a synthetic dataset using a **simulation-based modelling approach** and evaluate multiple machine learning models to predict system performance.  
The final goal is to identify the **best-performing ML model** based on evaluation metrics.

##  Simulation Domain

This project simulates a simplified **healthcare outpatient system (OPD)**, where patients arrive, wait in queue, get service from doctors, and exit.  
Such systems are common in hospitals and clinics, where understanding waiting time and congestion is important for resource planning.

## Simulation Tool Used

**SimPy** (Python Discrete Event Simulation Library)

SimPy allows modelling of discrete events such as:
- patient arrivals
- queue formation
- service procedures
- waiting times

##  Project Files

| File | Description |
|---|---|
| `healthcare_sim.ipynb` | Google Colab notebook |
| `simulation_dataset.csv` | Generated simulation dataset |
| `model_r2_scores.png` | ML model comparison visualization |
| `README.md` | This documentation |

##  Methodology / Steps Followed

### **Step 1: Simulator Selection**
Selected **SimPy**, a Python-based discrete event simulation library suitable for queuing and service-oriented system modelling.

### **Step 2: Parameter Identification**

The following input parameters were considered with defined bounds:

| Parameter | Description | Lower Bound | Upper Bound |
|---|---|---|---|
| Arrival Rate | patient arrival frequency (patients/hour) | 5 | 40 |
| Service Time | average treatment time (minutes) | 10 | 45 |
| Number of Doctors | available healthcare providers | 1 | 10 |
| Simulation Time | total runtime (minutes) | 240 | 240 |

### **Step 3: Data Generation (Simulation)**

- 1000 random parameter configurations were generated
- Simulation was executed for each configuration
- Output performance metric collected:

✔ **Waiting Time (minutes)** — our prediction target

The synthetic dataset contains both input parameters and output values.

### **Step 4: Machine Learning Model Training**

Multiple ML models were trained to predict **average waiting time**:

- Linear Regression
- Random Forest Regressor
- Gradient Boosting Regressor
- Support Vector Regressor (SVR)
- KNN Regressor
- XGBoost Regressor
- 
### **Step 5: Evaluation Metrics**

Models were evaluated using:

- **R² Score**
- **RMSE**
- **MAE**

##  Results

Below is the performance comparison of models:

| Model | R² Score | MAE | RMSE |
|---|---|---|---|
| Linear Regression | 0.845 | 9.66 | 12.18 |
| Random Forest | 0.942 | 4.97 | 7.44 |
| Gradient Boosting | 0.933 | 6.30 | 8.05 |
| Support Vector Regressor | 0.048 | 26.79 | 30.19 |
| KNN Regressor | 0.891 | 7.08 | 10.21 |
| XGBoost | 0.933 | 5.34 | 7.98 |

> **Best Model Based on R²:** **Random Forest Regressor**

##  Visualization

The following plot compares R² scores across models:
<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/f4711478-ca09-4e15-9276-59bce0eaf7ae" />

Higher R² indicates better performance.

## Conclusion

This assignment demonstrates how **simulation-based data generation** can be used to create machine learning datasets in domains such as healthcare, where real-world data may be expensive, scarce, or privacy-sensitive.

Among the evaluated models, **Random Forest Regressor** achieved the highest R² score and lowest error metrics, indicating superior ability to model non-linear relationships in the simulated healthcare system.


