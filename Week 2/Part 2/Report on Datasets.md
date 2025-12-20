# Medical Imaging Datasets - Explorative Analysis
> Used [Medical_Dataset.ipynb](https://github.com/healthcare-ai-vision/2176_WiDS-25_AI-in-Healthcare/blob/3d1ed47a4b01e77ddbade21b1ee4be128d0e783d/Week%202/Part%202/Medical_Dataset.ipynb) to produce below information. 
## [1. Sunnybrook Cardiac Dataset](https://www.kaggle.com/datasets/tarunteja09/sunnybrook-cardiac-sturctured-2d)
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

## [2. Carotid Ultrasound Images](https://www.kaggle.com/datasets/orvile/carotid-ultrasound-images)
- The Carotid Ultrasound Images dataset is a specialized collection of B-mode ultrasound scans focused on the Common Carotid Artery (CCA). It is primarily used to develop and evaluate automated segmentation algorithms, which are crucial for calculating Intima-Media Thickness (IMT) and assessing cardiovascular risk.
- This dataset was originally published by Agata Momot on Mendeley Data and later hosted on Kaggle. The images were acquired using a Mindray UMT-500Plus machine with an L13-3s linear probe from a study group of 11 subjects examined on both the left and right sides of the neck.
- **Type of Imaging Data:** Ultrasound (B-mode) - Common Carotid Artery (CCA).
- **Available Classes or Labels:**
  - This is a **segmentation-focused dataset** containing two primary categories of files:
    - **US Images:** 1,100 raw grayscale ultrasound frames (100 images per subject).
    - **Expert Mask Images:** 1,100 corresponding binary masks where the carotid artery lumen and walls have been manually traced by technicians and verified by clinical experts.
  - The "labels" are pixel-level annotations used to distinguish the **Arterial Structure** from the surrounding **Background/Tissue**.
- **Dataset Imbalance:**
  - **Image-to-Mask Ratio:** Perfectly balanced at a 1:1 ratio (1,100 raw images vs. 1,100 masks).
  - **Subject Level:** There is a notable subject-level limitation as the data is derived from only **11 subjects**. This lack of broad demographic diversity can lead to model overfitting on specific anatomical patterns.
- **Challenges:**
  - *Speckle Noise:* Like all B-mode ultrasound, the images contain inherent "speckle" (granular noise) that can obscure the fine boundaries between the vessel wall and the lumen.
  - *Annotation Subjectivity:* Although verified by experts, manual segmentation of the carotid artery is subject to inter-observer variability, especially in frames where the artery wall is poorly defined due to low contrast.
  - *Anatomical Variance:* Because the dataset only features 11 individuals, a model may struggle to generalize to patients with significant arterial plaque, stenosis, or unusual vascular branching.
