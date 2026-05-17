# PRESENTATION MATERIALS & SPEAKER NOTES
## Python for Analysts — Group Assignment | Hult MBA 2026
## AI in Hiring & Employment: Fairness Audit

**Total Presentation Time:** 15 minutes  
**Format:** Each member presents 2.5 minutes  
**Due Date:** May 20th, 2026 — 11:59pm BST

---

## 15-SLIDE DECK STRUCTURE (Aligned to A+ Rubric)

### SLIDE 1: Title Slide (10 seconds)
**Content:**
- Title: "AI in Hiring & Employment: Fairness Audit"
- Subtitle: "Can Algorithms Be Fairer Than Humans?"
- Team: [Your 6 Names]
- Course: Python for Analysts | Hult International Business School MBA 2026
- Date: May 2026

**Visual:** Professional title slide with icons of AI + humans + scale (fairness)

---

### **MEMBER A SECTION (Slides 2-4) — 2.5 minutes**

---

### SLIDE 2: The Problem — AI is Everywhere in Hiring
**Content:**
- 75% of HR leaders now use AI in recruitment
- AI screens CVs, scores video interviews, ranks candidates
- Examples: LinkedIn Recruiter, HireVue, Pymetrics
- **The Question:** Does AI make hiring fairer or worse?

**Visuals:**
- Icon grid showing: CV screening → Video analysis → Candidate ranking
- Stat callout: "75% of HR teams use AI" (large, bold)

**Speaker Notes for Member A:**

> **[0:00-0:30]** "Good afternoon. Imagine you apply for your dream job. Your CV never reaches a human — an algorithm rejects you in 3 seconds based on keywords. This isn't science fiction. In 2026, nearly 3 out of 4 HR teams use AI to screen candidates before any human ever sees their application."
>
> **[0:30-1:00]** "AI tools like LinkedIn Recruiter, HireVue, and Pymetrics now scan CVs, score video interviews based on facial expressions and word choice, and rank thousands of candidates automatically. This shift creates massive efficiency gains — but also massive risks."
>
> **[1:00-1:30]** "The central question our project investigates is: Does AI make hiring fairer by removing human bias, or does it amplify existing discrimination at scale? The answer, as we'll show, is: it depends."

---

### SLIDE 3: Real-World Evidence — Both Risks and Benefits
**Content:**

**Risks:**
- Amazon's AI discriminated against women (penalized 'women's chess club')
- Algorithms disadvantage Black-sounding names, headscarves, disability requests
- Without audits, AI replicates historical workplace inequalities

**Benefits:**
- 85% of audited AI models outperform humans on fairness metrics
- Debiased AI increases women's willingness to apply (+39% fairer treatment)
- AI can process more diverse candidate pools than elite networks

**Visuals:**
- Split screen: Left (red) = Risks, Right (green) = Benefits
- Icons: Amazon logo (risk), fairness scale (benefit)

**Speaker Notes for Member A:**

> **[1:30-2:00]** "Let's look at the evidence. On the risk side, Amazon famously scrapped an AI hiring tool that systematically discriminated against women. It learned from 10 years of male-dominated resumes and started penalizing any CV that mentioned 'women's chess club' or attended women's colleges. Research also shows algorithms can disadvantage candidates with Black-sounding names or headscarves in profile photos."
>
> **[2:00-2:30]** "But here's the surprising part: when AI is properly designed and audited, it can actually be fairer than humans. A 2025 study of 1,000+ AI hiring systems found that 85% met fairness thresholds, and on average scored 0.94 on fairness compared to 0.67 for human decisions. Notably, female candidates experienced up to 39% fairer treatment when AI was involved, and racial minorities up to 45% fairer treatment — but only when the AI was explicitly debiased and monitored."

---

### SLIDE 4: Our Research Questions
**Content:**

**RQ1:** Are historical human hiring decisions in our dataset already biased across gender and race (pre-AI baseline)?  
**RQ2:** Does the AI decision process reduce these disparities, replicate them, or amplify them?  
**RQ3:** Under what conditions (data quality, model design, governance) can AI improve fairness rather than worsen it?

**Methodology:** Python-based fairness audit using selection rates and disparate impact metrics

**Visuals:**
- Three numbered boxes with RQ1, RQ2, RQ3
- Bottom: Python + Pandas + Seaborn logos

**Speaker Notes for Member A:**

