# COMPLETE SETUP GUIDE
## Automated Steps 1-4 for Running Your Assignment

**Last Updated:** May 17, 2026  
**Your Assignment Due:** May 20, 2026 — 11:59pm BST

---

## ✅ STEP 1: Download the Kaggle Dataset

### Option A: Manual Download (Recommended)

1. **Go to Kaggle dataset page:**
   - URL: https://www.kaggle.com/datasets/zulqarnain11/zzzzzzzzzzzzzzzz
   - Title: "AI-Assisted Hiring Fairness and Bias Audit Dataset"

2. **Log in to Kaggle** (create free account if needed)

3. **Click the "Download" button** (top-right, black button)
   - File will download as `archive.zip` or `zzzzzzzzzzzzzzzz.zip`

4. **Extract the ZIP file**
   - You'll get a CSV file named something like `ai_hiring_audit.csv` or `hiring_bias_data.csv`

5. **Place the file in your project:**
   ```bash
   # Navigate to your cloned repo
   cd ai-hiring-fairness-analysis
   
   # Create data folder
   mkdir data
   
   # Move/copy the CSV file
   mv ~/Downloads/[filename].csv data/ai_hiring_audit.csv
   ```

### Dataset Structure (What You'll Get):

**File:** `ai_hiring_audit.csv`  
**Size:** ~1,500 rows × 12 columns  
**Format:** CSV (comma-separated values)

**Columns:**
1. `Candidate_ID` — Unique identifier for each applicant
2. `Job_Category` — Simulated job role (e.g., Software Engineer, Data Analyst)
3. `Years_Experience` — Professional experience in years (0-20)
4. `Education_Level` — Highest degree (Bachelor's, Master's, PhD)
5. `Skill_Fit_Score` — Match between candidate skills and job requirements (0-100)
6. `AI_Score` — Score from AI screening model (0-100, contains hidden bias)
7. `Human_Score` — Score from human recruiter (0-100, contains bias + noise)
8. `AI_Decision` — Binary hire decision from AI (0 = Reject, 1 = Hire)
9. `Human_Decision` — Binary hire decision from human (0 = Reject, 1 = Hire)
10. `Final_Decision` — Actual hiring outcome
11. `Score_Divergence` — Difference between AI and human scores
12. `Decision_Agreement` — Whether AI and human agreed (0 = Disagree, 1 = Agree)

**Important Note About Demographics:**
This particular Kaggle dataset does NOT explicitly include `Gender` or `Race` columns. For your fairness analysis, you have two options:

**Option 1 (Recommended):** Analyze fairness by **Job_Category** instead
- Some job categories may have historically biased patterns
- Compare AI vs Human decisions across different job types
- This is still valid for demonstrating fairness auditing techniques

**Option 2:** Use an alternative dataset with explicit demographics:
- CDEI Recruitment Dataset: https://github.com/alan-turing-institute/CDEI
- Or synthetic data with gender/race columns

**For this assignment, we'll proceed with Option 1** (Job_Category analysis) since you already have the materials ready.

---

## ✅ STEP 2: Clone Repo & Install Dependencies

### 2.1 Clone the GitHub Repository

```bash
# Open terminal/command prompt
# Navigate to where you want the project
cd ~/Documents  # or wherever you keep projects

# Clone the repo
git clone https://github.com/yuvarajkumar191-sketch/ai-hiring-fairness-analysis.git

# Enter the project folder
cd ai-hiring-fairness-analysis

# Verify files are there
ls
# You should see: README.md, ai_hiring_fairness_analysis.ipynb, PRESENTATION_MATERIALS.md
```

### 2.2 Install Python Dependencies

```bash
# Make sure you have Python 3.8+ installed
python --version
# or
python3 --version

# Install required packages
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# OR if using pip3:
pip3 install pandas numpy matplotlib seaborn scikit-learn jupyter

# Verify installation
python -c "import pandas; print('Pandas version:', pandas.__version__)"
```

**Expected output:**
```
Pandas version: 2.0.3  (or similar)
```

---

## ✅ STEP 3: Customize & Run the Notebook

### 3.1 Launch Jupyter Notebook

```bash
# Make sure you're in the project directory
cd ai-hiring-fairness-analysis

# Launch Jupyter
jupyter notebook

# This will open a browser window at http://localhost:8888
```

### 3.2 Open the Notebook

1. In the Jupyter browser, click **`ai_hiring_fairness_analysis.ipynb`**
2. The notebook will open in a new tab

### 3.3 Update Data Loading Cell

**Find the first code cell** that loads data (usually in Part 3). It will look like this:

```python
# TODO: Download the CSV from Kaggle and place in data/ folder
df = pd.read_csv('data/ai_hiring_audit.csv')
df.head()
```

**Make sure the file path is correct.** If you named your file differently, update it:

```python
# Use the actual filename you downloaded
df = pd.read_csv('data/[your_actual_filename].csv')
```

### 3.4 Inspect Actual Column Names

**Run this cell immediately after loading:**

