# Preprocessing SOP
 
## Labels

- Three-class diagnosis: **AD / Mixed / Non-AD** from `Final_Diagnosis` mapping.

- Stage-1 label (binary): **AD vs Others**; Stage-2 label: **Mixed vs Non-AD** (within non-AD subset).
 
## De-duplication

- **De-duplication**: per-scan one row (prefer `ScanID`; otherwise `BrcId+Scan_Date`); keep the earliest or most complete record.
 
## MMSE policy

- **MMSE**: take the score closest to the **scan date** per subject; if `Pre` and `Post` both available, prefer `Pre`.
 
## Variables

- **Stage-1 features**: ['048_Right Hippocampus__pct', '049_Left Hippocampus__pct', '117_Right Ent entorhinal area__pct', '118_Left Ent entorhinal area__pct', '171_Right PHG parahippocampal gyrus__pct', '172_Left PHG parahippocampal gyrus__pct', '155_Right MTG middle temporal gyrus__pct', '156_Left MTG middle temporal gyrus__pct', '133_Right ITG inferior temporal gyrus__pct', '134_Left ITG inferior temporal gyrus__pct', '201_Right STG superior temporal gyrus__pct', '202_Left STG superior temporal gyrus__pct', '123_Right FuG fusiform gyrus__pct', '124_Left FuG fusiform gyrus__pct', '203_Right TMP temporal pole__pct', '204_Left TMP temporal pole__pct', '167_Right PCgG posterior cingulate gyrus__pct', '168_Left PCgG posterior cingulate gyrus__pct', '169_Right PCu precuneus__pct', '170_Left PCu precuneus__pct', '199_Right SPL superior parietal lobule__pct', '200_Left SPL superior parietal lobule__pct', '197_Right SOG superior occipital gyrus__pct', '198_Left SOG superior occipital gyrus__pct', '145_Right MOG middle occipital gyrus__pct', '146_Left MOG middle occipital gyrus__pct', '129_Right IOG inferior occipital gyrus__pct', '130_Left IOG inferior occipital gyrus__pct', '052_Right Lateral Ventricle__pct', '053_Left Lateral Ventricle__pct', '050_Right Inf Lat Vent__pct', '051_Left Inf Lat Vent__pct', 'Brain_Left_0_Frontal_0__pct', 'Brain_Left_0_Frontal_1__pct', 'Brain_Left_0_Frontal_2__pct', 'Brain_Left_0_Frontal_99__pct', 'Brain_Left_1_Temporal_3__pct', 'Brain_Left_1_Temporal_4__pct', 'Brain_Left_1_Temporal_99__pct', 'Brain_Left_2_Parietal_5__pct', 'Brain_Left_2_Parietal_6__pct', 'Brain_Left_2_Parietal_99__pct', 'Brain_Left_3_Occipital_7__pct', 'Brain_Left_3_Occipital_8__pct', 'Brain_Left_4_DeepNuclei_9__pct', 'Brain_Left_4_DeepNuclei_10__pct', 'Brain_Left_4_DeepNuclei_99__pct', 'Brain_Left_99_nan_99__pct', 'Brain_Medial_99_nan_99__pct', 'Brain_Right_0_Frontal_0__pct', 'Brain_Right_0_Frontal_1__pct', 'Brain_Right_0_Frontal_2__pct', 'Brain_Right_0_Frontal_99__pct', 'Brain_Right_1_Temporal_3__pct', 'Brain_Right_1_Temporal_4__pct', 'Brain_Right_1_Temporal_99__pct', 'Brain_Right_2_Parietal_5__pct', 'Brain_Right_2_Parietal_6__pct', 'Brain_Right_2_Parietal_99__pct', 'Brain_Right_3_Occipital_7__pct', 'Brain_Right_3_Occipital_8__pct', 'Brain_Right_4_DeepNuclei_9__pct', 'Brain_Right_4_DeepNuclei_10__pct', 'Brain_Right_4_DeepNuclei_99__pct', 'Brain_Right_99_nan_99__pct', 'Brain_Left_0_Frontal_0_2__pct', 'Brain_Left_0_Frontal_1_2__pct', 'Brain_Left_0_Frontal_2_2__pct', 'Brain_Left_0_Frontal_99_2__pct', 'Brain_Left_1_Temporal_3_2__pct', 'Brain_Left_1_Temporal_4_2__pct', 'Brain_Left_1_Temporal_99_2__pct', 'Brain_Left_2_Parietal_5_2__pct', 'Brain_Left_2_Parietal_6_2__pct', 'Brain_Left_2_Parietal_99_2__pct', 'Brain_Left_3_Occipital_7_2__pct', 'Brain_Left_3_Occipital_8_2__pct', 'Brain_Left_4_DeepNuclei_9_2__pct', 'Brain_Left_4_DeepNuclei_10_2__pct', 'Brain_Left_4_DeepNuclei_99_2__pct', 'Brain_Left_99_99__pct', 'Brain_Medial_99_99__pct', 'Brain_Right_0_Frontal_0_2__pct', 'Brain_Right_0_Frontal_1_2__pct', 'Brain_Right_0_Frontal_2_2__pct', 'Brain_Right_0_Frontal_99_2__pct', 'Brain_Right_1_Temporal_3_2__pct', 'Brain_Right_1_Temporal_4_2__pct', 'Brain_Right_1_Temporal_99_2__pct', 'Brain_Right_2_Parietal_5_2__pct', 'Brain_Right_2_Parietal_6_2__pct', 'Brain_Right_2_Parietal_99_2__pct', 'Brain_Right_3_Occipital_7_2__pct', 'Brain_Right_3_Occipital_8_2__pct', 'Brain_Right_4_DeepNuclei_9_2__pct', 'Brain_Right_4_DeepNuclei_10_2__pct', 'Brain_Right_4_DeepNuclei_99_2__pct', 'Brain_Right_99_99__pct', 'MTL_total_pct', 'Temporal_lateral_total_pct', 'Medial_parietal_total_pct', 'Posterior_total_pct', 'Ventricles_total_pct', 'LI_PCgG', 'LI_PCu', 'LI_MTG', 'LI_ITG', 'LI_STG', 'asthma', 'falls', 'hypertension', 'Cerebrovascular_accident', 'Epilepsy', 'Diabetes_mellitus', 'Chronic_kidney_disease', 'Psoriasis', 'Parkinsons_disease', 'Multiple_sclerosis', 'Eczema', 'Hypertensive_disorder', 'Transient_ischemic_attack', 'Migraine', 'Chronic_obstructive_lung_disease', 'Arthritis', 'Heart_failure', 'Asthma', 'Ischemic_heart_disease', 'Inflammatory_bowel_disease', 'Atrial_fibrillation', 'Chronic_liver_disease', 'Chronic_sinusitis', 'Coronary_arteriosclerosis', 'age', 'MMSE', 'Gender_ID']

- **Stage-2 features**: ['wmh_icv_pct', 'wmh_log_icv', 'wmh_missing', 'hypertension', 'Hypertensive_disorder', 'Diabetes_mellitus', 'Atrial_fibrillation', 'Ischemic_heart_disease', 'Cerebrovascular_accident', 'Transient_ischemic_attack', 'Heart_failure', 'Coronary_arteriosclerosis', 'age', 'Gender_ID']
 
## Percent volumes

- **Percent volume**: `ROI_pct = ROI_volume / Total × 100`. Bilateral ROIs are summed before percent; lobe-level composites sum all ROI% in the lobe.
 
## WMH

- **WMH**: merge by `BrcId` from `WMH.xlsx` (columns `WMH(77)`, `Intracranial-volume`). If multiple rows per `BrcId`, take **max** WMH and **median** ICV; derive `wmh_icv_pct`, `wmh_log_icv`, `wmh_missing`.
 
## Missing data

- Numerical: **median imputation** (fit inside fold); Categorical: **most-frequent** + One-Hot (`handle_unknown='ignore'`).
 
## Cross-validation & thresholding

- 5-fold **grouped** CV by `BrcId`; **Stage-1 threshold** selected by inner CV (objective: macro-F1); external evaluation on outer folds.
 
