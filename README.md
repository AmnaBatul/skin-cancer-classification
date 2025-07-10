# skin-cancer-classification
Multi-modal skin lesion classification using images and metadata from the HAM10000 dataset (ResNet50).

This project focuses on classifying skin lesions into seven diagnostic categories using the HAM10000 dataset. It combines dermoscopic images and patient metadata (age, sex, lesion location).

## 🔹Dataset
* Name: HAM10000 (Human Against Machine with 10,000 training images)
* Source: https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000
* Size: 10,015 dermoscopic images + metadata
* Diagnosis Labels:
   * nv: Melanocytic nevi
   * mel: Melanoma
   * bkl: Benign keratosis-like lesions
   * bcc: Basal cell carcinoma
   * akiec: Actinic keratoses
   * vasc: Vascular lesions
   * df: Dermatofibroma

 ## 📊 Exploratory Data Analysis (EDA)
 Performed in `skin_cancer_EDA.ipynb`
 ### Metadata Analysis
 * Diagnosis Distribution: Visualized class imbalance; majority of samples belong to nv, minority classes include df, vasc.
 * Age Distribution: Most patients are between 25 and 65 years old.
 * Sex Distribution: Slight male dominance; some missing values.
 * Lesion Localization: Frequent locations include lower extremities, back, and trunk.
 ### Visual Inspection
 * Sampled and displayed one representative image per class for qualitative analysis.

## 🔧 Classification Pipeline
Performed in `skin_cancer_ResNet.ipynb`
### Model Details
* Image Model: Pretrained ResNet50 to extract visual features
* Metadata Model: To process age, sex, and location
* Fusion: Combined both branches before the final classifier

### Training Setup
* Loss Function: CrossEntropyLoss
* Optimizer: Adam
* Evaluation Metric: Macro F1-score, Accuracy
* Training Monitoring: Early stopping on testing F1

### Results
* Test Accuracy: ~88%
* Macro F1 Score: ~0.80

## 🛠️ How to Run
git clone https://github.com/AmnaBatul/skin-cancer-classification.git

cd skin-cancer-classification
