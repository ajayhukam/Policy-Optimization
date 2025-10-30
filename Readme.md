# Policy Optimization for Financial Decision-Making

## Overview
This project explores *loan approval optimization* using both *Supervised Deep Learning* and *Offline Reinforcement Learning (RL)* approaches.  
The goal is to improve decision-making for a fintech company’s loan approval process using historical LendingClub data (2007–2018).  

The project demonstrates how predictive modeling and policy learning can be combined to balance *risk management* and *profit maximization*.

---

## Objectives
1. Perform Exploratory Data Analysis (EDA) and feature engineering on LendingClub loan data.  
2. Train a *Deep Learning (MLP)* model to predict loan default risk.  
3. Frame the same problem as an *Offline Reinforcement Learning* task using *CQL (Conservative Q-Learning)*.  
4. Compare and analyze both models’ decision-making behaviors and financial implications.  
5. Document insights and recommendations for future deployment.                     

---

## Running the Project


1. Supervised Learning Model (MLP)
Train and evaluate the Deep Learning model:
python train_supervised_mlp.py

## Outputs:

Test metrics: AUC = 0.711, F1 = 0.157


2. Offline Reinforcement Learning (CQL)
Train the offline RL agent:
python train_rl_cql.py

##Outputs:


Trained model saved as models/cql_model/


Evaluation metric: Estimated Policy Value (EPV) printed after training



## Results Summary
Model TypeMetricValueInterpretationSupervised MLPAUC0.711Good ranking ability between defaults/non-defaultsF1-Score0.157Model detects some defaults but affected by class imbalanceOffline RL (CQL)

## Visualizations

Precision-Recall Curve — Highlights model precision under class imbalance

## Reward Function Design
ScenarioActionRewardLoan Approved & Fully PaidApprove+ (loan_amnt × int_rate)Loan Approved & DefaultedApprove- loan_amntLoan DeniedDeny0
This function captures realistic financial trade-offs: interest gains vs. principal loss.
