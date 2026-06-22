# Opaque_wall_prioritisation_CRITIC_TOPSIS

This repository contains the Python code used to prioritise Passive Envelope Design Features (PEDFs) for opaque walls using the CRITIC (weighting) and TOPSIS (ranking) multi-criteria decision-making methods. This is the analytical component of a  research on identifying and prioritising PEDFs for energy-efficient building design in the Indian climate.

---

## What the code does

1. Loads survey responses from two data sources — architect survey (n=274) 
   and expert panel (n=14)
2. Constructs a decision matrix of 11 PEDFs across four evaluation criteria:
   - C1: Frequency of usage (architect survey)
   - C2: Difficulties faced / ease of use (architect survey, inverse criterion)
   - C3: Need for early design tool (architect survey)
   - C4: Expert opinion on energy performance (expert panel)
3. Applies a reliability scaling factor (1/SE) to each criterion to account 
   for differences in sample size and response consistency
4. Derives objective criteria weights using the CRITIC method
5. Ranks the 11 PEDFs under three evaluation cases using TOPSIS:
   - Case 1 (Urgent Need): all criteria maximised
   - Case 2 (Emerging Tech): frequency treated as cost criterion
   - Case 3 (Easy Baseline): difficulty and tool need treated as cost criteria
6. Calculates Cronbach's Alpha for internal consistency validation
7. Produces visualisations: decision matrix heatmap, CRITIC weight 
   distribution, and TOPSIS ranking comparison

---

## Inputs

| File | Description | Source |
|------|-------------|--------|
| `Survey1.xlsx` | Architect survey responses (n=274) covering C1, C2, C3 | Google Forms export |
| `Survey2.xlsx` | Expert panel responses (n=14) covering C4 | Google Forms export |

**Survey1.xlsx column structure:**
- Columns 7–17: C1 Frequency of usage (Likert scale)
- Columns 19–29: C2 Difficulties faced (categorical/checkbox)
- Columns 30–40: C3 Need for design tool (Likert scale)

**Survey2.xlsx column structure:**
- Columns 5–15: C4 Expert energy performance scores (Likert scale)

---

## Outputs

| Output | Description |
|--------|-------------|
| Decision matrix | 11×4 table of raw criterion scores per PEDF |
| CRITIC weights | Objective weight (%) assigned to each criterion |
| TOPSIS rankings | Rank of each PEDF under all three cases |
| TOPSIS scores | Closeness coefficients for each PEDF per case |
| Cronbach's Alpha | Internal consistency score for each criterion group |
| Heatmap | Visual decision matrix with relative performance index |
| Weight chart | Stacked bar chart of CRITIC weight distribution |

---

## How to run

### Local (Jupyter Notebook)
1. Clone this repository:
```bash
   git clone https://github.com/your-username/PEDF-prioritisation-CRITIC-TOPSIS.git
```
2. Install dependencies:
```bash
   pip install pandas numpy matplotlib seaborn openpyxl
```
3. Place `Survey1.xlsx` and `Survey2.xlsx` in the same folder as the notebook
4. Open and run the notebook in Jupyter

---

## Dependencies

| Package | Purpose |
|---------|---------|
| `pandas` | Data loading and matrix operations |
| `numpy` | Numerical calculations |
| `matplotlib` | Visualisation |
| `seaborn` | Heatmap and chart styling |
| `openpyxl` | Excel file reading |

---

## Citation

If you use this code, please cite:

> Pant, P. et al. (202X). Prioritising Passive Envelope Design Features for Opaque Walls: A CRITIC-TOPSIS Approach. *Journal Name*. DOI: xxx

Code repository DOI: [Zenodo DOI here once registered]

---

## License

MIT License — free to use and adapt with attribution.

---

## Contact

For questions about the methodology or data, contact: priyankita_p@ar.iitr.ac.in