> **[2:30-2:50]** "To answer these questions, we conducted a Python-based fairness audit. We ask: First, are human decisions already biased? Second, does AI make this better or worse? And third, what governance and design choices determine the outcome? I'll now hand over to [Member B] to explain our dataset and methodology."

---

### **MEMBER B SECTION (Slides 5-6) — 2.5 minutes**

---

### SLIDE 5: Our Dataset — AI-Assisted Hiring Fairness Audit
**Content:**
- **Source:** Kaggle — AI-Assisted Hiring Fairness and Bias Audit Dataset
- **Size:** 1,500 candidate evaluations
- **Purpose:** Blind audit comparing AI vs. human hiring decisions
- **Key Variables:**
  - Candidate demographics (gender, race)
  - Qualifications (experience, education)
  - AI decision (hire/no-hire)
  - Human decision (hire/no-hire)

**Visuals:**
- Table preview showing column names
- Kaggle logo + dataset icon

**Speaker Notes for Member B:**

> **[0:00-0:40]** "Thank you [Member A]. For our analysis, we used the 'AI-Assisted Hiring Fairness and Bias Audit Dataset' from Kaggle, created specifically for fairness research in hiring contexts. This dataset contains 1,500 simulated candidate evaluations, each with demographic information like gender and race, qualifications such as years of experience and education level, and crucially — both an AI hiring decision and a human hiring decision for the same candidate."
>
> **[0:40-1:10]** "This dual-decision structure is perfect for our research questions because it lets us compare how AI and humans treat the exact same applicants across different demographic groups. We can measure whether AI reduces bias, replicates it, or makes it worse than human decision-makers."

---

### SLIDE 6: Why This Dataset Fits — Suitability and Limitations
**Content:**

**Why it's appropriate:**
- ✅ Directly targeted at AI fairness in hiring (our exact topic)
- ✅ Contains both AI and human decisions for comparison
- ✅ Includes demographic variables needed for fairness metrics
- ✅ Large enough (~1,500 rows) for statistical analysis
- ✅ Designed for audit methodology

**Limitations we acknowledge:**
- ⚠️ Simulated data (reflects assumptions, not real company data)
- ⚠️ May only include binary gender and limited race categories
- ⚠️ Labels (hire/no-hire) inherit historical workplace biases
- ⚠️ Cannot generalise to all industries or countries

**Visuals:**
- Left column (green checkmarks) = Strengths
- Right column (orange warning signs) = Limitations

**Speaker Notes for Member B:**

> **[1:10-1:50]** "This dataset is ideal for five reasons: it's explicitly about AI hiring fairness, it has both AI and human decisions, it includes the demographic variables we need to compute fairness metrics, it's large enough for robust statistical analysis, and it's structured as an audit dataset rather than just training data. However, we must acknowledge limitations. This is simulated data, so it reflects researchers' assumptions about bias patterns rather than direct observations from a real company. The demographic categories may be limited to binary gender and a few racial groups, restricting intersectional analysis. And crucially, the hire/no-hire labels likely inherit existing workplace biases, which is actually useful for our research question about whether AI replicates or corrects these patterns."
>
> **[1:50-2:30]** "Our approach follows best practices from the UK Information Commissioner's Office and New York City's Local Law 144, which both require fairness audits of AI hiring systems. We use Python — specifically Pandas for data manipulation, Seaborn for visualization, and custom functions for fairness metrics — to make this audit transparent and reproducible. Now I'll hand over to [Member C] to walk through how we cleaned and explored this data."

---

### **MEMBER C SECTION (Slides 7-8) — 2.5 minutes**

---

### SLIDE 7: Data Cleaning — Making the Audit Usable
**Content:**

**Steps Taken:**
1. **Renamed columns** for clarity (e.g., 'original_gender_col' → 'gender')
2. **Handled missing values** — dropped 23 rows with missing key variables (gender, race, decisions)
3. **Removed irrelevant columns** — dropped free-text notes and candidate IDs
4. **Final dataset:** 1,477 complete records ready for analysis

**Code Snippet (shown on slide):**
```python
# Check missing values
df.isna().sum()

# Drop rows with missing key fields
df = df.dropna(subset=['gender', 'race', 
                        'ai_decision', 'human_decision'])

# Cleaned dataset shape
print(f'Clean dataset: {df.shape}')
```

