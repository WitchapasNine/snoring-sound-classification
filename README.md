## 🎙️ Automatic Snoring-Sound Classification (DES432 Statistics and Data Modeling project)

## 📌 Overview  
This project builds a machine learning pipeline to classify **snore vs. non-snore** 1-second audio clips.  
The system extracts **MFCC features** from raw audio and evaluates three traditional ML models: **Logistic Regression, k-Nearest Neighbors, and Support Vector Machine (SVM)**.  
Performance is validated with **nested cross-validation** and confirmed with **statistical significance testing**.

---

## 🚀 Features
- **MFCC Feature Extraction**
  - 20 MFCCs per frame from 1-second audio clips.
  - Summarized with **global mean + standard deviation** → 40 features per clip.
- **Model Comparison**
  - Logistic Regression (with regularization hyperparameter `C`).
  - k-Nearest Neighbors (varied `k` from 1–11).
  - RBF-SVM (tuned `C` and `gamma`).
- **Evaluation**
  - 5-fold **stratified cross-validation** with inner 3-fold grid search for hyperparameter tuning.
  - Metrics: Accuracy, Sensitivity (Recall for snore), Specificity, ROC-AUC ± Standard Error.
- **Statistical Testing**
  - **McNemar’s test** used to check if SVM’s improvement over Logistic Regression was statistically significant.

---

## 📊 Results  
Cross-validation results (public dataset, ~1,000 clips):

| Model   | Accuracy | Sensitivity | Specificity | AUC ± SE     |
|---------|----------|-------------|-------------|--------------|
| LogReg  | 0.934    | 0.932       | 0.936       | 0.983 ± 0.004 |
| kNN     | 0.983    | 0.970       | 0.996       | 0.997 ± 0.002 |
| SVM     | 0.997    | 0.994       | 1.000       | 1.000 ± 0.000 |

- ✅ **SVM achieved near-perfect accuracy and AUC.**  
- ✅ **McNemar’s test (p = 0.22)** showed no significant difference between SVM and Logistic Regression → LR is a lighter but competitive option for deployment.  

---

## 🛠️ Tech Stack
- **Language**: Python  
- **Libraries**: NumPy, Pandas, Scikit-learn, Librosa, Matplotlib, tqdm, statsmodels  
- **Data**: Public snore/non-snore WAV dataset (~1,000 clips, balanced)  

---

## 👥 Team members
6522790276 Kanapitch Khamjorn

6522770765 Sukpat Wongtrakool

6522772464 Kueakul Jongpermponwattana

6522780780 Witchapas Chotichaiyon

6522770799 Saharat Yuanthong

6522790201 Potcharaphon Eaksil

6722300255 Chia Jia Yi

