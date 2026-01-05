🏦 Early Warning System (EWS) for Loan Default Prediction
This project implements a Machine Learning pipeline to predict credit risk in the banking sector. It uses a "Twin-Engine" approach (Micro-level classification & Macro-level aggregation) to identify high-risk loans and vulnerable industry sectors.

🚀 Project Overview
Objective: Predict the Probability of Default (PD) for individual loans and aggregate risk by sector.

Algorithm: XGBoost Classifier (Gradient Boosting).

Techniques: SMOTE (Synthetic Minority Over-sampling), Winsorization (Outlier Capping), Exposure-Weighted Risk Scoring.

Status: Deployed via Gradio Interface.

🛠️ The Pipeline
The project follows the Basel III / IFRS 9 modeling framework:

Data Engineering:

Vertical Stacking: Combined 6 quarters of snapshot data (Panel Data format).

Feature Engineering: Created DPD_Velocity (Trend of arrears) and mapped Restructure_Codes to ordinal risk ranks.

Preprocessing (No Data Leakage):

Imputation: Median (Numerical) & Mode (Categorical) calculated on Train set only.

Outlier Handling: Winsorization at the 99th percentile.

Balancing: Applied SMOTE to handle the 95:5 Class Imbalance.

Modeling:

Trained an XGBoost model to predict default probability.

Evaluated using Recall (Sensitivity) to minimize missed defaults.

Deployment:

Built a Gradio Web App for loan officers to test scenarios in real-time.

📊 Key Results
Model Performance: Achieved a Recall of 82% on the "Default" class, ensuring high sensitivity to risk.

Sector Analysis: Identified Tourism (Traditional Crafts) as a critical risk sector due to high exposure-weighted default rates.
