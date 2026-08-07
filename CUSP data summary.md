# CUSP Data Dictionary — The Canadian Underage Substance Use Prevention Trial 
[CUSP](https://www.conrodventurelab.com/project-pages/cusp-trial) is a cluster randomized controlled trial (in Quebec, British Columbia, Nova Scotia and Ontario) to test the effectiveness of PreVenture when disseminated through a Train-the-Trainer implementation model and to address questions about program sustainability and scale-up.

**Variable naming:** Raw items use a `LETTER#_SUFFIX` scheme tied to questionnaire section ordered in ahlphabetical order (`J12_01` = section J, item 12, sub-item 01). Derived variables use short lowercase names (`sdq_tot`, `audit_cat`) with no year suffix 

## Instrument index

**Demographics & sessions:** [Background (B1–B23)](#background-b1b23--demographics-ses--school-connection) · [Trial design & intervention](#trial-design--intervention-preventure-workshop-variables)

**Mental health & psychopathology:** [BSI](#bsi--brief-symptom-inventory-subset-cusp) · [BRIEF-COPE](#brief-cope--brief-cope-inventory-cusp) · [APSS](#apss--anxiety-sensitivity--psychotic-like-experiences-screen) · [ATQ](#atq--automatic-thoughts-questionnaire-cusp) · [SDQ](#sdq--strengths-and-difficulties-questionnaire-cusp)

**Psychosocial:** [Rosenberg Self-Esteem Scale (mislabeled "SES")](#rosenberg-self-esteem-scale-mislabeled-ses-in-raw-item-bank) · [CHU-9D](#chu-9d--child-health-utility-9d)

**Personality:** [SURPS](#surps--substance-use-risk-profile-scale-cusp)

**Substance use:** [CRAFFT](#crafft--car-relax-alone-forget-friends-trouble-screen) · [DEP-ADO](#dep-ado--dep-ado-substance-use-screening-cusp) · [SUMM](#summ--substance-use-motives-measure) · [MAAQ](#maaq--marijuana-alcohol-abstinence-questionnaire) · [AUDIT](#audit--alcohol-use-disorders-identification-test) · [Tobacco/E-cigarette/Cannabis frequency items](#tobacco-e-cigarette-cannabis-frequency--quitting-items) · [CAST](#cast--cannabis-abuse-screening-test) · [CUDIT](#cudit--cannabis-use-disorders-identification-test) · [NPDMU](#npdmu--non-prescription-drug-misuse)

**Service use & adversity:** [Mental/physical health self-rating, help-seeking, trauma, violence](#mental-physical-health-self-rating-help-seeking-trauma-violence)

**COVID-19:** [NIH COVID-19 Questionnaire](#nih-covid-19-questionnaire)

---
# **Instruments/Questionnaires**

## Demographics & sessions

### Background (B1–B23) — demographics, SES & school connection
- **Description:** Date of birth, grade, time in Canada, ethnicity/cultural background, sex at birth, gender identity, sexual orientation, parental birthplace, household composition, caregiver education/employment, part-time work/study hours, perceived family SES, family/school/community connectedness, perceived school-standing, school marks, unexcused/illness school absences, and suspension/expulsion history.
- **Raw items:** 26 (`B1`–`B23`, including sub-items `B4`, `B9a`–`B9d`, `B14_A`–`B14_F`)
- **Derived variables (all baselines data dictionary):** `absent_ill`, `absent_other`, `bplace`, `caregiver_educ`, `ethn_east_asian`, `ethn_indigenous`, `ethn_south_asian`, `gender`, `immigrant_bg`, `lgbt`, `parent_bplace2`, `racialised`, `ses` , `sex`, `connection` (school/family/community connectedness composite, B14 items, 6–24)
- **Data source:** raw items → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q2. Derived variables → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Demographics & SES".
- **Example variable:** `B4_10` = East/Southeast Asian ethnicity checkbox (recoded to `ethn_east_asian` in the derived dataset)

### Trial design & intervention (PreVenture workshop variables)
- **Description:** CUSP is a trial of the **PreVenture** personality-targeted intervention. These variables track workshop assignment and attendance rather than questionnaire responses: cohort, wave, school ID, SURPS-based high-risk classification, workshop attendance (1st/2nd session), workshop cluster/ID, and treatment arm.
- **Derived variables:** `Interventionnumber`, `attend1`, `attend2`, `attend_any`, `esample`, `high_risk`, `highrisk`, `intervention_cluster`, `intervention_id`, `intervention_num`, `surps_cat`, `treat`, plus linkage fields `Usercode`, `Y2AutoMatch`, `Y3AutoMatch`, `cohort`, `datatag`, `dob_date`, `prov`, `schoolID`, `wave`
- **Data Source:** `all_baselines_data_dictionary.xlsx`, `Data dictionary` tab, domains `Identifiers & linkage` and `Trial design & intervention`
- **Example variable:** `high_risk` = "High risk on any SURPS subscale z>0.9 SD (baseline records only)"
- **Not in:** the raw `CUSP` tab item bank — this is trial/administrative metadata generated during data management, not a questionnaire section.

---

## Personality

### `SURPS` — Substance Use Risk Profile Scale (CUSP)
- **Description:** Personality risk-factor scale for substance misuse — 4 subscales: Negative Thinking, Anxiety Sensitivity, Impulsivity, Sensation Seeking. Used in CUSP to assign participants to the PreVenture workshop stream matching their highest-risk subscale.
- **Raw items:** `A1_a`–`A1_w`
- **Derived variables:** `surps_ax` (anxiety), `surps_im` (impulsivity), `surps_nt` (negative thinking), `surps_ss` (sensation seeking); also feeds `surps_cat`, `high_risk`, `highrisk` under Trial design above
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q1. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Personality (SURPS)".
- **Example variable:** `A1_c` = "I would like to skydive (parachute out of a plane)."
- **Also found in:** Coventure/NeuroVenture ([`SURPS_`](behavioural_data_summary.md#surps_--substance-use-risk-profile-scale)) and Proventure ([`SURPS`](proventure_data_dictionary.md#surps--substance-use-risk-profile-scale-proventure)). Item count (23) matches Proventure's shortened version rather than the 48-item Coventure/NeuroVenture version — confirm before pooling across studies.

---

## Mental health & psychopathology

### `BSI` — Brief Symptom Inventory (subset) (CUSP)
- **Description:** Past-12-month psychological symptom checklist covering depression and anxiety.
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q4. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Mental health & wellbeing" (BRIEF-COPE is its own domain, "Coping (Brief COPE)").
- **Example variable:** `J8_01` = "Thoughts of ending your life."
- **Also found in:** Coventure/NeuroVenture ([`BSI_`](behavioural_data_summary.md#bsi_--brief-symptom-inventory-subset)).

### `BRIEF-COPE` — Brief COPE Inventory (CUSP)
- **Description:** Coping strategies in response to problems/stress, 14 subscales.
- **Raw items:** `J9_01`–`J9_28`
- **Derived variables:** `cope_acceptance`, `cope_active`, `cope_denial`, `cope_disengage`, `cope_emot_support`, `cope_humor`, `cope_instr_support`, `cope_planning`, `cope_reframe`, `cope_religion`, `cope_self_blame`, `cope_self_dist`, `cope_substance`, `cope_venting` (all 0–6)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q4. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Mental health & wellbeing" (BRIEF-COPE is its own domain, "Coping (Brief COPE)").
- **Example variable:** `J9_03` = "I've been saying to myself 'this isn't real'."
- **Also found in:** Coventure/NeuroVenture ([`COPE_`](behavioural_data_summary.md#cope_--brief-cope-inventory)).

### `APSS` — Anxiety Sensitivity & Psychotic-like Experiences Screen
- **Description:** Screens for psychotic-like experiences (thought reading, special messages, being followed/spied on).
- **Raw items:** `J10_01`–`J10_09`
- **Derived variables:** `apss` (total, 0–7, 0.5-point steps; higher = more)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q4. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Mental health & wellbeing" (BRIEF-COPE is its own domain, "Coping (Brief COPE)").
- **Example variable:** `J10_03` = "Have you ever thought that you were being followed or spied upon?"
- **Also found in:** Coventure/NeuroVenture ([`PSYCHOTIC_`](behavioural_data_summary.md#psychotic_--psychotic-like-experiences-screen)) and Proventure ([`PSYCHOTIC` / `APSS-PLE`](proventure_data_dictionary.md#psychotic--apss-ple--thoughts-and-feelings-questionnaire)). Same 9-item instrument across all three studies (this is the source of the "APSS-PLE" name used in Proventure).

### `ATQ` — Automatic Thoughts Questionnaire (CUSP)
- **Description:** Frequency of negative automatic thoughts.
- **Raw items:** `J11_01`–`J11_20`
- **Derived variables:** `atq` (total, 0–80; higher = more)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q4. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Mental health & wellbeing" (BRIEF-COPE is its own domain, "Coping (Brief COPE)").
- **Example variable:** `J11_02` = "I am worthless"
- **Also found in:** Coventure/NeuroVenture ([`AUTO_`](behavioural_data_summary.md#auto_--automatic-thoughts-questionnaire)).

### `SDQ` — Strengths and Difficulties Questionnaire (CUSP)
- **Description:** Standard child/adolescent behavioural screening tool. 5 subscales: Emotional, Conduct, Hyperactivity, Peer, Prosocial, plus Total Difficulties.
- **Raw items:** `J12_01`–`J12_25`
- **Derived variables:** `sdq_conduct` (items 5,7R,12,18,22; 0–10), `sdq_emotional` (items 3,8,13,16,24; 0–10), `sdq_hyperactive` (items 2,10,15,21R,25R; 0–10), `sdq_peer` (items 6,11R,14R,19,23; 0–10), `sdq_prosocial` (items 1,4,9,17,20; 0–10), `sdq_tot` (0–40)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q4. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Mental health & wellbeing" (BRIEF-COPE is its own domain, "Coping (Brief COPE)").
- **Example variable:** `J12_01` = "I try to be nice to other people. I care about their feelings"
- **Also found in:** Coventure/NeuroVenture ([`SDQ_`](behavioural_data_summary.md#sdq_--strengths-and-difficulties-questionnaire)).

---

## Psychosocial

### Rosenberg Self-Esteem Scale (mislabeled "SES" in raw item bank)
- **Description:** Standard 10-item global self-esteem measure. note: the `CUSP` tab labels the `Scale` column as **"SES"**, it's important to note it is the **Rosenberg Self-Esteem Scale**, not a socioeconomic-status measure. 
- **Raw items:** `J13_01`–`J13_10`
- **Derived variables:** `self_esteem` (10–40; higher = more self-esteem)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q4. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Mental health & wellbeing" (BRIEF-COPE is its own domain, "Coping (Brief COPE)").
- **Example variable:** `J13_03` = "I feel that I have a number of good qualities."
- **Also found in:** Coventure/NeuroVenture ([`SELF_ESTEEM_`](behavioural_data_summary.md#self_esteem_--rosenberg-self-esteem-scale)).

### `CHU-9D` — Child Health Utility 9D
- **Description:** 9-domain child health-related quality-of-life measure (worry, sad, pain, tired, annoyed, schoolwork, sleep, daily routine, ability to join activities), rated "today."
- **Raw items:** `I6`–`I14`
- **Derived variables**: derived variables in all_baselines_data_dictionary.xlsx are named under the eq5d_* prefix
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q4. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Mental health & wellbeing" (BRIEF-COPE is its own domain, "Coping (Brief COPE)").
- **Example variable:** `I8` = "Pain" 

---

## Substance use

### `CRAFFT` — Car, Relax, Alone, Forget, Friends, Trouble screen
- **Description:** Brief adolescent substance-use screening tool. Part A screens for any past-12-month use (alcohol, marijuana, other); Part B (asked depending on skip logic) asks 6 CRAFFT questions (riding in a car with an impaired driver, using to relax/fit in, using while alone, forgetting things, being told to cut down, getting into trouble).
- **Raw items:** `C1A_A`–`C1A_C`, `C1B_A`–`C1B_F`
- **Derived variables:** `crafft_score` (0–6, prorated if ≥5/6 Part B items; missing if Part A incomplete and no use reported), `crafft_pos` (positive screen, score ≥2), `crafft_partA_incomplete` (flag)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q3. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Substance use".
- **Example variable:** `C1B_C` = "Do you ever use alcohol or drugs while you are by yourself, or ALONE?" 

### `DEP-ADO` — DEP-ADO substance use screening (CUSP)
- **Description:** Québec adolescent alcohol/drug screening tool. Extensive substance list (alcohol, tobacco, e-cigarettes, cannabis, spice, OTC cough/cold medicine, pain killers, stimulants, sedatives, cocaine/crack, MDMA, methamphetamine, heroin, fentanyl, salvia, psilocybin/mescaline, LSD, jimson weed, mephedrone, steroids, adrenochromes, PCP, and more), asking lifetime use, age of first use, and past-12-month use per substance.
- **Raw items:** `C2_A`–`C2_Y` lifetime-use block with paired `_specify` age-of-first-use items; `C3` access/availability; `C4_A`–`C4_K` past-12-month use block
- **Derived variables:** `illicit_12mo` (any illicit drug use, past 12mo), `cannabis_ever`, `cannabis_12mo`, `tobacco_ever`, `tobacco_12mo`, `ecig_ever`, `ecig_12mo`
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q3. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Substance use".
- **Example variable:** `C2_D` = "CANNABIS (also known as weed, marijuana, pot, splif, hash...)"
- **Also found in:** Coventure/NeuroVenture ([`DEPAPO_`](behavioural_data_summary.md#depapo_--dep-ado-substance-use-screening)) and Proventure ([`DEPADO_`](proventure_data_dictionary.md#dep-ado--dep-ado-substance-use-screening-proventure)). Same underlying DEP-ADO tool across all three studies; item sets and exact substance list differ — confirm alignment before pooling.

### `SUMM` — Substance Use Motives Measure
- **Description:** Why participants use the substance(s) they endorsed in DEP-ADO — repeated per substance the participant reported using (alcohol block = `C5_A`, cannabis block = `C5_B`, etc.).
- **Raw items:** `C5_A_01`–`C5_A_06` shown; repeated for each additional substance
- **Derived variables:** `motives_alcohol` (SUMM C5_A, 0–28, missing if non-drinker past year), `motives_cannabis` (SUMM C5_B, 0–28, missing if non-user past year)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q3. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Substance use".
- **Example variable:** `C5_A_04` = "Because the substance helps me cope when I'm feeling sad, down, or depressed"
- **Similar to:** Coventure/NeuroVenture's [`DMQ_`](behavioural_data_summary.md#dmq_--drinking-motives-questionnaire) and [`CMQ_`](behavioural_data_summary.md#cmq_--cannabis-motives-questionnaire) — conceptually similar (substance-use motives) but a different, single combined measure rather than separate drinking/cannabis motives questionnaires. Not directly poolable.

### `MAAQ` — Marijuana/Alcohol Abstinence Questionnaire
- **Description:** Reasons for *not* using a substance or for limiting use (interference with school, no desire, religious/spiritual beliefs, impaired self-control, medical/genetic condition, family disapproval, prior substance use problem, financial priorities).
- **Raw items:** `C6_A_01`–`C6_A_08`, repeated per substance
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q3
- **Example variable:** `C6_A_06` = "My family disapproves of using substances (e.g. they get upset)"
- **Dictionary:** Not currently reflected as a standalone derived variable in `all_baselines_data_dictionary.xlsx` — check the `Syntax`/`SKIP` tabs of the derived-variable workbook if you need the scoring rule.

### `AUDIT` — Alcohol Use Disorders Identification Test
- **Description:** Standard alcohol-use screening tool covering consumption frequency/quantity, dependence symptoms, and alcohol-related harms.
- **Raw items:** `D2_01`–`D2_09`
- **Derived variables:** `audit` (total, 0–40, prorated if ≥8/10 items), `audit_8plus` (flag, ≥8 = hazardous/harmful use), `audit_cat` (0=low 0–7; 1=hazardous 8–14; 2=harmful/dependent 15+)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q3. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Substance use".
- **Example variable:** `D2_01` = "How often do you have four (4) or more drinks on one occasion?"

### Tobacco / E-cigarette / Cannabis frequency & quitting items
- **Description:** Standalone frequency and quit-attempt items for tobacco cigarettes (`E1`, `E3`), e-cigarettes (`F1`, `F3`), and cannabis method/type of use (`G1`, `G2`) — not part of a named standardized scale.
- **Derived variables:** feed into `binge`, `binge_freq`, `binge_monthly`, `cannabis_freq`, `cannabis_dab`, `dab_group` in the derived dataset
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q3. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Substance use".
- **Example variable:** `G1` = "In the LAST 12 MONTHS, how have you used cannabis? (Choose ALL that apply)" — feeds `cannabis_dab`/`dab_group`

### `CAST` — Cannabis Abuse Screening Test
- **Description:** Cannabis-specific problem-use screening (using alone, memory problems, being told to cut down by friends/family, among other items).
- **Raw items:** `G4_02`–`G4_06`
- **Derived variables:** `cast` (0–24; 0 if no past-12mo use), `cast_risk` (0=low <3; 1=moderate 3–6; 2=high 7+)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q3. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Substance use".
- **Example variable:** `G4_03` = "Have you had memory problems when you smoked cannabis?"

### `CUDIT` — Cannabis Use Disorders Identification Test
- **Description:** Cannabis dependence/problem-use screening (failing role obligations, time spent obtaining/using, memory/concentration problems while using).
- **Raw items**: `G4_08`–`G4_10`
- **Derived variables:** `cudit_7` (7-item score as asked in CUSP, 0–28, prorated if ≥6/7 items), `cudit_8` (8-item score, substituting Q2 with Q1, 0–32), `cudit_8plus` (flag, ≥8 = hazardous use), `cudit_12plus` (flag, ≥12 = possible cannabis use disorder)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q3 (Cannabis subsection). Also has its own dedicated CUDIT tab in that same workbook, with full scoring syntax. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Substance use".
- **Example variable:** `G4_09` = "How often have you devoted a great deal of your time to getting, using, or recovering from cannabis?"

### `NPDMU` — Non-Prescription Drug Misuse
- **Description:** Misuse of prescription/non-prescription drugs — pain killers, sedatives/tranquilizers, stimulants — covering reasons for use, harms, and quit attempts.
- **Raw items:** `H1_01`–`H1_08`
- **Derived variables:** `npdmu` (any non-prescription drug use, past 12mo)
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Section Q3. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Substance use".
- **Example variable:** `H1_02` = "Sedatives or tranquilizers (downers such as Ativan or Xanax)"

---

## Service use & adversity

### Mental/physical health self-rating, help-seeking, trauma, violence
- **Description:** Single-item self-ratings and service-use questions: self-rated physical health, self-rated mental/emotional health, sleep hours, long-term disability/illness, professional mental-health help-seeking (frequency), crisis helpline use (phone/text/web), prescribed psychiatric medication (ADHD/anxiety/depression), unmet mental-health need, lifetime traumatic/negative event exposure, and perceived exposure to violence.
- **Raw items:** `I1`–`I3`, `J1`–`J7`
- **Derived variables:** `srph`, `srmh`, `low_srmh`, `sleep_hours`, `helpseeking_any`, `helpseeking_freq`, `helpline_any`, `helpline_phone`, `helpline_text`, `helpline_web`, `meds_any`, `meds_adhd`, `meds_anxiety`, `meds_depression`, `unmet_need`, `trauma`, `violence_exp`, `violence_agree`
- **Data source:** raw → 'Derived_Variable_Algorithm_and_Skip_Rules.xlsx', CUSP tab, Sections Q4. Derived → 'all_baselines_data_dictionary.xlsx', Data dictionary tab, domain "Service use & adversity"
- **Example variable:** `J4` = "In the LAST 12 MONTHS, was there a time when you wanted to talk to someone about a mental health or emotional problem you had, but did not know where to turn?" (→ `unmet_need`)

---

## COVID-19

### NIH COVID-19 Questionnaire
- **Description:** COVID-19 infection history, pandemic impact on schooling and social connection, coping strategies used during the pandemic, life-satisfaction during the pandemic, and a trauma/stress-response item set (sleep difficulty, being easily startled, anger outbursts, avoidance of COVID-related thoughts/information, distressing dreams).
- **Raw items:** `K1`, `L2`, `L5`–`L9_9`
- **Data source:** `Derived_Variable_Algorithm_and_Skip_Rules.xlsx`, `CUSP` tab, Section `Q5`
- **Dictionary:** Derived_Variable_Algorithm_and_Skip_Rules.xlsx
- **Example variable:** `L9_1` = "Had difficulty sleeping" (since becoming aware of the COVID-19 outbreak)

---

## Data Dictionary Structure (CUSP)

### `Derived_Variable_Algorithm_and_Skip_Rules.xlsx`, `CUSP` tab

| Column | Meaning |
|---|---|
| `Section` | Top-level questionnaire section (`Q1`–`Q5`) |
| `Construct` | Broad construct/domain label (e.g. "Substance Use", "Mental Health") |
| `Scale` | Named instrument within that construct (e.g. "AUDIT", "CAST") |
| `ITEM` | Variable name for that question |
| `Question` | Full question wording as shown to participants |
| `Response Codes` | Response options, generally in `CODE=Label` format, one option per column |

### `all_baselines_data_dictionary.xlsx`, `Data dictionary` tab

| Column | Meaning |
|---|---|
| `Domain` | Grouping used in the all baselines data dict (e.g. "Substance use", "Coping (Brief COPE)") |
| `Variable` | Exact variable name in the all baselines data dictionary |
| `Variable label` | Human-readable description, often including scoring range and proration rules |
| `Type` | Stata variable type (numeric, string, date) |
| `Stata format` | Stata display format code |
| `Value-label set` | Name of the linked value-label set, if categorical (see `Value labels` tab) |
| `N valid` / `N m
issing` / `% missing` | Completeness in the current dataset |
| `Range` | Observed value range or distinct-value count |
| `Distribution (numeric)` | Mean/SD/median, for numeric variables |
| `Categories (n)` | Category breakdown with counts, for categorical variables |


---



