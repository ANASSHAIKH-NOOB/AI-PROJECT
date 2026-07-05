# 🏥 HealTrack Pakistan: Data-Driven Stratification and Capacity Modeling of National Healthcare Infrastructure

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)
[![ML Framework](https://img.shields.io/badge/scikit--learn-latest-orange.svg)](https://scikit-learn.org/)
[![Dataset](https://img.shields.io/badge/Kaggle-Dataset-blueviolet.svg)](https://www.kaggle.com/datasets/algozee/healthcare-accessibility-and-quality-in-pakistan)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

HealTrack Pakistan is an advanced data science and predictive machine learning pipeline designed to dynamically stratify and model the capacity of Pakistan’s public and private healthcare institutions[cite: 2]. Using 37 key structural, human resource, financial, and operational variables across a dataset of 5,500 institutional logs, this project transforms raw healthcare data into actionable strategic insights[cite: 2]. It automatically flags under-resourced units, predicts critical infrastructural needs, and optimizes multi-million PKR provincial spending bars across targeted development tracks[cite: 2].

---

## 📋 Table of Contents
* [🏛️ Project Overview & Local Context](#%EF%B8%8F-project-overview--local-context)
* [📊 Data Pipeline & Feature Architecture](#-data-pipeline--feature-architecture)
* [⚙️ Methodology & Pipeline Phases](#%EF%B8%8F-methodology--pipeline-phases)
* [📈 Model Performance & Evaluation](#-model-performance--evaluation)
* [🚀 Inference Engine & Deployment Tracks](#-inference-engine--deployment-tracks)
* [🌍 Project Impact Assessment](#-project-impact-assessment)
* [🛠️ Installation & Usage](#%EF%B8%8F-installation--usage)

---

## 🏛️ Project Overview & Local Context

Healthcare resource distribution across Pakistan’s 5,500 public and private institutions exhibits deep systemic disparities[cite: 2]. While tier-1 metropolitan cities feature a dense footprint of advanced clinical assets, regional districts and rural facilities frequently face critical shortages of operational beds, specialized personnel, and emergency gear[cite: 2].

Manual auditing of these facility frameworks by provincial health departments is slow and prone to oversight[cite: 2]. This project implements a predictive Machine Learning classification architecture using 37 key infrastructure and human resource variables to dynamically tier healthcare operations, quickly highlighting vulnerable, under-resourced units across Pakistan's provinces[cite: 2].

---

## 📊 Data Pipeline & Feature Architecture

### 1. Target Variable Definition
Because public healthcare registries track facility capacities but rarely include pre-labeled socio-economic stratification tiers, this project mathematically engineers a ground-truth target column: **`Target_Capability_Tier`**[cite: 2].
* **Class 1 (High-Capability Hub):** Represents a fully equipped medical facility containing active ICU assets and a functional Emergency Department[cite: 2].
* **Class 0 (Under-Resourced Care Unit):** Lacks critical infrastructure, designating it as an immediate priority for resource allocation[cite: 2].

### 2. Predictor Feature Groups
The 36 structural predictor features are grouped into four core operational vectors[cite: 2]:

| Vector Group | Included Features |
| :--- | :--- |
| **Spatial & Structural Demographics** | `Sector` (Public vs Private), `City`, `Province`, `Hospital_Type`, `Distance_from_City_Center`[cite: 2] |
| **Core Infrastructure Assets** | `Total_Beds`, `ICU_Beds`, `Operation_Theatres`, `Emergency_Department`, `Diagnostic_Labs`, `Medical_Equipment_Score`[cite: 2] |
| **Human Resource Footprint** | `Total_Doctors`, `Specialists`, `Nurses`, `Paramedical_Staff`, `Doctor_Patient_Ratio` (Engineered)[cite: 2] |
| **Operational & Financial Metrics** | `Daily_Outpatients`, `Monthly_Admissions`, `Surgeries_Per_Month`, `Emergency_Cases`, `Surgery_Cost`, `Government_Funding`, `Rural_Patients_Percentage`[cite: 2] |

---

## ⚙️ Methodology & Pipeline Phases

### Phase 1: Data Acquisition & Structural Profiling
* **Source:** Automated cache fetch or fresh query via `kagglehub` from the `algozee/healthcare-accessibility-and-quality-in-pakistan` open-source repository[cite: 2].
* **Volume:** 5,500 entries spanning 37 multi-type columns (`int64`, `float64`, and `object`)[cite: 2].

### Phase 2: Actionable Data Preprocessing
* **Imputation:** Numeric values are filled using statistical column-wise **medians** to prevent skewness from extreme outliers, while text fields use the **mode**[cite: 2].
* **Encoding:** Vectorized label mapping normalizes binary categorical variables (`Sector`, `Emergency_Department`) into binary `1/0` values[cite: 2].

### Phase 3: Feature Selection via Multi-Criteria Voting Matrix
To filter out collinear noise, features are subjected to a rigorous normalized dual-scoring evaluation: Information Gain (Mutual Information) and Random Forest Feature Importance (Mean Decreasing Gini)[cite: 2].
---

## 📈 Model Performance & Evaluation

The processed dataset is partitioned into an `80/20` train-test split, with the training set balanced using synthetic resampling where necessary[cite: 2].

### 1. Classification Benchmarking
* **Model A: Baseline Logistic Regression**
  * *Characteristics:* Fast convergence, serves as the linear boundary baseline[cite: 2].
  * *Test Accuracy:* ~50% (highly susceptible to structural overlaps in raw multi-dimensional vectors)[cite: 2].
* **Model B: Ensemble Random Forest Classifier**
  * *Characteristics:* Captures non-linear dependencies across geographic and operational thresholds[cite: 2].
  * *Test Accuracy / F1-Score:* Achieves well-balanced macro metrics (~54% F1-Score for Under-Resourced identification), outperforming linear models in complex data topologies[cite: 2].

### 2. Multi-Target Regression Engine
Beyond strict classification, a secondary multi-output regression model forecasts specific structural metrics[cite: 2]:
* **Government_Funding Forecast:** Explains **59.12% of Variance ($R^2$)** with high fiscal predictability[cite: 2].
* **Total_Beds & Doctor_Patient_Ratio:** Modeled to surface local asset gaps relative to regional standards[cite: 2].

---

## 🚀 Inference Engine & Deployment Tracks

When a batch of monitored healthcare facilities is fed through the pipeline, the deployment engine automatically segments and parses data across three clinical optimization tracks[cite: 2]:

### 🏥 TRACK 1: INFRASTRUCTURAL KIT DEPLOYMENT
* Identifies facilities requiring immediate diagnostic and surgery equipment upgrades based on low `Medical_Equipment_Score` and operational demands[cite: 2].

### 👨‍⚕️ TRACK 2: HUMAN RESOURCE STRAIN REMEDIATION
* Calculates the exact average doctor staff deficit required to bring under-resourced hospitals back to safe, standard patient-to-staff workload bounds[cite: 2].

### 💰 TRACK 3: FINANCIAL OPTIMIZATION & REVENUE DEPLOYMENT
* Calculates the total recommended budget allocation (PKR) and separates it into area-specific spending recommendations[cite: 2]:
  1. **Physical Infrastructure:** Building expansion, wards, and trauma beds[cite: 2].
  2. **Human Resource Payroll:** Recruitment and retention packages for specialized medical officers[cite: 2].
  3. **Advanced Emergency Equipment:** Surgical tools, diagnostic machinery, and life-support kits[cite: 2].

---

## 🌍 Project Impact Assessment

### 1. Shift from Reactive Auditing to Predictive Stratification
Currently, provincial healthcare planning in Pakistan relies heavily on periodic manual audits, leading to severe blind spots[cite: 2]. HealTrack Pakistan provides a data-driven model that can run continuously, identifying vulnerable, under-resourced facilities instantly before structural failures or severe healthcare deficits occur[cite: 2].

### 2. Algorithmic Optimization of Fiscal and Public Resources
By using the Multi-Target Regression Engine and Track 3 Financial Optimization, provincial health secretaries can move away from arbitrary budget distribution[cite: 2]. Budgetary allocations can be linked directly to a facility's real-time operational load and specific shortages, ensuring maximum utilization of every public PKR spent[cite: 2].

### 3. Mitigation of Rural-Urban Healthcare Disparities
By integrating the `Rural_Patients_Percentage` and `Distance_from_City_Center` variables into the core classification and optimization tracks, the system acts as an equity filter[cite: 2]. It ensures that rural clinics and basic health units (BHUs) are mathematically highlighted for swift intervention, reducing the long-standing healthcare asset gap between metadata cities (like Lahore and Karachi) and regional outer-districts[cite: 2].
