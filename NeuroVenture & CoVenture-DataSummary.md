# Behavioural Questionnaire Data Summary - NeuroVenture & CoVenture

This page acts as a legend for [CoVenture](#coventure-study) and [NeuroVenture](#neuroventure-study) data (see descriptions of each study below). It tells you how and where to find the data you're searching for, including what each instrument is, how its variables are named, where to find it in the data files.

---

### Naming convention legend

Most questionnaire variables (variable_name) follow this pattern:

```
PREFIX_QQ_Y#
```

| Part | Meaning | Example |
|---|---|---|
| `PREFIX` | Instrument abbreviation (see table of instruments below) | `SDQ`, `SURPS`, `DEM` |
| `QQ` | Item/question number within the instrument, as it appears on the original questionnaire | `01`, `02`, ... |
| `Y#` | Timepoint / study year the data was collected (`Y1`–`Y5`) | `Y1` = Year 1, `Y5` = Year 5 |

### How to match a column to its dictionary entry

1. Strip the trailing `_Y#` from the column name (in AllDataWide file) to get the **base variable name** (e.g. SDQ_07_Y3 → SDQ_07).
2. Find the base variable name you're looking for in the legend below to obtain information about the variable.
3. Look up that variable name in the data dictionary indicated by the legend (`coventure_data_dictionary.csv` or `data_dictionary.csv` — for information on each dictionary see the bottom of this page) → `variable_name` column.

---

## Instrument index

Click an instrument to jump to its section. Instruments are grouped by domain.

**Demographics & sessions:** [DEM](#dem_--demographics) · [Demographic Information](#demographic_informations--participant-demographics--history) · [Testing Sessions](#testing_sessions--session-level-metadata) · [Codes](#codes--administrative-id-codes)

**Cognitive tasks:** [CMS](#cms--memory-task) · [SWM](#swm--spatial-working-memory) · [CFT](#cft--culture-fair-non-verbal-iq-test) · [PALP](#palp--probabilistic-associative-learning-paradigm) · [BART](#bart-balloon-analogue-risk-task--risk-taking-task) · [Stop-Signal Task](#stop-signal-task--response-inhibition-task) · [n-back task](#n-back-task--working-memory-task) · [Behavioural Scores](#behavioural_scores--memory-iq-and-executive-function-battery)

**Clinical assessments:** [DAWBA](#dawba--development-and-well-being-assessment) · [CTQ_X](#ctq_x--childhood-trauma-questionnaire)

**Mental health & psychopathology:** [SDQ](#sdq_--strengths-and-difficulties-questionnaire) · [BSI](#bsi_--brief-symptom-inventory-subset) · [Psychotic-like experiences](#psychotic_--psychotic-like-experiences-screen) · [Automatic Thoughts](#auto_--automatic-thoughts-questionnaire) · [COPE](#cope_--brief-cope-inventory)

**Psychosocial:** [Self-Esteem](#self_esteem_--rosenberg-self-esteem-scale) · [Bullying](#bully_--bullying-involvement-questionnaire) · [Sleep](#sleep_--sleep-habits-questionnaire) · [Eating habits](#eat_--eating-habits-questionnaire)

**Substance use:** [DEP-ADO](#depapo_--dep-ado-substance-use-screening) · [DMQ](#dmq_--drinking-motives-questionnaire) · [CMQ](#cmq_--cannabis-motives-questionnaire) · [Social Norms](#soc_norms_--perceived-social-norms) · [SURPS](#surps_--substance-use-risk-profile-scale) · [Timeline Follow-Back](#time_line_follow_back--timeline-follow-back-substance-use)

---
# **Instruments/Questionnaires**

## Demographics & sessions

### `DEM_` — Demographics
- **Description:** Gender, pubertal status (sex-specific items), grade level, and other demographic items. Some items, e.g. `DEM_02f`/`DEM_02m`, are sex-specific and only populated for the relevant sex.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "DEM_"`
- **Example variable:** DEM_01
- **Also found in:** Proventure (`DEM_` — see the [Proventure data dictionary](ProVenture%20data%20summary.md#dem--demographics-proventure))

### `DEMOGRAPHIC_INFORMATIONS` — participant demographics & history
- **Description:** One-time or slowly-changing participant background information: project status, school, gender, date of birth, handedness, language history, brain injury/diagnosis history (self and relatives), medication use, height and weight.
- **Timepoints:** mostly not timepoint-specific; `Medication`, `Medication_Type`, `Height`, `Weight` are `1;2;3`
- **Dictionary:** `data_dictionary.csv`, `instrument == "DEMOGRAPHIC_INFORMATIONS"`
- **Example variable:** `Starting_Grade` = highschool grade at timepoint 1

### `TESTING_SESSIONS` — session-level metadata
- **Description:** Information about each testing session: date, participant age at testing, whether the participant had braces (relevant for MRI eligibility), and the time elapsed between sessions.
- **Timepoints:** `1;2;3` (`Braces` is `2;3` only)
- **Dictionary:** `data_dictionary.csv`, `instrument == "TESTING_SESSIONS"`
- **Example variable:** date, age

### `CODES` — administrative ID codes
- **Description:** Cross-referencing ID codes linking a participant's records across different data collection systems (Psytools, Dot-probe task, DAWBA).
- **Timepoints:** `1;2;3` for `Psytools`, `Dotprobe`, `DAWBA`; others not timepoint-specific
- **Dictionary:** `data_dictionary.csv`, `instrument == "CODES"`
- **Naming note:** `Sec2_Psytools` / `Sec4_Psytools` = Psytools code recorded when the participant was in Secondary 2 / Secondary 4; `BB_Psytools` = code used before the participant reached baseline (i.e., started the project already in Secondary 2)

---

## Cognitive tasks

### `CMS` — Memory task
- **Description:** Children's Memory Scale (CMS)
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "CMS"`
- **Example variable:** CMS_C1

### `SWM` — Spatial Working Memory
- **Description:** Spatial working memory task (variable names such as `SWM_BSE_10_1`, `SWM_BSE_4_1` follow CANTAB-style "between search errors" naming)
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "SWM"`
- **Example variable:** SWM_BSE_10_1, SWM_WSE_10_1, SWM_t4_span

### `CFT` — Culture Fair (non-verbal IQ) test
- **Description:** Non-verbal reasoning/IQ test, Raven's Progressive Matrices-style (per dictionary note on `CFT_Raw_Total`).
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "CFT"`
- **Example variable:** CFT_Test_1

### `PALP` — Probabilistic Associative Learning Paradigm
- **Description:** Reward/punishment-based associative learning task (variables named `PALP_RP_Om`, `PALP_RP_Com`, `PALP_RP_RT_mean` — "Reward/Punish omissions/commissions/reaction time").
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "PALP"`
- **Example variable:** PALP_RP_Com
- **Also found in:** Proventure ([`PALP`](ProVenture%20data%20summary.md#palp--stop-or-go-task) — "Stop or Go Task")

### `BART (Balloon Analogue Risk Task)` — risk-taking task
- **Description:** Computerized behavioural risk-taking task. Participants pump up virtual balloons to earn points; each pump raises payout but also the risk the balloon explodes and points are lost. Produces summary scores across 30 balloon trials.
- **Timepoints:** not specified
- **Dictionary:** `data_dictionary.csv`, `instrument == "BART (Balloon Analogue Risk Task)"`
- **Example variable:** Maximum_number_of_pumps, `BART_Score` = average number of pumps before collecting points (the primary risk-taking index)

### `Stop-Signal Task` — response inhibition task
- **Description:** Go/No-Go response inhibition task using letter cues ("O" and "X"). Measures ability to withhold a prepotent response when a stop-signal appears.
- **Timepoints:** not specified in dictionary
- **Dictionary:** `data_dictionary.csv`, `instrument == "Stop-Signal Task"`
- **Example variable:** Go_O_n (Total of Go "O" cue)

### `n back task` — working memory task
- **Description:** N-back working memory task with 2-back and 3-back conditions. Measures reaction time, hit rate, false alarms (commission errors), and misses (omission errors) at each load level.
- **Timepoints:** not specified in dictionary
- **Dictionary:** `data_dictionary.csv`, `instrument == "n back task"`
- **Naming note:** suffix `_2` = 2-back condition, `_3` = 3-back condition
- **Example variable:** Mean_RT_2, total_trial_2, FA_2

### `BEHAVIOURAL_SCORES` — memory, IQ, and executive function battery
- **Description:** A bundle of pen-and-paper/psytools cognitive test scores (CMS/CMS2, WISC, Stroop, SOPT).
- **Timepoints:** `1;2;3`; Note: CMS2 items are `2;3` only
- **Dictionary:** `data_dictionary.csv`, `instrument == "BEHAVIOURAL_SCORES"`
- **Example variable:** `Stroop_Inhibition_Ratio` = mistakes/correct-words ratio on the Stroop inhibition trial

---

## Clinical assessments

### `DAWBA` — Development and Well-Being Assessment
- **Description:** Structured parent-report (and youth self-report) psychiatric diagnostic interview. Produces symptom subscale scores (emotional, conduct, hyperactivity, peer, prosocial, impact) and computer-generated diagnostic "band" predictions for a wide range of DSM-IV/ICD-10 disorders (separation anxiety, specific/social phobia, panic, agoraphobia, PTSD, OCD, generalized anxiety, depression, ADHD, oppositional defiant disorder, conduct disorder, eating disorder, tics, autism spectrum).
- **Timepoints:** `1;2;3` for the main administration; `3` only for the "time2" repeat items
- **Dictionary:** `data_dictionary.csv`, `instrument == "DAWBA"`
- **Naming note:** `p1` prefix = Parent 1 respondent; `s` prefix = Youth/self respondent; `band` suffix = diagnostic classification; `z2` = second/repeat administration
- **Example variable:** `depband` = computer-predicted Depression diagnostic band (DSM-IV & ICD-10)
- **Also found in:** Proventure ([`DAWBA`](ProVenture%20data%20summary.md#dawba--development-and-well-being-assessment-proventure))

### `CTQ_X` — Childhood Trauma Questionnaire
- **Description:** Retrospective self-report measure of childhood abuse and neglect (28 items covering emotional abuse, physical abuse, sexual abuse, emotional neglect, and physical neglect, plus reverse-scored protective/positive items e.g. "I felt loved").
- **Timepoints:** not specified in dictionary
- **Dictionary:** `data_dictionary.csv`, `instrument == "CTQ_X"`
- **Example variable:** `CTQ_Q3` = "People in my family called me things like 'stupid', 'lazy', or 'ugly'."

---

## Mental health & psychopathology

### `SDQ_` — Strengths and Difficulties Questionnaire
- **Description:** Standard child/adolescent behavioural screening tool. 5 subscales: Emotional problems, Conduct problems, Hyperactivity, Peer problems, Prosocial behaviour, plus a Total Difficulties score. Questions 1-25.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "SDQ_"`
- **Example variable:** SDQ_01 = question 1 "Give your answers on the basis of how things have been for you OVER THE LAST 12 MONTHS: I try to be nice to other people. I care about their feelings"

### `BSI_` — Brief Symptom Inventory (subset)
- **Description:** Past-12-month psychological symptom checklist. Subscales present: Depression, Anxiety, Interpersonal Sensitivity, plus a suicidal-ideation item. Questions 1-12.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "BSI_"`
- **Example variable:** BSI_01 = question 1 'IN THE PAST 12 MONTHS, how much have you experienced the following feelings ?: Thoughts of ending your life.'

### `PSYCHOTIC_` — Psychotic-like experiences screen
- **Description:** Screens for psychotic-like experiences (e.g. thought reading, special messages, being followed/spied on). Questions 1-9.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "PSYCHOTIC_"`
- **Example variable:** PSYCHOTIC_01
- **Also found in:** Proventure ([`PSYCHOTIC` / `APSS-PLE`](ProVenture%20data%20summary.md#psychotic--apss-ple--thoughts-and-feelings-questionnaire) — "Thoughts and Feelings questionnaire").

### `AUTO_` — Automatic Thoughts Questionnaire
- **Description:** Frequency of negative automatic thoughts ("thoughts that pop into your head"). Subscales: Personal failure, Hostility, plus a total score. Questions 1-20.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "AUTO_"`
- **Example variable:** AUTO_01

### `COPE_` — Brief COPE Inventory
- **Description:** Coping strategies in response to problems/stress. 14 subscales: Active coping, Distraction, Denial, Substance use, Emotional support, Instrumental support, Behavioural disengagement, Venting, Positive reframing, Planning, Humor, Acceptance, Religion, Self-blame. Questions 1-28.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "COPE_"`
- **Example variable:** COPE_01

---

## Psychosocial

### `SELF_ESTEEM_` — Rosenberg Self-Esteem Scale
- **Description:** Standard 10-item global self-esteem measure (e.g. "On the whole, I am satisfied with myself"). Questions 1-10.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "SELF_ESTEEM_"`
- **Example variable:** SELF_ESTEEM_01

### `BULLY_` — Bullying involvement questionnaire
- **Description:** Bullying victimization and perpetration at school. Questions 1-12.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "BULLY_"`
- **Example variable:** BULLY_01

### `Sleep_` — Sleep habits questionnaire
- **Description:** Self-reported weekday/weekend bed and wake times over the past month (one item per day of the week). Questions 1-10.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "Sleep_"`
- **Example variable:** SLEEP_01

### `EAT_` — Eating habits questionnaire
- **Description:** Frequency of eating/drinking specific food/drink categories over the past 7 days, plus breakfast frequency. Questions 1-9.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "EAT_"`
- **Example variable:** EAT_01
- **Also found in:** Not exactly the same but related to Proventure's [`HQA_EW_`](ProVenture%20data%20summary.md#hqa_ew--eating-disorder-screening-phqa-subscale) eating disorder screen covers a similar domain (weight/shape concerns, compensatory behaviors) but is a different instrument questionnaire

---

## Substance use

### `DEPAPO_` — DEP-ADO substance use screening
- **Description:** Adolescent alcohol/drug screening tool. Screens lifetime and past-year use of alcohol, cannabis, and other drugs, frequency of use, and consequences of use. Produces three factor scores (alcohol & cannabis, other drugs, consequences) plus a total score.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "DEPAPO_"`
- **Example variable:** `DEPAPO_ALC` = alcohol use item
- **Also found in:** Proventure ([`DEPADO_`](ProVenture%20data%20summary.md#dep-ado--dep-ado-substance-use-screening-proventure)) Note: typo in this dictionary, should be DEPADO

### `DMQ_` — Drinking Motives Questionnaire
- **Description:** Why participants drink alcohol, across 5 motive subscales: Social, Coping with anxiety, Coping with depression, Enhancement, Conformity. Questions 1-28.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "DMQ_"`
- **Example variable:** DMQ_01 = DMQ question 1 "how often you drink as a way to celebrate"

### `CMQ_` — Cannabis Motives Questionnaire
- **Description:** Why participants use cannabis, across 5 motive subscales: Social, Coping with anxiety, Coping with depression, Enhancement, Conformity. Questions 1-28.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "CMQ_"`
- **Example variable:** CMQ_01 = CMQ question 1 "how often you use cannabis as a way to celebrate"

### `SOC_NORMS_` — Perceived Social Norms
- **Description:** Perceived peer acceptability of substance use ("Do you think it's OK for someone your age to do the following: try smoking / drinking / getting drunk..."). Questions 1-11.
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "SOC_NORMS_"`
- **Example variable:** SOC_NORMS_01 = social norms question 1

### `SURPS_` — Substance Use Risk Profile Scale
- **Description:** Personality risk-factor scale for substance misuse, 4 subscales: Negative Thinking (NT), Anxiety Sensitivity (AS), Impulsivity (IMP), Sensation Seeking (SS). Collected in both studies, but stored differently:
  - **`coventure_data_dictionary.csv`** → raw item-level responses (`SURPS_01`–`SURPS_48`, one per year)
- **Timepoints:** Y1–Y5
- **Dictionary:** `coventure_data_dictionary.csv`, `instrument == "SURPS_"` (raw items) · `data_dictionary.csv`, `instrument == "SURPS"` (subscale scores)
- **Example variable:** `SURPS_01_Y1` = raw item 1, Year 1; `SURPS_SS_Raw` = raw Sensation Seeking subscale score; `ZSURPS_NT_School_Y#` = NT subscale, z-scored vs. school mean; `ZSURPS_NT_Total_Y#` = z-scored vs. full sample
- **Also found in:** Proventure ([`SURPS`](ProVenture%20data%20summary.md#surps--substance-use-risk-profile-scale-proventure)

### `TIME_LINE_FOLLOW_BACK` — Timeline Follow-Back substance use
- **Description:** Calendar-based recall method for quantifying substance use over the past 6 months. Captures, per month: number of days used, quantity used, and money spent — separately for alcohol, binge drinking, tobacco, cannabis, and up to two additional "other" drugs.
- **Timepoints:** `2;3` for alcohol/tobacco/cannabis/other-drug-#1 items; `3` only for the second "other drug" block
- **Dictionary:** `data_dictionary.csv`, `instrument == "TIME_LINE_FOLLOW_BACK"`
- **Naming note:** `EtOH` = alcohol (ethanol), `$` in variable name = money spent; `Days` = number of days used; `MonthN` = calendar month N of the 6-month recall window
- **Example variable:** `BingeDaysMonth3` = number of binge-drinking days for month 3
- **Also found in:** Proventure ([`TLFB`](ProVenture%20data%20summary.md#tlfb--timeline-followback))

---

## Data Dictionary Structure

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

> **Note:** `data_dictionary.csv` variable names do **not** carry a `_Y#` suffix — timepoints are recorded separately in the `timepoints` field (`1`, `2`, `3` = testing session 1/2/3).

---

## Coventure study
### `coventure_data_dictionary.csv`
- **What it is:** CoVenture is a large-scale, decade-long youth mental health cohort study that tracks students from the Greater Montreal area. The data dictionary for the **Coventure cohort's yearly self-report questionnaire** — the mental health, substance use, and psychosocial questionnaires (SDQ, SURPS, DEP-ADO, COPE, etc.).
- **Variable naming:** `PREFIX_QQ_Y#` — instrument prefix, question number, and study year (`Y1`–`Y5`).
- **Includes:** DEPAPO, DMQ, CMQ, SOC_NORMS, SURPS (raw items), SDQ, BSI, PSYCHOTIC, AUTO, COPE, SELF_ESTEEM, BULLY, Sleep, EAT, DEM, plus the cognitive tasks CMS, SWM, CFT, PALP.

## NeuroVenture study
### `data_dictionary.csv`
- **What it is:** NeuroVenture is a sub-study of the CoVenture cohort that looks into how adolescent substance use impacts brain development using neuroimaging (MRI). The data dictionary for the **NeuroVenture** study — cognitive/behavioural computer tasks (eprime), a clinical diagnostic interview (DAWBA), a childhood trauma questionnaire (CTQ), a substance-use calendar (Timeline Follow-Back), and session/demographic admin data.
- **Variable naming:** Plain variable names, **no `_Y#` suffix**. Timepoints are recorded separately in the `timepoints` column, using numeric session labels (`1`, `2`, `3` = testing session 1/2/3), not `Y1`–`Y5`.
- **Includes:** BART, Stop-Signal Task, n-back task, SURPS (subscale scores only — see [SURPS entry](#surps_--substance-use-risk-profile-scale) above), BEHAVIOURAL_SCORES (CMS, WISC, Stroop, SOPT), DAWBA, CTQ_X, TIME_LINE_FOLLOW_BACK, DEMOGRAPHIC_INFORMATIONS, TESTING_SESSIONS, CODES.

---
