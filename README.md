# 🧠 NESARC Research: Social Anxiety Disorder (SAD) & Family Behavioral History  

*A data-driven exploration of the relationship between SAD severity and family history of behavioral problems.*

## 📌 Overview  

This project was developed as part of the **Data Analysis and Interpretation Specialization** from **Wesleyan University** on **Coursera**. It explores the relationship between **Social Anxiety Disorder (SAD)** and a family history of behavioral problems using data from the **National Epidemiologic Survey on Alcohol and Related Conditions (NESARC)**. The analysis applies **statistical hypothesis testing**, including **ANOVA, Chi-Square test, Pearson Correlation, and moderation analysis (Gender as a moderator)** to assess these relationships.

## 📂 Dataset  
- **Source**: [National Epidemiologic Survey on Alcohol and Related Conditions (NESARC)](https://www.nesarc.org)  
- **File**: `source/NESARC Dataset.csv`  
- **Size**: 252.61 MB *(tracked with [Git LFS](https://git-lfs.github.com/))*  
- **Key Variables**:  

| Variable                   | Type          | Description                                                                 |
|---------------------------|---------------|-----------------------------------------------------------------------------|
| `SAD_score`                | Numerical     | Composite score derived from SAD-related survey responses.                  |
| `SAD_spectrum`             | Categorical   | **Low (≤2)**, **Medium (2-5)**, **High (>5)** severity categories.         |
| `behavior_problems_count`  | Numerical     | Number of relatives with behavioral problems.                              |
| `relatives_with_problems`  | Binary (Y/N)  | Presence of ≥1 relative with behavioral problems.                          |

## 🎯 Objectives  
1. **Primary**: Determine if family history of behavioral problems correlates with higher SAD severity.  
2. **Secondary**: Assess if **gender** moderates this relationship.  

## 🔍 Methodology  

### 1. Data Preprocessing  
- **Cleaning**: Removed missing values and standardized variables.  
- **Feature Engineering**:  
  - Created `SAD_score` from symptom-related survey responses.  
  - Binned `SAD_score` into **Low/Medium/High** categories.  
  - Derived `relatives_with_problems` from `behavior_problems_count`.  

### 2. Statistical Analysis  

#### **ANOVA: SAD Spectrum vs. Behavior Problems Count**  
A one-way ANOVA revealed significant differences in behavior problems across SAD severity groups:  

| Source          | Sum Sq   | df  | F      | p-value       |
|-----------------|----------|-----|--------|---------------|
| SAD_spectrum    | 125.78   | 2   | 22.24  | **2.48e-10**  |
| Residual        | 10919.14 | 3862| –      | –             |

**Post-hoc Tukey's HSD**: All group pairs showed significant differences (p < 0.05).  

#### **Chi-Square Test: Relatives With Problems vs. SAD Spectrum**  
- **χ² = 34.56** *(p = 3.13e-08)*  
- **Cramér's V = 0.095** (small effect size)  

*Conclusion*: Significant association between family history and SAD severity.  

#### **Pearson Correlation: SAD Score vs. Behavior Problems Count**  
- **r = 0.08** *(p = 3.82e-07)*  
- **r² = 0.0067** (0.67% variance explained)  

*Conclusion*: Weak but statistically significant correlation.  

#### **Moderation Analysis: Gender as a Moderator**  
An ANOVA with interaction terms tested if gender moderates the SAD-behavior relationship

**Key Findings**:  
- Interaction term **p = 0.187** → Gender does not significantly moderate the relationship.  
- Main effects of `SAD_spectrum` remain significant.  

## 📁 Repository Structure  

```
NESARC_research/
├── source/                  # Raw data (tracked via Git LFS)
│   └── NESARC Dataset.csv
├── .gitattributes           # Git LFS configuration
├── DMV.ipynb                # Jupyter Notebook (full analysis)
├── LICENCE                  # MIT Licence
├── README.md                # Project documentation
└── requirements.txt         # Python dependencies
```

## 🛠️ Installation & Usage  

### 1. Clone the Repository  
```bash
git clone https://github.com/PogloLopez/nesarc_research.git
cd nesarc_research
```

### 2. Install Git LFS & Download Data  
```bash
git lfs install   # Set up Git LFS
git lfs pull      # Download dataset
```

### 3. Set Up a Virtual Environment  
```bash
python -m venv .venv
source .venv/bin/activate  # Mac/Linux
.\.venv\Scripts\activate   # Windows
```

### 4. Install Dependencies  
```bash
pip install -r requirements.txt
```

### 5. Run the Analysis  
Launch Jupyter Notebook:  
```bash
jupyter notebook DMV.ipynb
```

## 📜 License  
This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.  

---

*💡 For questions or collaborations, contact [Pablo López](mailto:poglolopez@gmail.com) or connect on [LinkedIn](https://linkedin.com/in/pablo-a-lopez-s).*  
