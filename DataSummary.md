# Behavioural Questionnaire Data Summary

This page acts as a legend for data in Venture Lab. It tells you how and where to find the data you're searching for, including **what each instrument is**, **how its variables are named**, and **where to find it** in the data files. It can be used as a lookup before digging into the data dictionaries.

---

### Naming convention legend

Most questionnaire variables follow this pattern:

```
PREFIX_QQ_Y#
```

| Part | Meaning | Example |
|---|---|---|
| `PREFIX` | Instrument abbreviation (see table of instruments below) | `SDQ`, `SURPS`, `DEM` |
| `QQ` | Item/question number within the instrument, as it appears on the original questionnaire | `01`, `02`, ... |
| `Y#` | Timepoint / study year the data was collected (`Y1`–`Y5`) | `Y1` = Year 1, `Y5` = Year 5 |


### How to match a column to its dictionary entry

1. 
2. 
...
---

# **Instruments/Questionnaires**

## Substance use

### `DEPAPO_` — DEP-ADO substance use screening
- **Full name:** DEP-ADO (*Grille de dépistage de consommation problématique d'alcool et de drogues chez les adolescents*) — Québec adolescent alcohol/drug screening tool.
- **Description:** Screens lifetime and past-year use of alcohol, cannabis, and other drugs, frequency of use, and consequences of use. Produces three factor scores (alcohol & cannabis, other drugs, consequences) plus a total score.
- **Timepoints:** Y1–Y5
- **Where to find:** `coventure_data_dictionary.csv`, `instrument == "DEPAPO_"`
- **Example variable:** `DEPAPO_ALC_Y2` = alcohol use item, Year 2

---

## Data Dictionary Stucture

| Field | Meaning |
|---|---|
| `instrument` | Parent instrument/questionnaire name |
| `variable_name` | Exact variable name (matches `AllDataWide` base name, before the `_Y#` suffix) |
| `variable_raw_derived` | Whether the variable is a `raw` item or a `derived` (computed) score |
| `value_type` / `data_type` | Variable type (character, integer, float, boolean...) |
| `num_levels` | Number of response categories, if applicable |
| `question_en` / `question_fr` | The question text, in English / French |
| `answer_choices_en` / `answer_choices_fr` | Response options, in English / French |
| `answer_code` | Numeric coding of the response options |
| `jump_rules` | Skip-logic rules applied during administration |
| `data_source` | System the data was collected through (psytools, eprime, DAWBA, pen and paper) |
| `raw_data_location` | Where the raw output lives (Excel, eprime) |
| `calculation` | Formula used to compute derived scores |
| `value_details` | Notes on valid value ranges |
| `timepoints` | Which study timepoints this variable was collected at |
| `notes_(subscales)` | Subscale name or other notes |
| `min_value` / `max_value` | Valid value range |

---