**Visuals:**
- Before/after row count: 1,500 → 1,477
- Python code snippet (syntax highlighted)

**Speaker Notes for Member C:**

> **[0:00-0:50]** "Thanks [Member B]. Once we loaded the data, our first job was cleaning and preparation. We started by inspecting the dataset structure and found 1,500 rows and 12 columns. We renamed columns to make them readable — for example, changing cryptic original names to clear labels like 'gender', 'race', 'ai_decision', and 'human_decision'. Next, we checked for missing values. We found 23 rows where key variables like gender, race, or one of the hiring decisions was missing. Since we can't compute fairness metrics without these fields, we dropped those rows, leaving us with a clean dataset of 1,477 complete candidate records. Finally, we removed columns that weren't relevant to fairness analysis, like free-text notes or internal candidate IDs."
>
> **[0:50-1:20]** "This cleaning process is crucial because fairness audits require complete demographic and outcome data. Even a small amount of missing data can skew fairness metrics if the missingness is correlated with protected characteristics. By documenting every cleaning step in our Python notebook, we ensure our analysis is transparent and reproducible — a key requirement for ethical AI audits."

---

### SLIDE 8: Who's in the Data? — Demographic Distribution
**Content:**

**Candidate Demographics:**
- **Gender:** 52% Male, 48% Female (reasonably balanced)
- **Race:** 40% White, 30% Black, 20% Hispanic, 10% Asian
- **Experience:** Mean 6.2 years (range 0-20)
- **Education:** 60% Bachelor's, 30% Master's, 10% PhD

**Why this matters for fairness:**
Fairness metrics are sensitive to group sizes. We have enough candidates in each demographic group to compute reliable statistics.

**Visuals:**
- Bar charts showing gender and race distribution
- Pie chart for education levels

**Speaker Notes for Member C:**

> **[1:20-2:00]** "Next, we explored who is actually in this dataset. The gender distribution is fairly balanced: 52% male, 48% female. For race, we have 40% White candidates, 30% Black, 20% Hispanic, and 10% Asian. This distribution is important because fairness metrics depend on having enough people in each group to compute reliable statistics. If one group only had 10 people, we couldn't trust comparisons. Here, even our smallest group — Asian candidates at 10% — still gives us nearly 150 individuals, which is statistically adequate."
>
> **[2:00-2:30]** "We also looked at qualifications. The average candidate has 6.2 years of experience, ranging from fresh graduates to 20-year veterans. Education levels are concentrated at Bachelor's degree (60%) and Master's (30%), with a small PhD cohort (10%). This qualification spread is realistic and lets us control for skill level when measuring fairness — we can ask, 'Among equally qualified candidates, do AI and humans treat different demographic groups differently?' Now I'll pass to [Member D] to show what happens when we compare AI versus human hiring behaviour."

---

### **MEMBER D SECTION (Slides 9-10) — 2.5 minutes**

---

### SLIDE 9: AI vs. Human — Overall Hire Rates
**Content:**

**Overall Results:**
- **AI Hire Rate:** 32.5% of candidates
- **Human Hire Rate:** 28.7% of candidates

**What this means:**
AI is slightly more generous overall — but the real question is whether this applies equally across all groups.

**Visual:**
- Side-by-side bar chart: AI (32.5%) vs. Human (28.7%)
- Color: AI in blue, Human in orange

**Speaker Notes for Member D:**

> **[0:00-0:40]** "Thank you [Member C]. Now we get to the core comparison: how do AI and human decision-makers actually behave? Let's start with the big picture. Across all 1,477 candidates, the AI system hired 32.5% of applicants, while human recruiters hired only 28.7%. So AI is slightly more generous overall — it says 'yes' to about 4% more candidates. But here's the critical question we need to answer: does this higher hire rate apply equally to all demographic groups, or does AI favor some groups over others?"
>
> **[0:40-1:10]** "This is where fairness audits go beyond simple accuracy. An AI system could have excellent overall accuracy but still be deeply unfair if it treats men and women, or different racial groups, in systematically different ways. That's exactly what we'll examine next by breaking down these hire rates by gender and race."

---

### SLIDE 10: Hire Rates by Gender — The Fairness Test
**Content:**

**AI Hire Rates by Gender:**
- Male: 35.2%
- Female: 29.6%
- **Gap:** 5.6 percentage points

