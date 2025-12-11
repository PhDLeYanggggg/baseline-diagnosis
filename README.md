Hierarchical 3-Class Diagnostic Model for Alzheimer's DiseaseThis repository contains a machine learning pipeline for the 3-class classification of dementia diagnosis: Alzheimer's Disease (AD), Mixed Dementia, and Non-AD.
The model utilizes a Hierarchical XGBoost approach, combining MRI volumetric features, cognitive scores (MMSE), white matter hyperintensities (WMH), and clinical comorbidities to achieve robust diagnostic performance.
📌 Project Overview
Objective: Classify subjects into three diagnostic groups: AD, Mixed, or Non-AD.Methodology: A 2-Stage Hierarchical Classification framework.Stage 1: Detect AD vs. Others (Binary Classification).
Stage 2: Differentiate Mixed vs. Non-AD among the non-AD predictions from Stage 1.Key Metrics: Macro F1-Score, Balanced Accuracy, and Fairness (Gender/Ethnicity).
🚀 Features & Data
The model utilizes a comprehensive set of features:MRI Features: Percent volumes (ROI / Total Intracranial Volume * 100) for key regions (Hippocampus, Entorhinal area, Lobar volumes, Ventricles, etc.).
Composites: Aggregated volumes for Medial Temporal Lobe (MTL), Lateral Temporal, Medial Parietal, etc.Laterality Indices: Left-Right asymmetry measures.
Clinical Data: Age, Sex, MMSE scores (Mini-Mental State Examination).
Vascular/Comorbidities: White Matter Hyperintensities (WMH), Hypertension, Diabetes, Stroke history, etc.🛠 Model Architecture
Stage 1: AD DetectionAlgorithm: XGBoost Classifier.Input: Full feature set (MRI + Clinical).Target: AD (1) vs Others (0).
Thresholding: Dynamic threshold optimization based on cross-validated probability calibration (Best threshold $\approx$ 0.538)
2.
Stage 2: Mixed vs. Non-ADAlgorithm: XGBoost Classifier.Input: Subset of subjects classified as "Others" in Stage 1.
Features: Enhanced with specific vascular features (WMH, vascular comorbidities) relevant to Mixed Dementia
3.
Target: Mixed (1) vs Non-AD (0).📊 Performance HighlightsThe hierarchical model demonstrates strong performance, particularly in identifying AD cases.
Overall Confusion Matrix: 4Pred ADPred MixedPred Non-ADTrue AD19173342True Mixed101438106True Non-AD34130509Overall Accuracy: ~86.5%Macro F1-Score: ~0.806 5AD Recall: ~96% (High sensitivity for Alzheimer's detection).
⚖️ Fairness AnalysisFairness checks were conducted to ensure the model does not exhibit significant bias across demographic groups6:Gender: The model shows high consistency between male and female groups (Accuracy gap < 1%).
Ethnicity: Analysis performed across multiple ethnic groups. Note: Some minority groups have small sample sizes (<30), and results for those groups should be interpreted with caution.

📈 VisualizationsThe pipeline automatically generates diagnostic plots stored in surv_out/:SHAP 
Plots: Feature importance analysis for Stage 1 and Stage 27.Calibration Curves: Reliability diagrams (Raw vs Isotonic)
8.Violin Plots: ROI distributions across diagnostic groups9.Interaction Plots: 2D/3D visualizations of feature interactions (e.g., Ventricles vs MTL)
🔧 RequirementsPython 3.8+xgboostscikit-learnpandas & numpymatplotlib & seabornscikit-posthocs (for statistical testing)shap (for explainability)
📝 UsagePlace the dataset (Merge_data_with_Pre_Mini_Mental_Total.csv and WMH.xlsx) in the root directory.Run the main notebook baseline_dignosis.ipynb.Outputs will be generated in the surv_out and hier_out folders.
