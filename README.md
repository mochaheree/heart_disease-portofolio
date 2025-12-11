# 🫀 Heart Disease Risk Profile — Data Analyst Portfolio Project

Hi, I'm Gevan! This is an end-to-end **Data Analyst portfolio project** using a heart disease dataset.  
I cleaned the data in Python, explored patterns through EDA, and then built a lightweight monitoring dashboard in Google Sheets.

> ⚠️ Disclaimer: This analysis focuses on **association, not medical causation**.  
> The results are intended for data insights and decision support, not clinical diagnosis.

---

## ✨ Project Goals
Think of this as a Health/Insurance analytics task. The goals are to:
1. Measure overall heart disease prevalence in the dataset.
2. Identify demographic and lifestyle patterns linked to higher prevalence.
3. Compare numeric biomarkers between groups.
4. Create a simple lifestyle risk indicator for segmentation.
5. Deliver insights in a dashboard for easy stakeholder monitoring.

---

## ❓ Business Questions
- What is the overall prevalence of heart disease?
- How does prevalence vary by **age group**, **gender**, and **stress level**?
- Which **numeric biomarkers** show the clearest separation between “Yes” vs “No” groups?
- Does a combined lifestyle risk score capture meaningful patterns?

---

## 📦 Dataset Overview
- Source: [heart-disease.csv](https://www.kaggle.com/datasets/oktayrdeki/heart-disease)
- Rows: **10,000**
- Columns: **21**
- Target label: **`heart_disease_status` (Yes/No)**
- Types: mix of numeric biomarkers + categorical lifestyle/demographics
- Missing values: small but present across several fields (~0.2–0.3%)

**Key feature groups**
- **Demographics:** age, gender  
- **Lifestyle:** smoking, alcohol_consumption, exercise_habits, stress_level, sleep_hours, sugar_consumption  
- **Clinical / biomarkers:** blood_pressure, cholesterol_level, bmi, triglyceride_level, fasting_blood_sugar, crp_level, homocysteine_level  
- **Clinical flags:** high_blood_pressure, high_ldl_cholesterol, low_hdl_cholesterol, diabetes, family_heart_disease  

---

## 🧹 Data Cleaning & Preparation
Cleaning was performed in Python:

1. **Data quality checks**
   - removed duplicates  
   - validated numeric ranges  
   - standardized column names into snake_case  

2. **Categorical normalization**
   - trimmed whitespace  
   - unified casing  
   - standardized labels (`yes/YES/ Yes` → `Yes`)  

3. **Missing value handling**
   - numeric columns → median imputation  
   - categorical columns → mode or `"Unknown"`  
   - target label was not imputed  

4. **Feature engineering**
   - created `age_group` buckets  
   - built a lightweight lifestyle risk score:
     - `risk_score_light` (0–6)
     - `risk_segment` (Low / Medium / High)

---

## 🔍 Exploratory Data Analysis (EDA)

### ✅ Key Insights (End of EDA)

**Insight 1 — Age group (mild pattern):**  
Age group shows only a mild prevalence variation. Heart disease prevalence stays fairly stable across age buckets (around **~19–22%**). There is a small bump in the **30–49** range, but the separation is weak overall, suggesting age alone is not a strong standalone risk indicator in this dataset.

**Insight 2 — Gender (marginal difference):**  
Gender differences are marginal. Females show slightly higher prevalence (**~20.7%**) compared to males (**~19.3%**). The gap is small, so gender is best treated as supporting demographic context rather than a primary risk driver.

**Insight 3 — Stress level (clearest categorical signal):**  
Stress level provides the clearest categorical signal, although the pattern is non-linear. The **Medium stress** group has the highest prevalence (**~21.4%**), followed by **High** (**~19.8%**) and **Low** (**~18.7%**). This suggests stress may relate to risk clustering in this dataset, but not in a strictly “higher stress = higher risk” way.

**Insight 4 — Lifestyle risk accumulation:**  
The heart disease group has a slightly higher average lifestyle risk score (**2.27 vs 2.24, +1.26%**), indicating that risk may be better captured through **combined lifestyle patterns** rather than any single categorical factor.

**Insight 5 — BMI shift:**  
Mean BMI is marginally higher among cases (**29.33 vs 29.02, +1.07%**), showing a small but consistent association between higher body mass and heart disease status.

**Insight 6 — Numeric separation is weak overall:**  
Other numeric biomarkers (blood pressure, cholesterol, triglycerides, CRP, homocysteine) show very small mean gaps (**<1%**), implying limited standalone separation in this dataset.

---

## 📊 Dashboard (Google Sheets)
A one-page dashboard was created to monitor prevalence and risk distribution interactively.

**Dashboard highlights**
- KPI cards:
  - Total Population
  - Heart Disease Prevalence (% Yes)
  - Average BMI
  - Average Lifestyle Risk Score
  - Average Sleep Hours
- Segment charts:
  - Prevalence by Age Group
  - Prevalence by Gender
  - Prevalence by Stress Level
  - Prevalence by Risk Segment
- Filters/slicers for quick exploration:
  - risk_segment, gender, & age_group

🔗 **Dashboard Link:** *[Heart Disease Dashboard](https://docs.google.com/spreadsheets/d/1fpL0BvnE8l5V7Pf1CYrRAMscvFv13T-HN-or4OMaHXE/edit?usp=sharing)*  
🖼️ **Preview:** *![Here](https://github.com/mochaheree/heart_disease-portofolio/blob/main/Heart_Disease_Dashboard.png)*

---

## 💡 Business Recommendations
1. **Prioritize multi-factor risk profiling**  
   Individual categorical factors show weak standalone effects, while combined lifestyle scoring offers clearer prioritization.

2. **Monitor BMI and lifestyle score as early warning indicators**  
   Both metrics display consistently higher values among heart disease cases.

3. **Use stress level as a supporting segmentation layer**  
   Stress is the clearest categorical signal and may help refine priority groups when combined with biomarkers.

---

## 🛠 Tools Used
- **Python:** pandas, numpy, matplotlib, seaborn  
- **Google Colab:** analysis environment  
- **Google Sheets:** dashboarding  

---

## 🚧 Limitations & Next Steps
- Most categorical and numeric gaps are small, suggesting the dataset may be balanced or synthetic.
- Findings are associative, not causal.
- Next steps:
  - explore interactions between biomarkers and lifestyle factors  
  - validate insights using richer or longitudinal medical datasets  

---

## 🙌 Thanks for reading!
If you have feedback or want to connect, feel free to reach out 🙂