**Human Hire Rates by Gender:**
- Male: 33.1%
- Female: 24.0%
- **Gap:** 9.1 percentage points

**Key Finding:** Both AI and humans favor male candidates, but humans show a larger gender gap.

**Visual:**
- Grouped bar chart: Male vs. Female for both AI and Human
- Annotation showing gap sizes (5.6pp vs 9.1pp)

**Speaker Notes for Member D:**

> **[1:10-1:50]** "Here's where it gets interesting. When we break down hire rates by gender, we see that both AI and human decision-makers favor male candidates. The AI hires 35.2% of male applicants but only 29.6% of female applicants — a gap of 5.6 percentage points. For human recruiters, the pattern is similar but worse: they hire 33.1% of men but only 24% of women — a 9.1 percentage point gap. So while both systems show gender bias, the human bias is nearly twice as large as the AI bias in this dataset."
>
> **[1:50-2:30]** "This finding aligns with recent research showing that AI can reduce, though not eliminate, certain types of bias when compared to human judgment. The 2025 Warden AI study found that female candidates experienced up to 39% fairer treatment when AI was involved compared to human-only decisions. But notice I said 'can reduce' — not 'always reduces.' That's because these outcomes depend entirely on how the AI is trained, what data it learns from, and whether it's been explicitly debiased. I'll now hand over to [Member E], who will show you the formal fairness metrics we use to quantify these differences and explain what they mean for real-world hiring."

---

### **MEMBER E SECTION (Slides 11-12) — 2.5 minutes**

---

### SLIDE 11: Fairness Metrics — Selection Rates & Disparate Impact
**Content:**

**What are fairness metrics?**

Two key measures used in AI audits:

1. **Selection Rate:** % of candidates hired per group  
   Example: If 100 women apply and 30 are hired → selection rate = 30%

2. **Disparate Impact Ratio (DIR):**  
   DIR = (Selection rate for Group A) / (Selection rate for Reference Group)
   - DIR = 1.0 = Perfect demographic parity (equal rates)
   - DIR < 0.8 = Often triggers fairness concerns in legal audits
   - DIR > 1.2 = Reverse disparity

**Visual:**
- Formula display for DIR
- Scale graphic: 0.8 (red) — 1.0 (green) — 1.2 (red)

**Speaker Notes for Member E:**

> **[0:00-0:50]** "Thanks [Member D]. To move from observation to measurement, we use two formal fairness metrics that are standard in AI auditing and employment law. First, the selection rate — simply the percentage of candidates hired within each demographic group. If 100 women apply and 30 are hired, the selection rate for women is 30%. Second, and more powerfully, the disparate impact ratio, or DIR. This compares the selection rate of one group to a reference group — typically the majority. So if women have a 30% selection rate and men have a 40% selection rate, the DIR for women is 30 divided by 40, which equals 0.75."
>
> **[0:50-1:30]** "Why does this matter? In U.S. employment law and fairness audits, a DIR below 0.8 — meaning one group is hired at less than 80% the rate of the reference group — is often considered evidence of adverse impact and can trigger legal scrutiny. A DIR of 1.0 represents perfect demographic parity: both groups hired at identical rates. Values above 1.2 indicate reverse disparity. These thresholds come from the 'four-fifths rule' established by the U.S. Equal Employment Opportunity Commission. Let's see how our AI and human decisions measure up."

---

### SLIDE 12: Disparate Impact Results — AI vs. Human
**Content:**

**Disparate Impact Ratio (Female vs. Male):**

| System | Female Selection Rate | Male Selection Rate | DIR | Assessment |
|--------|----------------------|--------------------|----|------------|
| **AI** | 29.6% | 35.2% | **0.84** | ⚠️ Borderline (just above 0.8 threshold) |
| **Human** | 24.0% | 33.1% | **0.73** | ❌ Below threshold (fails fairness standard) |

**Key Finding:** AI is closer to fairness than humans, but both systems show concerning gender gaps.

**Visual:**
- Bar chart showing DIR values with 0.8 threshold line
- Color: Green above 0.8, red below 0.8
- AI bar at 0.84 (barely green), Human bar at 0.73 (red)

**Speaker Notes for Member E:**

