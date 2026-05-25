# 🌎 WHO Global Suicide Statistics - Historical Trends & Forecasting
**A Data Science Project developed during the DecodeLabs Virtual Internship (Task 1 to Task 5)**

---

### 📊 Project Overview
This project conducts a comprehensive historical analysis of global suicide trends using the World Health Organization (WHO) suicide statistics dataset. Spanning 37 years and 141 countries, we explore demographic disparities, national trends, and decade-level shifts. Furthermore, we built a regression model to forecast suicide rates per 100,000 population, enabling global healthcare organizations to allocate mental health resources and run targeted intervention programs.

---

### 📂 File Structure
| File Name | Format | Description | Size |
|---|---|---|---|
| `Decodelabs_DSProject3.ipynb` | Jupyter Notebook (`.ipynb`) | End-to-end Jupyter Notebook containing Data Cleaning, multi-chart visualization, demographic trends, and regression modeling. | ~810 KB |
| `who_suicide_statistics.csv` | Comma-Separated Values (`.csv`) | Comprehensive raw WHO database containing suicide numbers and population grouped by country, year, sex, and age. | ~1.85 MB |
| `README.md` | Markdown (`.md`) | Professional project documentation, global insights, model comparison, and public policy recommendations. | - |
| `.gitignore` | Config file | Tells git to ignore common temporary and auto-generated python/jupyter files. | - |

---

### ⚙️ Cleaning & Preprocessing Pipeline
1. **Handling Missing Values**: Resolved null values in historical statistics through simple imputer models (median strategy) to preserve valid records.
2. **Rate Engineering**: Constructed the key target metric `suicide_rate` (Suicides per 100,000 population):
   $$\text{suicide\_rate} = \frac{\text{suicides\_no}}{\text{population}} \times 100,000$$
3. **Ordinal Encoding**: Encoded the `age` groups (e.g., "5-14 years", "15-24 years", etc.) to map demographic hierarchy into our forecasting models.
4. **Categorical Encoding**: Encoded `country` and `sex` features using Label Encoding.

---

### 📈 Key Global Findings & Historical Trends
- **Total Volume**: Over 8 million suicides were recorded across 141 countries in the 37-year span.
- **Massive Sex Disparity**: Males represent approximately **76%** of all global suicides, showing a consistent and severe gap across all age cohorts.
- **Age Disparity**: The suicide rate rises significantly with age, peaking in the older demographics (55-74 and 75+ age bands).
- **Peak Decade**: The 1990s marked the peak in absolute suicides globally, followed by a gradual downward trend in recent decades.
- **Top Countries by Total Volume**: The **Russian Federation** recorded the highest total absolute suicides historically.
- **Top Countries by Average Suicide Rate (per 100k)**:
  1. **Hungary** (39.68 per 100k)
  2. **Sri Lanka** (37.78 per 100k)
  3. **Lithuania** (37.69 per 100k)

---

### 🤖 Predictive Modeling: Suicide Rate Forecasting
We evaluated multiple regression models to predict the suicide rate per 100,000 population based on geographic, demographic, and temporal features (`year`, `country_enc`, `sex_enc`, `age_order`, `population`):

| Model | MAE | RMSE | $R^2$ Score |
|---|---|---|---|
| **Random Forest (Best Model)** | **4.5580** | **8.9203** | **0.7714** |
| **Gradient Boosting** | 5.2865 | 9.8482 | 0.7213 |
| **Linear Regression** | 10.5001 | 16.4748 | 0.2201 |
| **Ridge Regression** | 10.4994 | 16.4748 | 0.2201 |

*Note: Random Forest achieved an impressive $R^2$ score of 0.7714, suggesting it captured the interaction between country-specific demographic patterns and temporal trends extremely well.*

---

### 💡 Public Policy & Healthcare Recommendations
1. **Targeted Men's Mental Health Initiatives**: Design gender-specific counseling platforms and support groups to address the 76% male suicide disparity.
2. **Geriatric Mental Health Programs**: Establish proactive psychological support networks for elderly populations, who experience the highest average rates per 100k.
3. **National Suicide Hotline Infrastructures**: Prioritize resources and active hotlines in historically high-rate regions like Hungary, Lithuania, and Sri Lanka.
