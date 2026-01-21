#  F1 World Champion Prediction (Machine Learning)

Predict the **Formula 1 Drivers’ World Champion** using historical season + driver performance data.  
This project frames the problem as a **supervised binary classification** task:

- `1` → Driver became **World Champion**
- `0` → Driver did **not** become World Champion

Multiple ML models are trained and compared, and the best-performing model is used to generate **championship probabilities** for a target season.

---

##  Key Features

- End-to-end ML pipeline (data → training → evaluation → prediction)
- Champion labeling and target variable assignment
- Data preparation (cleaning, encoding, validation checks)
- Handles **class imbalance**
- Trains and compares:
  - Logistic Regression (baseline)
  - Random Forest
  - Gradient Boosting
- Outputs **probability-based predictions** (not just yes/no)

---

##  How It Works (Pipeline Overview)

1. **Data Collection**
   - Uses historical F1 data (driver-season records and performance indicators).

2. **Champion Labeling**
   - Assigns `1` to the champion driver of each season, others get `0`.

3. **Data Preparation**
   - Missing value handling
   - Encoding categorical features (e.g., driver, team)
   - Consistency checks (duplicate rows, invalid values, datatype fixes)
   - Feature scaling (where needed, depending on model)

4. **Class Imbalance Handling**
   - Champions are rare compared to non-champions → dataset is highly imbalanced.
   - Uses imbalance strategies such as class weights / resampling (depending on implementation).

5. **Model Training**
   - Trains multiple models and tunes key parameters.
   - Splits data into train/test (or uses cross-validation).

6. **Evaluation**
   - Uses classification metrics suited for imbalance:
     - Precision / Recall
     - F1-score
     - ROC-AUC (if used)
   - Selects best model based on evaluation performance.

7. **Prediction**
   - Generates championship probability scores for the target season.
   - Ranks drivers by predicted probability.

---

---

##  Dataset

This project expects a **driver-season level dataset** (each row = one driver in one season).  
Typical columns may include (examples):

- driver name / id
- constructor / team
- wins, podiums, points
- average finish / DNF count
- qualifying performance indicators
- season year

**Target column**
- `champion` (0/1)

> If your dataset is private, you can keep it out of GitHub using `.gitignore`.

---

##  Installation

### 1) Clone the repo
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>