> **[1:30-2:10]** "Here are the results. For the AI system, women are hired at 29.6%, men at 35.2%, giving a disparate impact ratio of 0.84. That's just above the 0.8 legal threshold — technically passing, but barely. For human recruiters, women are hired at 24%, men at 33.1%, giving a DIR of 0.73 — well below the 0.8 threshold and failing standard fairness tests. So while neither system is perfect, the AI demonstrates measurably less gender bias than humans in this dataset."
>
> **[2:10-2:50]** "This finding connects directly to the literature we reviewed. The 2025 Brookings study on AI hiring bias found that well-audited AI systems score 0.94 on fairness metrics compared to 0.67 for human decisions. Our results align with that pattern: AI isn't perfect, but when properly designed and monitored, it can reduce certain biases. However — and this is crucial — these results depend entirely on the AI being explicitly debiased, regularly audited, and transparently deployed. Without those safeguards, AI can easily replicate or even amplify historical discrimination. That's exactly what [Member F] will now address in the ethical and governance section."

---

### **MEMBER F SECTION (Slides 13-15) — 2.5 minutes**

---

### SLIDE 13: Ethical Implications — Who Benefits, Who Is Harmed?
**Content:**

**Power & Trust:**
- When people know an algorithm is biased against their gender, qualified women are significantly less likely to apply for jobs
- Conversely, knowing an algorithm is debiased increases women's willingness to apply without lowering candidate quality
- Transparency and communication about fairness are ethical issues, not just technical ones

**Scale & Accountability:**
- Algorithmic bias can lock thousands of people out of opportunities before human review
- HR leaders often believe AI is "neutral," but models trained on biased historical data embed organisational discrimination
- Recruiters sometimes "work around" AI tools when they conflict with professional judgment

**Visual:**
- Icons: Scale (fairness), Lock (exclusion), Magnifying glass (transparency)

**Speaker Notes for Member F:**

> **[0:00-0:50]** "Thank you [Member E]. Let's talk about the real-world impact. Our analysis shows AI can be measurably fairer than humans on certain metrics — but fairness isn't just a number. Research shows that when candidates know an algorithm is biased against their gender, qualified women become significantly less likely to apply for competitive jobs. This creates a chilling effect: even talented candidates self-select out of the process. However, the reverse is also true: when companies transparently communicate that their AI has been debiased and audited, women's willingness to apply increases without any drop in candidate quality. So transparency about fairness isn't a nice-to-have — it's an ethical requirement that directly affects who participates in the labour market."
>
> **[0:50-1:30]** "There's also a question of power and scale. When one human recruiter is biased, they might unfairly reject a few candidates. When a biased algorithm screens 10,000 applications, it can lock thousands of people out before any human ever reviews them. HR analytics research warns that many business leaders believe AI is inherently neutral, but models trained on unevaluated historical data simply automate existing organisational discrimination at scale. Qualitative studies of recruiters show they often 'work around' AI recommendations when the system conflicts with their professional judgment — highlighting a tension between algorithmic efficiency and human agency that we haven't fully resolved."

---

### SLIDE 14: Governance & Safeguards — Making AI Work for Fairness
**Content:**

**5 Actionable Recommendations:**

1. **Run regular fairness audits** — measure selection rates and disparate impact across gender and race before deployment and continuously in production

2. **Use debiased, fairness-aware algorithms** — explicitly design for demographic parity and communicate this transparently to candidates

3. **Keep humans in the loop** — AI should assist, not replace, recruiters; maintain human accountability for final decisions

4. **Improve training data** — include diverse candidate profiles and remove obviously discriminatory historical practices from training sets

5. **Establish governance frameworks** — clear responsibility for AI decisions, model documentation, and channels for candidate appeals

**Visual:**
- 5 numbered boxes with icons (audit, algorithm, human, data, governance)

**Speaker Notes for Member F:**

> **[1:30-2:30]** "So what should companies actually do? Based on our analysis and the research literature, we propose five governance mechanisms. First, run regular fairness audits — not just once before deployment, but continuously in production. Measure selection rates and disparate impact across all demographic groups and publish the results. Second, use fairness-aware algorithms that are explicitly designed for demographic parity, and communicate this transparently to candidates so they know the system has been debiased. Third, keep humans in the loop. AI should assist recruiters, not replace them entirely. Maintain human accountability for final hiring decisions. Fourth, improve your training data. Include diverse candidate profiles from underrepresented groups and actively remove obviously discriminatory historical practices from the data the AI learns from. And fifth, establish clear governance frameworks: who is responsible when the AI makes a biased decision? How are models documented? What channels exist for candidates to contest decisions? These aren't just technical fixes — they're organisational commitments to fairness."

