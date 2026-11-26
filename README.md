# Replication Package: Non-Technical Debt Categories and Their Shared Root Causes

Replication package for the paper "Non-Technical Debt Categories and Their Shared Root Causes in Software Development Projects", submitted to the 6th International Conference on Informatics and Software Engineering (IISEC 2027).

The paper reviews 20 primary studies to identify the categories of non-technical debt (NTD) and their root causes, and to assess whether the categories are orthogonal, i.e. whether each root cause belongs to only one category. This package contains the extracted and coded data and the full-resolution figures, so every number in the results can be traced back to the study it came from.

## Contents

```
├── data/NTD_replication_data.xlsx   extracted and coded data (5 sheets)
└── figures/
    ├── Fig.1.png     screening process
    ├── Fig.2.png     studies by year, data collection method and NTD category
    ├── Fig.3.png     root causes shared by each pair of NTD categories
    ├── Fig.4.a.png   root causes mapped to NTD categories
    └── Fig.4.b.png   root causes grouped into themes and mapped to NTD categories
```

## Reading order

| Step | Where | What it contains |
|---:|---|---|
| 1 | `Fig.1.png` | How 1138 search records were reduced to 20 primary studies. |
| 2 | Sheet `Primary Studies` | The 20 studies with their Study ID (1–20), year, research approach, data collection method, quality ratings and full citation. |
| 3 | Sheet `Criteria for QA` | The eight quality criteria (QC1–QC8). Each was rated Yes (1), Partially (0.5) or No (0); studies scoring 4 or more out of 8 were included. |
| 4 | Sheet `Root Cause Expressions` | Root causes as the authors of each study worded them (*root cause expressions*), under the NTD category they were reported for. |
| 5 | Sheet `Coding` | How each expression was coded into a *normalized root cause* (an underlying condition shared by one or more expressions) and a *theme* (a group of related root causes). |
| 6 | Sheet `Root Cause Definitions` | One row per normalized root cause: code, theme, definition, Study IDs and NTD categories. |
| 7 | `Fig.2.png`–`Fig.4.b.png` | The figures of the paper, all of which can be recomputed from the `Coding` sheet. |

## The data file

### Primary Studies

One row per primary study. The Study ID is used in every other sheet and on the mind maps.

| Column | Content |
|---|---|
| Study ID | 1–20 |
| Name | Title of the study |
| Year, Research Approach, Data Collection Method | Demographic attributes (Fig. 2a and 2b) |
| QC1–QC8 | Quality rating per criterion: Y = Yes (1), P = Partially (0.5), N = No (0) |
| Score | Sum of the eight ratings, out of 8 (inclusion threshold: 4) |
| Full Citation | Full reference of the study |

### Criteria for QA

The eight quality criteria (QC1–QC8), adapted from Dybå and Dingsøyr and from Kitchenham and Charters, with the Y/P/N scoring used in `Primary Studies`.

### Root Cause Expressions

The raw extraction. Each column is one NTD category, and each cell holds one root cause expression exactly as the study's authors worded it, under the category they reported it for. A study with many expressions continues over several rows, so an empty cell only means that the study has no further expressions for that category. The sheet holds 270 expressions from 19 studies.

| Column | Content |
|---|---|
| Study ID, Title | The study the expressions come from |
| People Debt … Management Debt | One column per NTD category |

### Coding

The core of the analysis: one row per assignment of an expression to a normalized root cause. An expression that describes more than one condition appears on several rows. For example, *time pressure* in study 3 was coded both as `TS14` (workload imbalance) and as `PP2` (deadline pressure). The 270 expressions give 374 rows, coded into 68 normalized root causes under 51 themes.

| Column | Content |
|---|---|
| Study ID | The study the expression comes from |
| NTD Category | The category under which the study reported it |
| Root Cause Expression | The expression, as in `Root Cause Expressions` |
| Root Cause Code | Code of the normalized root cause it was assigned to |
| Normalized Root Cause | Label of that root cause |
| Theme | Theme the root cause belongs to |

### Root Cause Definitions

One row per normalized root cause (68 rows), summarising the `Coding` sheet.

| Column | Content |
|---|---|
| Code | Root cause code, as in `Coding` |
| Theme | Theme of the root cause |
| Normalized Root Cause | Label used in Fig. 4 |
| Definition | Short definition capturing the shared meaning of its expressions |
| Study IDs | Studies in which at least one of its expressions was found |
| NTD Categories | Every category under which at least one of its expressions was reported; root causes with more than one are the 44 multi-category root causes |

## Worked example

Filtering the `Coding` sheet for code `HC1` gives six expressions, among them *lack of domain knowledge* (study 14, people debt) and *lack of knowledge* (study 2, social debt). Although they were reported under different categories, they describe the same condition and were merged into the normalized root cause *knowledge and domain expertise gaps*, under the theme *capability and expertise*. Because its expressions were reported under both people debt and social debt, `HC1` is linked to both categories and is counted in the people–social cell of Fig. 3.

## Reading the figures

- **Fig. 2c** counts, for each NTD category, the studies with at least one expression reported under it in the `Coding` sheet.
- **Fig. 3** shows on the diagonal the number of root causes linked to each category, and in the other cells the number linked to both categories of the row and column.
- **Fig. 4a** places the NTD categories in the middle and the root causes on both sides. The numbers on each line are the Study IDs that reported the root cause under that category.
- **Fig. 4b** adds the themes between the categories and the root causes. The coloured chips on each root cause show its categories: lilac social, light blue process, yellow people, teal organisational, orange infrastructure, pink documentation, green management.

Figs. 4a and 4b are provided at full resolution, so labels that are too small in the printed paper can be read by zooming in.
