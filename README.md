# W-Shape Steel Tension Member Calculator

A Python program for calculating tensile rupture strength of W-shape steel sections using AISC Chapter D provisions. The tool reads section properties from the AISC database, calculates tensile rupture values, and generates comparison charts for multiple shapes.

Developed for CIVE 202: Civil Engineering Analysis II  
University of Nebraska-Lincoln

Authors:
- Noah Morland
- Jacob Lamoureux
- Max Perry

---

## About

This project automates tensile rupture calculations for W-shape steel members connected through both flanges using welds. The program calculates:

- Shear lag factor (U)
- Effective net area (Ae)
- Nominal tensile rupture strength (Pn)
- LRFD design strength
- ASD allowable strength

The user can compare up to three W-shapes at once, and the program automatically generates two charts showing the results.

---

## Repository Contents

| File | Description |
|---|---|
| `Project_5_code.ipynb` | Main Jupyter notebook containing all calculations, functions, data cleaning, and graph generation |
| `CSV.csv` | AISC steel section property database used by the program |
| `Final_Report_5.docx` | Final written report including methodology, discussion, tables, figures, and conclusions |
| `Annotated_Code_Document.docx` | Annotated version of the code explaining important sections and engineering decisions |
| `Technical_Executive_Summary.docx` | Technical summary written for an engineering audience |
| `Nontechnical_Executive_Summary.docx` | Simplified project summary written for a non-engineering audience |
| `Scope_of_Work.docx` | Defines the project objectives, deliverables, and client requirements |
| `Gantt_Chart.pdf` | Project schedule and timeline for tasks completed during the semester |
| `Engineering_Timesheet.xlsx` | Record of work hours and task completion for each team member |
| `README.md` | Overview of the project, repository contents, and instructions for running the program |

---

## Requirements

Install the required Python packages before running:

```bash
pip install polars pyarrow matplotlib seaborn
```

| Package | Purpose |
|---|---|
| `polars` | Loads and filters the AISC section property database |
| `pyarrow` | Supports CSV/dataframe operations used by Polars |
| `matplotlib` | Creates the shear lag factor bar chart |
| `seaborn` | Creates the grouped tensile strength comparison chart |

---

## Data Source

The program uses the AISC Shapes Database from the Steel Construction Manual (16th edition). The CSV file contains section properties for steel shapes and is filtered down to W-shapes during execution.

Place the CSV file in the same folder as the notebook and name it:

```text id="1qp7ne"
CSV.csv
```

---

## Functions

### `calculate_U(x_bar, L)`

Calculates the shear lag factor using:

```text id="0d7vmr"
U = 1 - (x_bar / L)
```

Inputs:
- `x_bar` - Centroid distance in inches
- `L` - Connection length in inches

Returns:
- `U` - Shear lag factor

---

### `tensile_rupture(shape_name, L)`

Looks up a W-shape from the AISC database and calculates tensile rupture results.

Inputs:
- `shape_name` - W-shape name (example: `W14X48`)
- `L` - Connection length in inches

Outputs:
- Gross area
- Shear lag factor
- Effective net area
- Nominal strength
- LRFD strength
- ASD strength

---

## How to Run

1. Place `CSV.csv` in the same folder as the notebook
2. Open `Project_5_code.ipynb`
3. Run all notebook cells in order
4. Enter the requested shape names and connection lengths

### Example

```text id="s7d3wo"
Enter shape name for scenario 1 (e.g. W14X48): W14X48
Enter connection length for scenario 1 (in): 4
```

> Shape names are case-sensitive and must be entered in all caps.

---

## Output Charts

### Tensile Rupture Strength Comparison
Grouped bar chart comparing:
- Nominal strength
- LRFD strength
- ASD strength

### Shear Lag Factor Comparison
Bar chart showing the shear lag factor for each selected shape.

---

## Assumptions and Limitations

- `Fu` is assumed to be 65 ksi (ASTM A992 steel)
- Net area is assumed equal to gross area for welded connections
- Bolt hole deductions are not included
- The program is intended for W-shapes only

---

## References

- AISC Steel Construction Manual (16th ed.)
- AISC Shapes Database v16.0
- ASTM A992/A992M
- Segui, *Steel Design* (6th ed.)

---

## Course Information

Department of Civil & Environmental Engineering  
University of Nebraska-Lincoln  
CIVE 202: Civil Engineering Analysis II