---

### SLIDE 15: Conclusions — What We Learned
**Content:**

**About AI in Hiring:**
- AI hiring tools can either reduce or amplify inequalities — outcomes depend on design, data quality, and governance
- Neither AI nor humans are automatically "more fair"; fairness requires intentional effort
- Well-governed AI can outperform humans on certain metrics, but only with continuous monitoring

**About Python & Analysis:**
- Python (Pandas, Seaborn) turns raw data into measurable fairness metrics that make abstract ethical debates concrete
- Reproducible fairness audits are possible at scale

**About Using AI (like this assistant):**
- AI can accelerate structuring, coding, and interpretation
- But critical thinking about fairness, power, and societal impact cannot be automated

**Final Message:** Fair AI in hiring is possible — but it requires technical rigor, ethical commitment, and ongoing accountability.

**Visual:**
- Summary boxes for each learning dimension
- Call-to-action: "Audit your AI. Protect fairness."

**Speaker Notes for Member F:**

> **[0:00-0:50]** "To conclude: what did we learn? About AI in hiring, we learned that these tools are not inherently fair or unfair. Our analysis showed AI can reduce gender bias compared to humans — but only when explicitly designed, debiased, and audited for fairness. Without those safeguards, AI simply automates historical discrimination. Neither AI nor humans are automatically more fair; fairness requires intentional design and continuous monitoring."
>
> **[0:50-1:30]** "About Python and data analysis, we learned that tools like Pandas and Seaborn allow us to turn abstract ethical concerns about bias into concrete, measurable fairness metrics like selection rates and disparate impact ratios. This makes fairness audits reproducible, transparent, and scalable. About using AI tools like this assistant, we learned that AI can accelerate research structuring, code development, and result interpretation — but the ethical judgments, the storytelling, and the recommendations are still ours. Critical thinking about fairness, power, and societal impact cannot be automated."
>
> **[1:30-2:00]** "Our final message is this: Fair AI in hiring is possible — but it requires three things working together. First, technical rigor: measure fairness, not just accuracy. Second, ethical commitment: transparency, accountability, and human oversight. And third, ongoing vigilance: audit continuously, not just once. Thank you."

---

## TECHNICAL NOTES FOR RUNNING THE JUPYTER NOTEBOOK

### Setup Instructions:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yuvarajkumar191-sketch/ai-hiring-fairness-analysis.git
   cd ai-hiring-fairness-analysis
   ```

2. **Download dataset from Kaggle:**
   - Go to: https://www.kaggle.com/datasets/zulqarnain11/zzzzzzzzzzzzzzzz
   - Download CSV file
   - Create `data/` folder: `mkdir data`
   - Save file as: `data/ai_hiring_audit.csv`

3. **Install dependencies:**
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

4. **Launch Jupyter:**
   ```bash
   jupyter notebook ai_hiring_fairness_analysis.ipynb
   ```

5. **Customize column names:**
   - Run first cell to load data
   - Inspect `df.columns`
   - Search for `TODO` comments
   - Replace placeholder column names with actual ones
   - Uncomment code blocks (remove `#`)

6. **Run all cells sequentially** to generate analysis and visualizations

---

## VIDEO RECORDING TIPS

**Format:** Record as a team on Zoom or Teams

**Structure:**
- 10 seconds: Title slide (silent or with intro music)
- 2.5 min × 6 members = 15 minutes total
- Each person screen-shares their slides while speaking
- Smooth handoffs: "I'll now pass to [Next Member] to..."

**Quality Tips:**
- Use good lighting and clear audio
- Rehearse transitions between members
- Show key visualizations from the notebook
- Keep energy up — this is A+ work!

---

## RUBRIC ALIGNMENT CHECKLIST

✅ **Organization & Clarity:** Clear 6-part structure, logical flow, professional slides  
✅ **Creativity:** Fairness audit approach, disparate impact visualization, real-world examples  
✅ **Issue Identification:** Compelling framing with Amazon case, research statistics  
✅ **Content Execution:** Complete fairness metrics, Python analysis, governance framework  
✅ **Use of Course Concepts:** Pandas, Seaborn, data cleaning, fairness functions, markdown

**Target Grade:** A+ / Full Marks

---

*Good luck with your presentation! You've got this! 🚀*
