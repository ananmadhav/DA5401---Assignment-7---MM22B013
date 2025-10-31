# DA5401 – Assignment 7

**Name:** Anan Madhav T V  
**Roll Number:** MM22B013  

---

## 📂 Folder Structure  

├── DA5401_A7_MM22B013.ipynb           # Main Jupyter Notebook  
├── sat.trn                            # Train dataset  
├── sat.tst                            # Test dataset  
└── README.md                          # Readme file  

---

## ⚙️ How to Run  
1. Open the notebook `DA5401_A7_MM22B013.ipynb` in **Jupyter Notebook** or **Google Colab**.  
2. Make sure the files `sat.trn` and `sat.tst` are in the same directory.  
3. Run all cells sequentially to reproduce results and plots.

---

## 📝 Assignment Work

This assignment focuses on **multi-class model selection** using **ROC** and **Precision–Recall (PRC)** curve analysis for the **UCI Landsat Satellite dataset** (6 classes).  
The goal was to compare multiple classification algorithms and interpret their performance across different evaluation metrics and thresholds.

1. **Data Preparation:**  
   - Loaded and standardized the Landsat dataset.  
   - Split the data into training and testing sets.  

2. **Model Training:**  
   - Trained six different classifiers:  
     **K-Nearest Neighbors**, **Decision Tree**, **Dummy Classifier**, **Logistic Regression**, **Gaussian Naive Bayes**, and **Support Vector Classifier** (`probability=True`).  
   - For bonus analysis, experimented with **Random Forest** and **XGBoost**, and added a deliberately poor **flipped-label Logistic Regression** to demonstrate a model with **AUC < 0.5**.

3. **Evaluation Metrics:**  
   - Computed **Accuracy** and **Weighted F1-Score** as baseline metrics.  
   - Generated **One-vs-Rest (OvR) macro-averaged ROC** and **Precision–Recall curves** for all models.  
   - Calculated **macro-averaged AUC** and **Average Precision (AP)** values for comparison.  

4. **Interpretation:**  
   - Analyzed the ROC and PRC plots to identify best and worst performing models.  
   - Explained why poor models (like Dummy) show diagonal ROC lines and rapidly falling PRC curves as recall increases.  
   - Compared model rankings across F1, ROC-AUC, and PRC-AP to highlight trade-offs between precision, recall, and overall separability.

---

## ✅ Conclusion

- The **Support Vector Classifier (SVC)** achieved the **highest overall performance** with **AUC ≈ 0.985** and **AP ≈ 0.918**, showing strong and consistent results across all evaluation metrics.  
- **K-Nearest Neighbors** and **Logistic Regression** also performed competitively, while **Decision Tree** and **Gaussian Naive Bayes** showed moderate accuracy.  
- The **Dummy Classifier** performed at random-chance level (**AUC ≈ 0.5**), confirming its lack of discriminative power.  
- In the extended experiments, **XGBoost** slightly outperformed all other models, confirming the benefit of ensemble methods for this dataset.  
- The intentionally flipped-label Logistic Regression demonstrated **AUC < 0.5**, illustrating “worse-than-random” behavior.  

**Final Recommendation:**  
The **Support Vector Classifier** is the most suitable model for this classification task, providing the best balance of precision, recall, and overall class separability across multiple decision thresholds.  
Among ensemble extensions, **XGBoost** offers marginal improvements and could be chosen for production-level deployment.
