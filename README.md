# AI Impact on Jobs & Salaries

**Author:** Kunta Vinay Kumar

An exploratory data analysis of AI and data-sector salaries, examining how compensation varies
across experience levels, role families, company sizes, and work modes — situated within the
broader context of generative AI's occupational impact.

---

## Project Overview

This project analyses `ai_jobs_salaries_clean.csv`, a cleaned dataset of 71,913 self-reported
salary records from the AI and data industry. The analysis covers:

- Salary trends by **experience level** (Entry → Mid → Senior → Executive)
- Top-paying **role families** across the AI/data landscape
- Compensation differences by **company size** (Small / Medium / Large)
- Salary parity (or lack thereof) across **work modes** (On-site / Hybrid / Remote)

Results are delivered through a Jupyter Notebook with four annotated charts, accompanied by
a full project report (`Kunta_Vinay_Kumar_ProjectReport.docx`).

---

## Dataset

| Field | Detail |
|---|---|
| **Source** | [foorilla/ai-jobs-net-salaries](https://github.com/foorilla/ai-jobs-net-salaries) |
| **Licence** | CC0 1.0 Universal (Public Domain) |
| **File used** | `ai_jobs_salaries_clean.csv` |
| **Rows** | 71,913 |
| **Columns** | 17 |

### ⚠️ Important caveats

- **Self-reported data.** All salary figures come from a community survey, not verified payroll
  records. Results reflect broad trends and should not be treated as precise market benchmarks.
- **Uneven coverage.** Some countries and niche job titles have very few rows; group averages
  for those strata carry high uncertainty.
- **`role_family` is an approximate manual mapping** derived from raw `job_title` strings. It
  is illustrative only and not an authoritative occupational classification. See `data_dictionary.md`
  for the full mapping rules.
- **`isco_group_hint` is an approximate manual mapping** to ISCO-08 occupational group codes,
  intended to enable loose alignment with AI-exposure index data. It is not authoritative and
  should be treated as a directional hint rather than a verified classification.

---

## Repository Contents

```
.
├── ai_jobs_salaries_clean.csv                  # Source dataset
├── data_dictionary.md                          # Column definitions and known limitations
├── Kunta_Vinay_Kumar_AI_Jobs_Analysis.ipynb    # Main analysis notebook (4 charts + EDA)
├── Kunta_Vinay_Kumar_ProjectReport.docx        # Full written project report
├── requirements.txt                            # Python dependencies
└── README.md                                   # This file
```

---

## Technologies

| Library | Version | Purpose |
|---|---|---|
| `pandas` | >=2.0, <3.0 | Data loading, cleaning, groupby aggregations |
| `matplotlib` | >=3.7, <4.0 | Chart rendering, axis formatting, annotations |
| `seaborn` | >=0.13, <1.0 | Statistical chart themes (barplot, boxplot, histplot) |
| `notebook` | >=7.0, <8.0 | Classic Jupyter notebook server |
| `jupyterlab` | >=4.0, <5.0 | Modern Jupyter UI (optional alternative) |

**Python:** 3.9 or higher required.

---

## Setup & Running the Project

**1. Clone or download the repository**

```bash
git clone <repository-url>
cd <repository-folder>
```

**2. Create and activate a virtual environment** *(recommended)*

```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS / Linux
source .venv/bin/activate
```

**3. Install dependencies**

```bash
pip install -r requirements.txt
```

**4. Launch the notebook**

```bash
# Classic Jupyter
jupyter notebook Kunta_Vinay_Kumar_AI_Jobs_Analysis.ipynb

# Or JupyterLab
jupyter lab Kunta_Vinay_Kumar_AI_Jobs_Analysis.ipynb
```

**5. Run all cells** — use *Kernel → Restart & Run All* to execute the full analysis from scratch.

---

## Key Highlights

- 📈 **Seniority is the strongest salary predictor.** Average pay rises consistently from
  Entry-level ($96k) → Mid-level ($131k) → Senior-level ($161k) → Executive-level ($188k),
  a spread of ~$92,000 across the four tiers.

- 🏆 **Specialised roles command the highest premiums.** AI Architect ($193k), Research
  Scientist ($178k), and ML Engineer ($177k) top the role-family rankings — roughly $45–50k
  above the overall dataset mean.

- 🏢 **Medium companies dominate the dataset and the pay table.** 95% of records (68,375 rows)
  fall in the Medium size band, with a median salary of $137,000. Large companies show a slightly
  lower median, likely reflecting a broader mix of junior and mid-level roles.

- 🌐 **Remote work carries no salary penalty.** Remote ($145k avg) and On-site ($145k avg)
  averages are virtually identical, reflecting global demand for AI talent and employers'
  willingness to pay market rates regardless of location.

- 🚩 **1,754 outliers (2.44%) were flagged and excluded from charts** using a 1.5 × IQR fence.
  They are retained in the raw data; all visualisations use the cleaned `df_clean` subset.

- ⚠️ **Coverage is uneven.** The NLP role family has only 19 records; the Hybrid work-mode
  group has 324. Treat averages for small-n groups as indicative, not definitive.

---

## References

- Salary data: **foorilla/ai-jobs-net-salaries**, CC0 1.0.
  <https://github.com/foorilla/ai-jobs-net-salaries>
- AI-exposure scores: Gmyrek, P., Berg, J., Kamiński, K., Konopczyński, F., Ładna, A.,
  Nafradi, B., Rosłaniec, K., & Troszyński, M. (2025). *Global Index of Occupational Exposure
  to Generative AI*. International Labour Organization. CC BY 4.0.
