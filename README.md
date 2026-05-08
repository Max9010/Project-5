# Project-5: W-Shape Steel Tension Member Analysis

**CIVE 202: Civil Engineering Analysis II**  
University of Nebraska-Lincoln  
Noah Morland, Jacob Lamoureux, Max Perry

---

## About

A Python tool that calculates the tensile rupture strength of W-shaped steel sections using AISC Chapter D. The user enters up to three W-shape names and a connection length, and the program computes the shear lag factor, effective net area, nominal strength, and both LRFD and ASD design strengths. Results are displayed as printed summaries and two comparison charts.

---

## Files

| File | Description |
|------|-------------|
| `Project_5_code.ipynb` | Main Jupyter Notebook with all code |
| `CSV.csv` | AISC section property database (required to run) |
| `Final_Report_5.docx` | Full written report with results and analysis |

---

## Requirements

```bash
pip install polars pyarrow matplotlib seaborn
```

---

## How to Use

1. Place `CSV.csv` in the same folder as `Project_5_code.ipynb`
2. Open the notebook and run all cells in order
3. Enter a W-shape name and connection length when prompted for each of the three scenarios

**Example:**
```
Enter shape name for scenario 1 (e.g. W14X48): W14X48
Enter connection length for scenario 1 (in): 4.0
```
**Note:** Shape names must be in all caps — e.g. `W14X48`, not `w14x48`
