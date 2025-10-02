**🧪 A/B Testing with Python – E-commerce Conversion Analysis**
**📊 Project Overview**
This project demonstrates a complete A/B testing workflow using Python, focusing on conversion rate optimization for an e-commerce website. The goal is to analyze whether a new website design improves conversion rates compared to the existing one, using real-world statistical methods and data analysis techniques.

**📁 Dataset**
The project uses an A/B test dataset containing results from two user groups:

Control group – Visitors who saw the original design

Treatment group – Visitors who saw the new design

Each record includes:

group: Control or Treatment

converted: Whether the user converted (1 or 0)

device: User device type (e.g., Desktop, Mobile)

session_duration: Time spent on the website

**📊 Dataset Source: Kaggle – AB Testing Dataset**

**🔬 Analysis Workflow**
**1. 🧠 Hypothesis Formulation**
Null Hypothesis (H₀): New design conversion rate ≤ Old design

Alternative Hypothesis (H₁): New design conversion rate > Old design

**2. 📊 Statistical Analysis**
✅ Two-Proportion Z-Test
Used to compare conversion rates between control and treatment groups.

python
Copy code
z_score, p_value = stats.proportions_ztest(
    [conv_new, conv_old],
    [n_new, n_old],
    alternative='larger'
)
Result: Z = 4.74, p < 0.000001

**✅ Conclusion:** Reject H₀ – New design significantly improves conversions.

**📈 Confidence Interval Visualization**
Plotting 95% confidence intervals for conversion rates confirms statistical significance.

**3. 📊 Advanced Testing Scenarios**
📉 Chi-Square Test (Categorical Relationships)
Test if device type affects conversion:

python
Copy code
chi2, p, dof, _ = stats.chi2_contingency(contingency_table)
Result: p = 0.31 → No significant device effect.

📏 T-Test (Continuous Metrics)
Compare session durations between groups:

python
Copy code
t_stat, p_val = stats.ttest_ind(duration_treatment, duration_control)
Result: p = 0.62 → No significant difference in session duration.

**4. 📐 Experimental Design**
Sample Size Calculation: Using statsmodels power analysis

Randomization Checks: Ensuring demographic/device distribution balance

**📊 Business Insights & Recommendations**
**📈 Key Findings**
New design increased conversions by +1.5% (p < 0.0001)

Estimated annual revenue impact: +$180,000

No negative impact on session duration

**✅ Recommendations**
Roll out the new design to all users

Monitor mobile conversion rates (25% lower than desktop)

**🧠 Skills Demonstrated**
✅ Hypothesis Testing (Z-test, T-test, Chi-Square)

✅ Confidence Interval Estimation

✅ Experimental Design & Power Analysis

✅ Business Impact Translation

✅ Data Visualization & Reporting

**📈 Alternative Experiment Ideas**
💰 Pricing Test – “Do premium packages increase revenue?”

✉️ Email Campaign – “Does personalization improve open rate?”

🌙 Feature Test – “Does dark mode reduce complaints?”

**🛠️ Technologies Used**
Python 🐍

Pandas & NumPy – Data manipulation

SciPy & Statsmodels – Hypothesis testing

Matplotlib – Visualization

Jupyter Notebook – Analysis environment

**📁 Repository Structure**
python
Copy code
📂 AB-Testing-Project/
├── ab_data.csv.zip                 # Raw dataset
├── ab_test_summary_results.csv     # Summary results
├── analysis_notebook.ipynb         # Full analysis workflow
├── README.md                       # Project documentation
└── results_visualizations/         # Plots and charts
🚀 How to Run
Clone this repository:

bash
Copy code
git clone https://github.com/yourusername/ab-testing-python.git
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Run the analysis notebook:

bash
Copy code
jupyter notebook analysis_notebook.ipynb
**📜 License**
This project is licensed under the MIT License – feel free to use, modify, and share.