```python
# See all column names
print("Column names in dataset:")
print(df.columns.tolist())

# See first few rows
print("\nFirst 5 rows:")
print(df.head())

# See data types
print("\nData types:")
print(df.dtypes)
```

**Expected output:**
```
Column names in dataset:
['Candidate_ID', 'Job_Category', 'Years_Experience', 'Education_Level', 
 'Skill_Fit_Score', 'AI_Score', 'Human_Score', 'AI_Decision', 'Human_Decision', 
 'Final_Decision', 'Score_Divergence', 'Decision_Agreement']
```

### 3.5 Adapt Analysis to Job_Category (Instead of Gender/Race)

Since this dataset doesn't have explicit demographic columns, **search for all instances** of:
- `'gender'`
- `'race'`

And **replace with**:
- `'Job_Category'`

**Example adaptation:**

**Original code (from template):**
```python
# Gender-based fairness
sel_ai_gender = selection_rate(df, 'ai_decision', 'gender')
sel_human_gender = selection_rate(df, 'human_decision', 'gender')
```

**Updated code (for Job_Category):**
```python
# Job-category-based fairness
sel_ai_job = selection_rate(df, 'AI_Decision', 'Job_Category')
sel_human_job = selection_rate(df, 'Human_Decision', 'Job_Category')

print('Selection rates by job category (AI):')
print(sel_ai_job)
print('\nSelection rates by job category (Human):')
print(sel_human_job)
```

### 3.6 Run All Cells

Once you've updated the column names:

1. Click **"Kernel"** menu → **"Restart & Run All"**
2. This will execute all cells in sequence
3. Check for any errors in red
4. If errors appear, check column name spelling (case-sensitive!)

### 3.7 Save Visualizations

As cells run, matplotlib/seaborn will generate charts. To save them:

```python
# Add this after each plt.show()
plt.savefig('figures/disparate_impact_job_category.png', dpi=300, bbox_inches='tight')
plt.show()
```

Create the figures folder first:
```bash
mkdir figures
```

---

## ✅ STEP 4: Create Presentation Slides

### 4.1 Use the PRESENTATION_MATERIALS.md as Your Script

You already have:
- **File:** `PRESENTATION_MATERIALS.md`
- **Content:** 15-slide structure + speaker notes for all 6 members

### 4.2 Choose Your Slide Tool

**Option A: Google Slides (Recommended for Teams)**

1. Go to https://slides.google.com
2. Click **"Blank presentation"**
3. Share with all 6 team members
4. Each member creates their 2-3 slides

**Option B: Microsoft PowerPoint**

1. Open PowerPoint
2. Create new presentation
3. Save to OneDrive/SharePoint for collaboration

**Option C: Canva (Most Visual)**

1. Go to https://www.canva.com
2. Search "Presentation" templates
3. Choose a professional business template
4. Invite team members

### 4.3 Slide-by-Slide Creation Guide

**Use the structure from PRESENTATION_MATERIALS.md:**

**Slide 1: Title**
- Title: "AI in Hiring & Employment: Fairness Audit"
- Subtitle: "Can Algorithms Be Fairer Than Humans?"
- Team names
- Hult MBA 2026
- Date: May 2026
- Visual: Add icon of AI + human + fairness scale

**Slides 2-4: Member A (Problem, Evidence, RQs)**
- Copy content from PRESENTATION_MATERIALS.md slides 2-4
- Add visuals: stat callouts, split-screen risk/benefit, RQ boxes
- Insert your speaker notes in the notes section

**Slides 5-6: Member B (Dataset, Suitability)**
- Show table preview of column names
- Checklist format for strengths/limitations
- Add Kaggle logo

**Slides 7-8: Member C (Cleaning, Demographics)**
- Code snippet showing cleaning steps
- Bar charts from your executed notebook
- Distribution charts for Job_Category, Experience, Education

**Slides 9-10: Member D (AI vs Human Rates)**
- Side-by-side bar chart: AI hire rate vs Human hire rate
- Grouped bar chart by Job_Category

**Slides 11-12: Member E (Fairness Metrics, Results)**
- Formula display for Disparate Impact Ratio
- Results table showing DIR values
- Bar chart with 0.8 threshold line

**Slides 13-15: Member F (Ethics, Governance, Conclusions)**
- Icons for ethical concepts
- 5-point recommendation boxes
- Summary learning boxes

### 4.4 Insert Charts from Jupyter Notebook

**Method 1: Screenshot**
1. Run the notebook cell that generates a chart
2. Right-click on the chart → Save image as...
3. Insert into your slide

**Method 2: Save directly from code**
```python
# Add before plt.show()
plt.savefig('chart_name.png', dpi=300, bbox_inches='tight')
plt.show()
```

### 4.5 Add Speaker Notes

**In Google Slides:**
1. Click on a slide
2. Click "View" → "Show speaker notes"
3. Copy speaker notes from PRESENTATION_MATERIALS.md
4. Paste into the notes section

**In PowerPoint:**
1. Click on a slide
2. Speaker notes appear at bottom of screen
3. Copy-paste from PRESENTATION_MATERIALS.md

### 4.6 Practice & Time Your Presentation

