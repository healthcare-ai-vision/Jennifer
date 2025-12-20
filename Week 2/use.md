# Medical Imaging Datasets - Explorative Analysis
## 1.Sunnybrook Cardiac Dataset
- The Sunnybrook Cardiac Dataset is a medical imaging dataset containing cardiac MRI scans from multiple patients. It is widely used for research in cardiac disease classification, segmentation, and early diagnosis.
- This dataset originates from the Sunnybrook Health Sciences Centre and has been used in various medical imaging challenges. [https://www.cardiacatlas.org/sunnybrook-cardiac-data/]
- **Type of Imaging Data:** Cardiac MRI (Cine-MRI 2D Slices)
- **Available Classes or Labels:**
  - The dataset primarily classifies patients into normal and diseased categories based on MRI scans.
     - Normal (SC-N) – Healthy patients with no cardiac abnormalities.
     - Hypertrophic Cardiomyopathy (SC-HC) – Thickening of the heart muscle, reducing efficiency.
     - Dilated Cardiomyopathy (SC-DCM) – Heart's ability to pump blood is weakened due to enlargement.
     - Heart Failure (SC-HF) – Advanced heart failure cases with severe ventricular dysfunction.
   - There is labelling based on different MRI acquisition views and sequences:
     - SAX (Short Axis): Cross-sectional slices of the ventricles.
     - LAX (Long Axis): Vertical slices showing the heart's length.
     - PERF (Perfusion): Images tracking blood flow through the heart muscle.
- **Dataset Imbalance :**
  -  There is a massive disparity between the most common view (unnamed_2) and the rarest (1-image folders) which would be avoided as you would likely filter the dataset to use only the SAX slices for training a segmentation model.
-  **Challenges :**
  - *Motion Artifacts:* Because the heart is always beating, 2D slices can appear blurred if the "gating" (timing) of the MRI was not perfectly synced with the heartbeat.
  - *Legacy Annotations:* The ground truth contours were created in 2009. Medical imaging standards for what constitutes the "edge" of the heart muscle have evolved since then.
