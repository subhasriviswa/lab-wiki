# Proventure Data Dictionary — Clinical, Cognitive & Substance Use Battery

This page acts as a legend for Proventure. Its data dictionary (`Proventure_Data_Dictionnary_2026-04-09.xlsx`) is a raw **Psytools export** (one sheet per questionnaire block, there are both English/French sheets),**

---

### Naming convention legend

Most questionnaire variables (variable_name) follow this pattern:

```
PREFIX_QQ
```

| Part | Meaning | Example |
|---|---|---|
| `PREFIX` | Instrument abbreviation (see table of instruments below) | `SDQ`, `SURPS`, `DEM` |
| `QQ` | Item/question number within the instrument, as it appears on the original questionnaire | `01`, `02`, ... |

---

## Instrument index

**Demographics & sessions:** [DEM](#dem--demographics-proventure) · [UIC](#uic--unique-identifier-code)

**Cognitive tasks:** [WASI-II](#wasi-ii--wechsler-abbreviated-scale-of-intelligence) · [WMS-IV subscale](#wms-iv-subscale--verbal-paired-associates) · [Theory of Mind](#thegory-of-mind--combined-stories-test) · [ER-40](#er-40--emotion-recognition-task) · [Dual Task](#dual-task-discontinued) · [WCST](#wcst--wisconsin-card-sorting-test) · [PALP](#palp--stop-or-go-task)

**Clinical assessments:** [CAARMS](#caarms--comprehensive-assessment-of-at-risk-mental-states) · [DIGS](#digs--diagnostic-interview-for-genetic-studies) · [SOFAS](#sofas--social-and-occupational-functioning-scale) · [DAWBA](#dawba--development-and-well-being-assessment-proventure)

**Mental health & psychopathology:** [CAPE-42](#cape-42--community-assessment-of-psychic-experience) · [PSYCHOTIC / APSS-PLE](#psychotic--apss-ple--thoughts-and-feelings-questionnaire) · [PHQA](#phqa--patient-health-questionnaire-adolescents)

**Psychosocial:** [PSQI](#psqi--pittsburgh-sleep-quality-index)

**Substance use:** [DEP-ADO](#dep-ado--dep-ado-substance-use-screening-proventure) · [CEQ](#ceq--cannabis-experience-questionnaire) · [MMM](#mmm--marijuana-motives-measure) · [SMOKE](#smoke--hooked-on-nicotine-questionnaire) · [SURPS](#surps--substance-use-risk-profile-scale-proventure) · [TLFB](#tlfb--timeline-followback)

---

## Demographics & sessions

### `DEM_` — Demographics (Proventure)
- **Description:** Gender, sex-specific items, grade level, school absences, household composition, screen-time habits, and physical measurements (height/weight).
- **Source:** Proventure_Data Dictionary_2026-04-09 (PROVENTURE_Q1_EN)
- **Example variable:** `DEM_08` = "How much pocket money do you get from your parent/guardian each week?"
- **Also found in:** Coventure/NeuroVenture (`DEM_` — see [Demographics & sessions](#demographics--sessions)). Item wording overlaps but is not identical across studies.

### `UIC_` — Unique Identifier Code
- **Description:** set of questions (mother's first initial, father's first initial, date of birth, last letter of first name, number of older siblings) used to generate an anonymous linking code across surveys/sessions. 
- **Source:** Proventure_Data Dictionary_2026-04-09 (PROVENTURE_Q1_EN)
- **Also found in:** Coventure/NeuroVenture data dictionary— `UIC_1`–`UIC_5` 

---

## Cognitive tasks

### `WASI-II` — Wechsler Abbreviated Scale of Intelligence
- **Description:** General intelligence battery producing Verbal IQ (Vocabulary + Similarities subtests) and Performance IQ (Block Design + Matrix Reasoning subtests). A related Digit-Symbol/Coding task (from the Weschler adult intelligence scale battery) measuring processing speed is also administered.
- **Timepoints/notes:** discontinued after COVID
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Reference:** Wechsler, D. (2011). *Wechsler Abbreviated Scale of Intelligence–Second Edition (WASI-II)*. San Antonio, TX: NCS Pearson.

### `WMS-IV subscale` — Verbal Paired Associates
- **Description:** Verbal memory subtest (Verbal Paired Associates I & II) from the Wechsler Memory Scale, Fourth Edition.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY

### `Theory of Mind` — Combined Stories Test
- **Description:** Measures ability to infer others' mental states. Participants read 20 short stories and answer questions about characters' mental states.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Reference:** Achim, A. M., Ouellet, R., Roy, M. A., & Jackson, P. L. (2012). Mentalizing in first-episode psychosis. *Psychiatry Research*, 196(2), 207–213.

### `ER-40` — Emotion Recognition task
- **Description:** Participants view faces displaying different emotions (fear, anger, sadness, joy, surprise, disgust, neutral) and identify the emotion shown. Measures facial emotion recognition accuracy.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Reference:** Gillespie, S. M., Rotshtein, P., Wells, L. J., Beech, A. R., & Mitchell, I. J. (2015). Psychopathic traits are associated with reduced attention to the eyes of emotional faces among adult male non-offenders., Oct 7;9:552.

### `Dual Task` (discontinued)
- **Description:** Working memory span task — participants memorize and recall a series of letters, with concurrent simple arithmetic to increase task complexity. Discontinued after COVID.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Reference:** Oswald, F. L., McAbee, S. T., Redick, T. S., & Hambrick, D. Z. (2015). The development of a short domain-general measure of working memory capacity. *Behavior Research Methods*, 47(4), 1343–1355. *(battery document notes an equivalent task may be substituted)*

### `WCST` — Wisconsin Card Sorting Test
- **Description:** Executive function/cognitive flexibility task. Participants sort cards by an unstated rule (color, shape, or number) that changes periodically, and must adapt their sorting strategy based on feedback.
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_WCST_EN`)

### `PALP` — Stop or Go Task
- **Description:** Adapted Go/No-Go Passive Avoidance Learning Paradigm. Participants learn by trial and error to respond ("go") to "good" numbers and withhold responding ("no-go") to "bad" numbers, across Reward-only, Punish-only, and Reward-Punish conditions. Response inhibition is indexed by errors on no-go trials.
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_PALP_EN`)
- **Also part of:** Coventure/NeuroVenture (`PALP` — [Cognitive tasks](#cognitive-tasks)).
- **Reference:** Noorbakhsh, S., Boers, E., Afzali, M., & Conrod, P. (2020). Cognitive Function Impairments Linked to Alcohol and Cannabis Use During Adolescence: A Study of Gender Differences. *Frontiers in Human Neuroscience*, 14, 10.3389/fnhum.2020.00095. *(also citing Newman et al., 1985; Castellanos-Ryan et al., 2011; Whelan et al., 2012)*

---

## Clinical assessments

### `CAARMS` — Comprehensive Assessment of At-Risk Mental States
- **Description:** Structured clinical interview mapping the onset and progression of psychosis-risk symptoms.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Reference:** Yung, A., Yuen, H. P., McGorry, P., Phillips, L., & Kelly, D. et al. (2005). Mapping the Onset of Psychosis: The Comprehensive Assessment of At-Risk Mental States. *Australian & New Zealand Journal of Psychiatry*, 39(11-12), 964–971.

### `DIGS` — Diagnostic Interview for Genetic Studies
- **Description:** Structured psychiatric diagnostic interview originally developed for genetic studies of major psychiatric disorders.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Reference:** Nurnberger, J. (1994). Diagnostic Interview for Genetic Studies. *Archives of General Psychiatry*, 51(11), 849.

### `SOFAS` — Social and Occupational Functioning Scale
- **Description:** Single-score measure of social and occupational functioning, independent of symptom severity.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Reference:** Goldman, H., Skodol, A., & Lave, T. (1992). Revising Axis V for DSM-IV: A Review of Measures of Social Functioning.

### `DAWBA` — Development and Well-Being Assessment (Proventure)
- **Description:** Structured diagnostic interview covering a broad range of child/adolescent psychiatric conditions, including the SDQ, specific/social phobia, panic/agoraphobia, PTSD, OCD, generalized anxiety, depression, bipolar mood, ADHD, eating disorders, tics, and psychosis.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Also part of:** Coventure/NeuroVenture (`DAWBA` — see [Clinical assessments](#clinical-assessments) in the main summary). Same instrument; variable-level structure documented there.
- **Reference:** Goodman, R., Ford, T., Richards, H., Gatward, R., & Meltzer, H. (2000). The Development and Well-Being Assessment: description and initial validation of an integrated assessment of child and adolescent psychopathology. *Journal of Child Psychology and Psychiatry, and Allied Disciplines*, 41(5). [pubmed.ncbi.nlm.nih.gov/10946756](https://pubmed.ncbi.nlm.nih.gov/10946756/)

---

## Mental health & psychopathology

### `CAPE-42` — Community Assessment of Psychic Experience
- **Description:** Self-report measure of positive, negative, and depressive psychotic-like experiences in the general population, and how distressing each is. Each experience item is paired with a follow-up "how distressed are you by this" rating.
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_Q2_EN` sheet)
- **Example variable:** `CAPE_33` = "Do you ever hear voices when you are alone?"; `CAPE_33_feel` = associated distress rating
- **Reference:** Stefanis, N. C., Hanssen, M., Smirnis, N. K., Avramopoulos, D. A., Evdokimidis, I. K., Stefanis, C. N., Verdoux, H., & Van Os, J. (2002). Evidence that three dimensions of psychosis have a distribution in the general population. *Psychological Medicine*, 32, 347–358.

### `PSYCHOTIC` / `APSS-PLE` — Thoughts and Feelings questionnaire
- **Description:** Screens for psychotic-like experiences (thought reading, special messages, being followed/spied on, hearing voices, etc.).
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_Q2_EN` sheet)
- **Example variable:** `PSYCHOTIC_04` = "Have you ever heard voices that other people cannot hear?"
- **Also part of:** Coventure/NeuroVenture (`PSYCHOTIC_` — see [Mental health & psychopathology](#mental-health--psychopathology) in the main summary). Item count and content match exactly — same instrument.
- **Reference:** Laurens, K. R., Hodgins, S., Maughan, B., Murray, R. M., Rutter, M. L., & Taylor, E. A. (2007). Community screening for psychotic-like experiences and other putative antecedents of schizophrenia in children aged 9–12 years. *Schizophrenia Research*, 90(1), 130–146.

### `PHQA` — Patient Health Questionnaire, Adolescents
- **Description:** Diagnostic screening covering depression, anxiety/panic attacks, generalized anxiety, and eating disorder symptoms, in adolescent-appropriate language.
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_Q2_EN` sheet, variable prefix `HQA_`)
- **Example variable:** `HQA_13` = "In the last 2 weeks, have you often had thoughts that..."
- **Reference:** Patient Health Questionnaire for Adolescents — [hhs.texas.gov PHQ-A instructions PDF](https://www.hhs.texas.gov/sites/default/files/documents/doing-business-with-hhs/provider-portal/health-services-providers/thsteps/ths-patient-health-questionnaire-instr.pdf)

---

## Psychosocial

### `PSQI` — Pittsburgh Sleep Quality Index
- **Description:** Standardized self-report measure of sleep quality and disturbances over the past month.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Reference:** Buysse, D., Reynolds, C., Monk, T., Berman, S., & Kupfer, D. (1989). The Pittsburgh Sleep Quality Index: A new instrument for psychiatric practice and research. *Psychiatry Research*, 28(2), 193–213.

---

## Substance use

### `DEP-ADO` — DEP-ADO substance use screening (Proventure)
- **Description:** Québec adolescent alcohol/drug screening tool. Screens lifetime and past-year substance use, frequency, harms/consequences (physical, psychological, relational, school, legal, financial), and dependence symptoms (SDS items), separately for alcohol, cannabis, and other drugs.
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_Q1_EN` sheet, variable prefix `DEPADO_`)
- **Example variable:** `DEPADO_ALC_HARM01` = "Harm to your physical health caused by your alcohol use"
- **Also part of:** Coventure/NeuroVenture (`DEPAPO_` — see [Substance use](#substance-use) in the main summary). Note: prefix differs slightly (`DEPADO_` here vs. `DEPAPO_` in Coventure which is a typo and must be fixed).
- **Reference:** Germain, M. *Grille de dépistage de consommation problématique d'alcool et de drogues chez les adolescents et les adolescentes – DEP-ADO.* Recherche et intervention sur les substances psychoactives. Québec, 2005.

### `CEQ` — Cannabis Experience Questionnaire
- **Description:** Detailed cannabis-use history: age of first use, reasons for starting/continuing/stopping, current use patterns (frequency, quantity, type, method of consumption, setting), changes in use over time, subjective effects experienced while high (fear, paranoia, euphoria, hearing voices, etc.), and money spent.
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_Q1_EN` sheet, variable prefix `CEQ_`)
- **Example variable:** `CEQ_15.8.a.3` = "Quantity (average per day) (1 joint = 0.5g)"
- **Reference:** Barkus, E. J., Stirling, J., Hopkins, R. S., & Lewis, S. (2006). Cannabis-induced psychosis-like experiences are associated with high schizotypy. *Psychopathology*, 39, 175–178.

### `MMM` — Marijuana Motives Measure
- **Description:** Why participants use cannabis, across 5 motive subscales analogous to the Drinking Motives Questionnaire: Coping, Conformity, Social, Enhancement, Expansion.
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_Q1_EN` sheet)
- **Example variable:** `MMM_04` = "Because it helps me when I feel depressed or nervous"
- **Reference:** Simons, J., Correia, C. J., Carey, K. B., & Borsari, B. E. (1998). Validating a five-factor marijuana motives measure: Relations with use, problems, and alcohol motives. *Journal of Counseling Psychology*, 45(3), 265–273.

### `SMOKE` — Hooked on Nicotine Questionnaire
- **Description:** Assesses nicotine dependence symptoms: lifetime and past-year smoking frequency, quit attempts, cravings, withdrawal symptoms (irritability, poor concentration, restlessness) when unable to smoke.
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_Q1_EN` sheet)
- **Example variable:** `SMOKE_05` = "Have you ever felt like you were addicted to tobacco?"

### `SURPS` — Substance Use Risk Profile Scale (Proventure)
- **Description:** Personality risk-factor scale for substance misuse: Negative Thinking, Anxiety Sensitivity, Impulsivity, Sensation Seeking.
- **Source:** Proventure_Data Dictionary_2026-04-09 (`PROVENTURE_Q2_EN` sheet)
- **Example variable:** `SURPS_09` = "I like doing things that frighten me a little."
- **Also part of:** Coventure/NeuroVenture (`SURPS_` — see [Substance use](#substance-use) in the main summary).
- **Reference:** Woicik, P. A., Stewart, S. H., Conrod, P. J., et al. (2009). The Substance Use Risk Profile Scale: a scale measuring traits linked to reinforcement-specific substance use profiles. *Addictive Behaviors*, 34, 1042–1055.

### `TLFB` — Timeline Followback
- **Description:** Calendar-based recall method for quantifying substance use (drugs, cigarettes, marijuana) over a defined recall period.
- **Source:** PROVENTURE - COMPLETE TEST BATTERY
- **Also part of:** Coventure/NeuroVenture (`TIME_LINE_FOLLOW_BACK` — see [Substance use](#substance-use) in the main summary). Same method; variable-level structure (per-month days/quantity/money-spent for alcohol, tobacco, cannabis, other drugs) documented there.
- **Reference:** Sobell, L. C., & Sobell, M. (1996). Timeline Followback Method (Drugs, Cigarettes, and Marijuana).

---

## Data Dictionary Structure (Proventure xlsx)

Unlike the flat `instrument`/`variable_name` table format of the other two dictionaries, this file is a raw Psytools export:

| Sheet | Contents |
|---|---|
| `PROVENTURE_Q1_EN` / `_FR` | Questionnaire block 1 (UIC, DEM, DEPADO, SMOKE, CEQ, MMM), English/French |
| `PROVENTURE_Q2_EN` / `_FR` | Questionnaire block 2 (SURPS, HQA/PHQA, PSYCHOTIC, CAPE-42), English/French |
| `PROVENTURE_WCST_EN` / `_FR` | Wisconsin Card Sorting Task — instructions and stimulus card deck |
| `PROVENTURE_PALP_EN` / `_FR` | Stop-or-Go (PALP) task — instructions and condition scripts |

**Column structure:** Column A = variable name; further columns hold response-option codes in `CODE%%Label` format (e.g. `1%%Yes`, `2%%No`) and, on the first row of a repeated item block, the question text. There is no `instrument`, `timepoints`, or `data_source` column — those must be inferred from variable-name prefix and sheet, as done above.

---