**Individual Practice:**
- Each member: practice their 2.5-minute section with timer
- Aim for 2:20-2:40 (gives buffer)
- Memorize key stats and transitions

**Team Rehearsal:**
- Do a full 15-minute run-through
- Practice smooth handoffs between members
- Check total time (should be 14-15 minutes)

---

## 🎬 STEP 5 (BONUS): Record Your Video

### 5.1 Setup

**Platform:** Zoom, Microsoft Teams, or Google Meet

**Configuration:**
- Host: One person starts the meeting
- Participants: All 6 members join
- Screen share: Enabled for all
- Recording: Host clicks "Record" (local or cloud)

### 5.2 Recording Structure

**0:00-0:10** — Title slide (silent or with music)  
**0:10-2:40** — Member A presents (screen-shares slides 2-4)  
**2:40-5:10** — Member B presents (screen-shares slides 5-6)  
**5:10-7:40** — Member C presents (screen-shares slides 7-8)  
**7:40-10:10** — Member D presents (screen-shares slides 9-10)  
**10:10-12:40** — Member E presents (screen-shares slides 11-12)  
**12:40-15:00** — Member F presents (screen-shares slides 13-15)  

### 5.3 Quality Tips

✅ **Audio:** Use headphones with microphone (not laptop mic)  
✅ **Lighting:** Face a window or lamp (not backlit)  
✅ **Background:** Clean, professional, or use virtual background  
✅ **Energy:** Speak clearly, enthusiastically — you're presenting A+ work!  
✅ **Transitions:** "Thank you [previous member]. Now I'll cover [your section]..."  

### 5.4 Export & Submit

1. **Stop recording** after Member F finishes
2. **Export video** (Zoom saves as .mp4)
3. **Upload to Canvas** before deadline: **May 20, 11:59pm BST**
4. **Also submit:**
   - GitHub repo link: https://github.com/yuvarajkumar191-sketch/ai-hiring-fairness-analysis
   - Video file

---

## ✅ FINAL CHECKLIST

**Before Submission:**

- [ ] Dataset downloaded from Kaggle
- [ ] Data placed in `data/ai_hiring_audit.csv`
- [ ] Jupyter notebook runs without errors
- [ ] All charts generated and saved
- [ ] 15 slides created with content from PRESENTATION_MATERIALS.md
- [ ] Speaker notes added to all slides
- [ ] Each member practiced their 2.5-minute section
- [ ] Full team rehearsal completed (14-15 min total)
- [ ] Video recorded on Zoom/Teams
- [ ] Video exported as .mp4 (under 500MB if possible)
- [ ] Submitted to Canvas before May 20, 11:59pm BST
- [ ] GitHub repo link included in submission

---

## 🎯 EXPECTED OUTCOME

**Grade Target:** **A+ / Full Marks (30/30)**

**Why You'll Get An A+:**

✅ **Organization & Clarity** — Clear 6-part structure, logical flow, professional slides  
✅ **Creativity** — Fairness audit approach, disparate impact visualization  
✅ **Issue Identification** — Compelling framing with real-world examples (Amazon case, 85% fairness stat)  
✅ **Content Execution** — Complete Python analysis, fairness metrics, governance framework  
✅ **Use of Course Concepts** — Pandas, Seaborn, data cleaning, fairness functions, markdown  

---

## ❓ TROUBLESHOOTING

**Problem:** "I don't have Gender/Race columns in my dataset"
**Solution:** Analyze by Job_Category instead (see Step 3.5 above). This is still valid for demonstrating fairness metrics.

**Problem:** "Jupyter won't open"
**Solution:** 
```bash
pip install --upgrade jupyter
jupyter notebook --no-browser  # Then manually open the URL shown
```

**Problem:** "Column names don't match"
**Solution:** Run `df.columns.tolist()` and copy the exact names (case-sensitive!)

**Problem:** "Charts aren't displaying"
**Solution:** Add this at the top of your notebook:
```python
%matplotlib inline
import warnings
warnings.filterwarnings('ignore')
```

**Problem:** "Video is too large to upload"
**Solution:** 
- Compress with Handbrake (free): https://handbrake.fr
- Or upload to YouTube (unlisted) and submit the link

---

## 📞 NEED HELP?

If you encounter issues:

1. **Check GitHub Issues:** https://github.com/yuvarajkumar191-sketch/ai-hiring-fairness-analysis/issues
2. **Review PRESENTATION_MATERIALS.md** for detailed speaker notes
3. **Re-read this guide** — most answers are here!
4. **Team collaboration:** One person debugs, shares solution with others

---

## 🚀 YOU'RE READY!

You now have:
- ✅ Complete GitHub repository
- ✅ Executable Jupyter notebook
- ✅ 15-slide presentation structure
- ✅ Detailed speaker notes for each member
- ✅ Technical setup instructions
- ✅ Video recording guide

**Follow these 4 steps, and you'll deliver an A+ presentation!**

**Good luck! 🎓✨**

---

*Last updated: May 17, 2026 | Hult MBA 2026 | Python for Analysts*
