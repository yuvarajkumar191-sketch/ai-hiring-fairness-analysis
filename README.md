# AI in Hiring & Employment: Fairness Audit
### Python for Analysts — Group Assignment | Hult International Business School MBA 2026

![Python](https://img.shields.io/badge/Python-3.10-blue) ![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange) ![Status](https://img.shields.io/badge/Status-Complete-green)

---

## Project Overview

This project investigates how Artificial Intelligence affects **hiring and employment**, with a specific focus on **fairness, bias, and equitable access** to jobs. We analyse an AI-assisted hiring audit dataset to compare AI and human hiring decisions across demographic groups, compute fairness metrics, and provide evidence-based recommendations for ethical AI deployment in recruitment.

**Assignment Due:** May 20th, 2026 — 11:59pm BST  
**Course:** Python for Analysts  
**Institution:** Hult International Business School, London

---

## Team Members & Responsibilities

| Person | Part | Responsibility |
|--------|------|----------------|
| Member A | Part 1 | Topic Research & Problem Framing |
| Member B | Part 2 | Data Collection & Documentation |
| Member C | Part 3a | Data Cleaning & Demographic EDA |
| Member D | Part 3b | EDA: AI vs Human Decision Analysis |
| Member E | Part 4 | AI Impact & Fairness Metrics Analysis |
| Member F | Part 5 & 6 | Ethics, Recommendations & Presentation Design |

---

## Dataset

**Source:** [AI-Assisted Hiring Fairness and Bias Audit Dataset — Kaggle](https://www.kaggle.com/datasets/zulqarnain11/zzzzzzzzzzzzzzzz)  
**Size:** ~1,500 records of simulated candidate evaluations  
**Purpose:** Blind audit comparing AI-based resume screening vs. human decisions to study potential bias patterns across demographic groups.

### Why This Dataset?
- Directly targeted at AI fairness in hiring — matches our research topic exactly
- Contains both AI decisions and human decisions, enabling direct comparison
- Includes demographic variables (gender, race) needed for fairness metrics
- Large enough (~1,500 rows, 10+ columns) to compute statistically meaningful fairness statistics
- Designed as an audit dataset, supporting ethical evaluation focus

---

## Research Questions

1. **RQ1:** Are historical human hiring decisions in this dataset already biased across gender and race (pre-AI baseline)?
2. **RQ2:** Does the AI decision process reduce these disparities, replicate them, or amplify them?
3. **RQ3:** Under what conditions (data quality, model design, governance) can AI in hiring improve fairness rather than worsen it?

---

## Project Structure

```
ai-hiring-fairness-analysis/
├── README.md                          # This file
├── ai_hiring_fairness_analysis.ipynb  # Main Jupyter Notebook (all 6 parts)
└── data/
    └── ai_hiring_audit.csv            # Dataset (download from Kaggle link above)
```

### Notebook Structure

| Section | Part | Content |
|---------|------|---------|
| 1 | Part 1 | Topic Research & Problem Framing |
| 2 | Part 2 | Data Collection & Documentation |
| 3 | Part 3 | Data Cleaning & Exploratory Analysis |
| 4 | Part 4 | AI Impact & Fairness Metrics |
| 5 | Part 5 | Ethical & Societal Evaluation |
| 6 | Part 6 | Recommendations & Conclusions |

---

## Key Findings (Summary)

- **Pre-AI bias exists:** Historical human hiring decisions in the dataset show measurable disparities across gender and race groups before any AI involvement.
- **AI can amplify or replicate bias:** When trained on biased historical data, AI models tend to replicate and sometimes amplify existing human biases rather than correcting them.
- **Debiasing alone is insufficient:** Simply removing protected attributes (gender, race) from model features does not eliminate bias, because other correlated features (e.g., university, career gaps) act as proxies.
- **Well-governed AI can be fairer:** When audited, debiased, and transparently communicated to candidates, AI hiring tools can outperform humans on certain fairness metrics.
- **Governance matters most:** Technical fixes must be paired with organisational accountability, regular auditing, and candidate transparency to produce fair outcomes.

---

## Visualisations Produced

1. Candidate distribution by gender and race (bar charts)
2. Overall hire rates: AI vs Human (comparative bar chart)
3. Hire rates by gender: AI vs Human (grouped bar chart)
4. Hire rates by race: AI vs Human (grouped bar chart)
5. Disparate Impact Ratio by gender: AI vs Human (bar chart with 1.0 reference line)
6. Disparate Impact Ratio by race: AI vs Human (bar chart with 1.0 reference line)
7. Fairness scenario comparison: with vs without protected attributes (debiasing scenario)
8. Correlation heatmap of numerical features
9. Experience distribution by gender (box plot)
10. AI score distribution by demographic group (violin/KDE plot)

---

## How to Run

```bash
# 1. Clone this repository
git clone https://github.com/yuvarajkumar191-sketch/ai-hiring-fairness-analysis.git
cd ai-hiring-fairness-analysis

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# 3. Download dataset from Kaggle and place it in the data/ folder as:
#    data/ai_hiring_audit.csv

# 4. Launch Jupyter Notebook
jupyter notebook ai_hiring_fairness_analysis.ipynb
```

---

## Dependencies

```python
pandas >= 1.5
numpy >= 1.23
matplotlib >= 3.6
seaborn >= 0.12
scikit-learn >= 1.2
jupyter
```

---

## Working with AI Tools

This project was developed with the support of **Perplexity Comet (AI assistant)**. Below are examples of how we used AI to structure and build this project.

### Prompt Engineering Examples

**Prompt 1 — Project planning:**
> "We are 6 MBA students at Hult International Business School. Our assignment is to investigate how AI affects a social issue using Python. We chose hiring and employment. Our dataset is the AI-Assisted Hiring Fairness and Bias Audit Dataset from Kaggle. We need all 6 project parts completed — topic framing, data documentation, cleaning & EDA, AI impact analysis with fairness metrics, ethical evaluation, and recommendations. Build everything for all 6 team members, optimised to meet the A+ rubric criteria for organisation, creativity, issue identification, content execution, and use of course concepts."

**Prompt 2 — Fairness metrics code:**
> "Write Python functions using pandas and seaborn to compute selection rates and disparate impact ratios by gender and race, comparing AI decisions versus human decisions. Include clear markdown explanations using chain-of-thought reasoning that a non-technical audience can follow."

**Prompt 3 — Debiasing scenario:**
> "Using scikit-learn logistic regression, show how removing protected attributes (gender, race) from features changes the disparate impact ratio for hiring predictions. Explain in plain English whether this improves fairness and why or why not."

### How AI Helped Us
- **Structured the entire project** into 6 distinct, individually-owned parts matching the assignment brief
- **Designed fairness metrics** (selection rates, disparate impact ratios) and connected them to real-world hiring audit literature
- **Translated complex ethical literature** into concrete, actionable governance recommendations
- **Improved code quality** through chain-of-thought reasoning and use of technical vocabulary (disparate impact, demographic parity, fairness-aware algorithms)
- **Connected Python analysis** to broader societal implications and ethical frameworks

### AI Usage Reflection
Using AI as a co-analyst accelerated structuring and coding, but every result required human verification and interpretation. The ethical judgements, storytelling for the presentation, and final conclusions are our own. AI is a powerful tool for Python-assisted analysis, but it cannot replace critical thinking about fairness, power, and societal impact — which is precisely what this project is about.

---

## Ethical Note

This project analyses simulated data for educational purposes. All findings are framed in terms of fairness metrics and governance frameworks, with the goal of promoting equitable AI deployment in hiring — not to target any individual, organisation, or demographic group.

---

## License

MIT License — for educational and academic use.

---

*Hult International Business School | MBA 2026 | Python for Analysts | Group Assignment*
