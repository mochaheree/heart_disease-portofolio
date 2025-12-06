# 🫀 Heart Disease Risk Profile — Data Analyst Portfolio Project

Hi, I'm Gevan! This is an end-to-end **Data Analyst case study** based on a heart disease dataset.  
I used Python to clean the data, explore patterns, and extract insights. The next step after this README is building a lightweight monitoring dashboard in Google Sheets.

> ⚠️ Disclaimer: This project focuses on **association, not medical causation**.  
> The insights are for data storytelling and decision support, not clinical diagnosis.

---

## ✨ Project Goals
Imagine I’m a Data Analyst in a health/insurance company. The business wants to:
1. Understand how common heart disease is in this dataset.
2. Identify which factors show clearer differences between individuals with vs without heart disease.
3. Summarize lifestyle patterns into a simple risk indicator for segmentation.
4. Provide insights that can be monitored via a dashboard.

---

## ❓ Business Questions
This project answers questions such as:
- What is the overall prevalence of heart disease?
- How does prevalence vary by **age group**, **gender**, and **stress level**?
- Which **numeric biomarkers** show the strongest separation between groups?
- Does a combined lifestyle risk score capture meaningful differences?

---

## 📦 Dataset Overview
- Rows: **10,000**
- Columns: **21**
- Target label: **`heart_disease_status` (Yes/No)**
- Types: mix of **numeric biomarkers** and **categorical lifestyle/demographics**
- Missing values: present in several columns but small in proportion (~0.2–0.3%)

**Features include:**
- **Demographics:** age, gender  
- **Lifestyle:** smoking, alcohol_consumption, exercise_habits, stress_level, sleep_hours, sugar_consumption  
- **Clinical / biomarkers:** blood_pressure, cholesterol_level, bmi, triglyceride_level, fasting_blood_sugar, crp_level, homocysteine_level  
- **Clinical flags:** high_blood_pressure, high_ldl_cholesterol, low_hdl_cholesterol, diabetes, family_heart_disease

---

## 🧹 Data Cleaning & Preparation
Cleaning was performed in Python with these steps:

1. **Data quality checks**
   - Removed duplicates.
   - Validated numeric ranges (no negative ages, unrealistic sleep hours, etc.).
   - Standardized column names.

2. **Categorical normalization**
   - Trimmed whitespace, unified casing, and standardized category labels  
     (e.g., `yes/YES/ Yes` → `Yes`).

3. **Handling missing values**
   - Numeric columns → imputed with **median** (robust to outliers).
   - Categorical columns → imputed with **mode** or `"Unknown"` when needed.
   - Target label was **not imputed**.

4. **Feature engineering**
   - Created `age_group` buckets for clearer demographic comparison.
   - Built a lightweight lifestyle risk score.

---

## 🔍 Exploratory Data Analysis (EDA)
EDA was structured into:
1. **Target distribution**
2. **Categorical comparison** (age group, gender, stress)
3. **Numeric driver comparison**
4. **Risk score validation**

---

## ✅ Key Insights (End of EDA)

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

## 💡 Business Recommendations (Based on EDA)
Even with modest standalone signals, the analysis suggests practical actions:

1. **Use multi-factor profiling rather than single indicators**  
   Lifestyle risk appears to accumulate across behaviors, making a combined score more useful for prioritization.

2. **Monitor BMI and lifestyle score as early warning proxies**  
   Both show consistent upward shifts in the heart disease group, even if small.

3. **Include stress level as a supporting segmentation layer**  
   Stress is the clearest categorical signal; combining stress with elevated biomarkers may help identify priority groups.

---

## 🛠 Tools Used
- **Python:** pandas, numpy, matplotlib, seaborn, scipy  
- **Google Colab:** analysis environment  
- **Google Sheets (next step):** dashboarding and stakeholder monitoring

---

## 🚧 Limitations & Next Steps
- Most categorical and numeric gaps are small, suggesting the dataset may be balanced or synthetic.
- The analysis is **associative** and not causal.
- Next steps:
  - Build a monitoring dashboard for prevalence and risk distribution.
  - Explore interactions between biomarkers and lifestyle factors.
  - Validate insights on a richer or longitudinal dataset if available.

---
