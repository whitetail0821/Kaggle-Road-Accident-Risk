# 🏆 [Kaggle] Road Accident Risk Prediction Analysis (Regression)

**"A deep dive into tuning powerful boosting models and navigating environmental data complexities to predict granular accident risk."**

---

## 1. 💡 Project Overview

| Item | Detail |
| :--- | :--- |
| **Objective** | Develop a Regression model to predict **Accident Risk** based on geographical and environmental road factors. |
| **Metric** | $\text{RMSE}$ (Root Mean Squared Error) Minimization |
| **Best Performance** | **Public Score: 0.05566** (Personal Best) |
| **Final Rank** | 2112th (Out of 4083 total participants, $\approx$ Top 51.7%) |
| **Technologies** | $\text{Python (Pandas, Scikit-learn)}$, $\mathbf{LightGBM}$, **$\text{GridSearchCV}$** |

---

## 2. 🛠️ Methodology and Achievements (Process & Achievement)

This project focused not only on maximizing performance but also on **mastering advanced model tuning techniques** and **robust troubleshooting**.

### A. Data Preprocessing and EDA

* **Feature Engineering:** Applied **One-Hot Encoding** to categorical features like 'road_type', 'lighting', and 'time_of_day' for effective model ingestion.
* **Outlier Handling:** Attempted a **Log Transformation** on $'num_reported_accidents' to mitigate skewness. This was ultimately excluded from the final model as it did not yield a significant Public Score improvement, emphasizing a strategic focus on hyperparameter tuning instead.

### B. Baseline Model Construction and Analysis

* **Model Selection:** Employed **LightGBM**, a highly efficient Gradient Boosting framework, as the primary model.
* **Performance Tuning:** Achieved a Validation RMSE of 0.0559 through initial tuning. Further refinement included reducing the learning_rate to 0.01 and increasing n_estimators to 3000 to balance training time with prediction precision.
* **Feature Importance:** Confirmed that 'curvature' and 'speed_limit' were the most influential features, guiding subsequent tuning efforts.

### C. Technical Deep Dive (Advanced Approach)

* **Model Switching Attempt:** Explored XGBoost as an alternative to push past the performance ceiling. *(While the final notebook focuses on LightGBM for cleanliness, this step confirmed the limits of single-model tuning on this dataset.)*

---

## 3. 🎯 Key Learnings and Future Directions

This competition provided valuable insights into practical machine learning deployment and optimization.

* **Limit of Tuning:** Confirmed that the 0.05566 performance barrier could not be broken solely through parameter optimization, highlighting the necessity of data enrichment.
* **Future Strategy:** For future projects, the primary focus will shift to **Ensembling techniques** (blending LGBM and XGBoost predictions) and **deeper Feature Engineering** (creating new interaction terms) to effectively lower the RMSE

---

### File Structure

* `final_submission.ipynb`: Jupyter Notebook containing the final LightGBM model development, analysis, and submission process.
* `train.csv`, `test.csv`: (Dataset files)
