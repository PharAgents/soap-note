---
name: soap-note
description: Standardized clinical pharmacist SOAP note generator and drug therapy assessment tool. Assists pharmacists in documenting, evaluating, and reviewing patient drug therapy using the IESAC framework and the 7-category Drug Therapy Problem (DTP) methodology based on clinical guidelines.
license: MIT
metadata:
  author: Antigravity
  version: 1.0.0
  domain: Clinical Pharmacy / Medication Therapy Management (MTM)
  standards: IESAC Framework, Strand's DTP Classification, ADA Guidelines, ACC/AHA Guidelines
---

# Pharmacist Clinical SOAP Note Generator

This skill enables AI agents to assist pharmacists in writing, reviewing, and formatting high-quality, professional, and structured **SOAP (Subjective, Objective, Assessment, Plan)** notes. It strictly adheres to the clinical pharmacy practice guidelines taught in Thailand, incorporating the **IESAC** evaluation framework, drug-related problem (DRP) identification, and guideline-directed medical therapy (GDMT).

---

## 1. Trigger Conditions
Activate this skill when:
- The user requests to draft, review, or format a clinical pharmacy SOAP note.
- Performing Comprehensive Medication Management (CMM) or Medication Therapy Management (MTM) evaluations.
- Reviewing patient cases to identify Drug Therapy Problems (DTPs) / Drug-Related Problems (DRPs).
- Documenting clinical pharmacy interventions, patient counseling, or pharmacotherapy recommendations.

---

## 2. Clinical Assessment Framework (IESAC)
Every SOAP note must assess drug therapies using the **IESAC** (Indication, Efficacy, Safety, Adherence, Cost) principles to ensure systematic clinical evaluation.

### I — Indication (ข้อบ่งใช้)
- **Unnecessary Drug Therapy**: Is the patient taking a medication without a valid clinical indication?
- **Needs Additional Drug Therapy**: Does the patient have an untreated or under-treated medical condition that requires a new medication (e.g., missing a statin in a diabetic patient with high cardiovascular risk)?

### E — Efficacy (ประสิทธิภาพ)
Evaluate if the current medication achieves therapeutic targets. Specifically analyze:
1. **Optimal Therapy (Drug of Choice)**: Is this the first-line medication recommended by international or local guidelines (e.g., ADA for diabetes, ACC/AHA or Thai Hypertension Guidelines for hypertension)?
2. **Correct Dose**: Is the dose appropriate? Is it too low to achieve therapeutic goals? Has it been adjusted based on patient-specific factors like age, weight, and renal function (e.g., Cocroft-Gault $Cl_{cr}$)?
3. **Correct Dosage Form**: Is the dosage form optimal for the patient's condition (e.g., oral vs. intravenous, immediate-release vs. extended-release)?
4. **Correct Duration**: Is the treatment duration appropriate (especially for acute conditions like infections or short-term steroid courses)?
5. **Drug Required / Duplication**: Is there therapeutic duplication that could be consolidated to reduce pill burden?

### S — Safety (ความปลอดภัย)
- **Adverse Drug Reactions (ADR)**: Is the patient experiencing side effects or toxicities?
- **Dose Too High**: Is the dose exceeding therapeutic limits or renal adjustment guidelines?
- **Interactions**: Are there clinically significant drug-drug, drug-food, or drug-disease interactions?
- **Contraindications**: Are there patient factors (e.g., pregnancy, organ failure, allergy history) that contraindicate the therapy?

### A — Adherence (ความร่วมมือในการใช้ยา)
- **Patient Compliance**: Is the patient taking the medication as prescribed?
- **Barriers**: Identify reasons for non-adherence, such as side effects, complex dosing schedules, forgetfulness, physical difficulties (e.g., swallowing, opening bottles), or cognitive impairment.

### C — Cost (ราคาและความคุ้มค่า)
- **Affordability**: Can the patient afford the medication? Is it covered under their health insurance/welfare scheme?
- **Cost-Effectiveness**: Can a generic alternative be recommended to improve adherence and reduce financial toxicity?

---

## 3. Structural Guidelines for the SOAP Note
When documenting a case, structure the output using the following four sections. All data in **S** and **O** must directly align with and support the assessments in **A** and plans in **P**.

### S: Subjective Data (ข้อมูลเชิงอัตวิสัย)
Record all relevant self-reported information gathered from patient interviews or caregivers:
- **Chief Complaint (CC)**: The primary reason for the patient's visit, in their own words.
- **History of Present Illness (HPI)**: Progression of symptoms, aggravating/alleviating factors, onset, and duration.
- **Past Medical History (PMH) & Family History (FH)**: Chronic conditions, past hospitalizations, and relevant familial health conditions.
- **Social History (SH)**: Lifestyle habits (diet, sodium/carbohydrate intake, smoking status, alcohol consumption, exercise/physical activity).
- **Allergies & Adverse Drug Reactions**: Complete list of food/drug allergies, including specific reaction types (e.g., maculopapular rash, anaphylaxis).
- **Current Medications (Medication Reconciliation)**: Name, strength, dose, route, frequency, indication, and self-reported adherence for all Rx, OTC, herbals, and supplements.

### O: Objective Data (ข้อมูลเชิงวัตถุวิสัย)
Record all verifiable, measurable, and documented data:
- **Vital Signs (V/S)**: Blood Pressure (BP - specify seated/standing and arm), Heart Rate (HR), Respiratory Rate (RR), Temperature (Temp).
- **Physical Exam (PE)**: Relevant clinical findings (e.g., bilateral pitting edema, diabetic foot ulcers, chest clear to auscultation).
- **Laboratory Values (Labs)**: Glycemic markers (FBS, HbA1c), renal markers ($SCr$, $BUN$, calculated $eGFR$ or $Cl_{cr}$), lipid panels (TC, TG, HDL, LDL), electrolytes (K+, Na+), liver function tests (AST, ALT), or therapeutic drug monitoring levels.
- **Diagnostics**: Chest X-ray, ECG, echocardiogram, etc.
- **Pharmacy Dispensing Logs**: Refill history, pill counts, or Proportion of Days Covered (PDC) to objectify adherence.

### A: Assessment (การประเมินการรักษา)
Perform a detailed clinical analysis for each medical problem identified. For each problem, evaluate:
1. **Etiology (สาเหตุ)**: The pathophysiological cause or identification of the problem as a **Drug-Related Problem (DRP)** (e.g., drug-induced disease, untreated indication, side effect).
2. **Risk Factors (ปัจจัยเสี่ยง)**: Patient-specific predisposing factors contributing to the problem or potential drug toxicities (e.g., age, poor diet, renal impairment).
3. **Severity (ความรุนแรง)**: Clinical severity (Mild, Moderate, Severe) and urgency (Acute vs. Chronic, emergency vs. routine follow-up).
4. **Current / Proposed Treatment Evaluation (การรักษาที่ได้รับ/ควรได้รับ)**: Apply the **IESAC** framework with professional therapeutic rationale supported by current clinical guidelines (e.g., ADA Standards of Care, JNC-8/ACC/AHA Hypertension Guidelines, Thai Hypertension Guidelines).
   - Evaluate drug of choice, dosage adjustments for renal clearance, safety/interaction profiles, and adherence.

### P: Plan (แผนการรักษาและการติดตาม)
Formulate an actionable, comprehensive plan to address all identified clinical and drug-related problems:
1. **Therapeutic Goals (เป้าหมายการรักษา)**: Set specific, measurable, and guideline-directed targets (e.g., BP < 130/80 mmHg, HbA1c < 7.0%, LDL-C < 70 mg/dL).
2. **Therapeutic Plan (แผนการรักษา)**:
   - *Pharmacological*: Specific medication adjustments, discontinuations, or initiations (include exact drug name, strength, dose, route, frequency, and duration).
   - *Non-Pharmacological*: Dietary modifications (e.g., DASH diet, sodium restriction < 2,300 mg/day, carbohydrate counting), exercise regimen (e.g., aerobic exercise 150 mins/week), and smoking cessation.
3. **Monitoring Plan (แผนการติดตามผล)**: Specify what to check, when, and who will perform the check.
   - *Efficacy Parameters*: Monitoring markers to ensure the drug is working (e.g., home BP logs, self-monitoring of blood glucose [SMBG], follow-up HbA1c in 3 months).
   - *Safety/Toxicity Parameters*: Monitoring markers to identify adverse effects early (e.g., check $SCr$ and potassium 1-2 weeks after starting an ACEi/ARB, evaluate for muscle soreness/CK after statin initiation, evaluate for dry cough or peripheral edema).
4. **Patient Education (การให้ความรู้ผู้ป่วย)**: Critical drug counseling points, including correct administration techniques (e.g., insulin pen, inhalers), management of potential side effects (e.g., identifying and treating hypoglycemia), and compliance strategies.
5. **Future Plan (แผนการรักษาในอนาคต)**: Outline the step-up therapy or backup plan if current therapeutic changes do not reach goal within a specified timeframe (e.g., "If BP remains > 130/80 mmHg at 4-week follow-up, consider adding Low-Dose Chlorthalidone 1.25 mg daily").

---

## 4. Standard Pharmacy SOAP Note Template
Use this standardized Markdown template for all generated notes to ensure professional delivery:

```markdown
# CLINICAL PHARMACY SOAP NOTE
**Date:** [YYYY-MM-DD] | **Pharmacist:** [Name/ID]

## PATIENT DEMOGRAPHICS
- **Patient Name/ID:** [Initials/ID] | **Age/Gender:** [Age] / [M/F]
- **Height/Weight:** [cm] / [kg] | **BMI:** [kg/m²]
- **Calculated CrCl:** [mL/min] (using Cockcroft-Gault with actual/ideal body weight)

---

## S: SUBJECTIVE DATA
- **Chief Complaint (CC):** "[Patient's direct words]"
- **History of Present Illness (HPI):** [Detailed chronological history]
- **Past Medical History (PMH):** [Chronic conditions, past events]
- **Social History (SH):** [Diet, exercise, tobacco, alcohol, etc.]
- **Allergies & ADR History:** [Drug/Food allergen - specific reaction]
- **Current Medications & Adherence:**
  | Medication | Regimen | Indication | Self-Reported Adherence |
  | :--- | :--- | :--- | :--- |
  | [Drug A] | [Dose, route, frequency] | [Indication] | [High/Medium/Low + details] |

---

## O: OBJECTIVE DATA
- **Vital Signs:** BP [mmHg], HR [bpm], RR [/min], Temp [°C]
- **Physical Examination (PE):** [Relevant findings, e.g., edema, foot check]
- **Laboratory Values:**
  | Test | Value | Reference Range | Date |
  | :--- | :--- | :--- | :--- |
  | [Lab A] | [Value] | [Range] | [Date] |
- **Dispensing History / Pill Counts:** [Relevant data]

---

## A: ASSESSMENT
### Problem 1: [Disease/Problem Name] (Status: [Controlled / Uncontrolled / Worsened])
- **Etiology:** [Pathophysiology / drug-induced / DRP type]
- **Risk Factors:** [Patient-specific factors contributing to progression/safety risks]
- **Severity:** [Mild/Moderate/Severe] | **Urgency:** [Acute/Chronic]
- **Therapeutic Evaluation (IESAC):**
  - *Indication:* [Is therapy indicated? Are there untreated indications?]
  - *Efficacy:* [Guideline assessment. Is current drug/dose optimal?]
  - *Safety:* [Side effects, interactions, renal dosing limits]
  - *Adherence:* [Barriers identified]
  - *Cost:* [Affordability and cost-effectiveness]

### Problem 2: [Disease/Problem Name] ...
[Repeat for all active medical problems]

---

## P: PLAN
### Problem 1: [Disease/Problem Name]
- **Therapeutic Goals:** [Target values with guidelines cited]
- **Therapeutic Plan:**
  - *Pharmacological:* [Drug, dose, route, frequency, duration changes]
  - *Non-Pharmacological:* [Lifestyle modifications, DASH diet, sodium limits]
- **Monitoring Plan:**
  - *Efficacy:* [Parameters + Timeline]
  - *Safety/Toxicity:* [Parameters + Timeline]
- **Patient Education:** [Key counseling points, administration, side-effect actions]
- **Future Plan:** [Alternative plan if targets are not met]

### Problem 2: [Disease/Problem Name] ...
[Repeat for all active medical problems]
```

---

## 5. Realistic Clinical Example (T2DM and Hypertension)
Below is a highly professional, verified, and complete SOAP note generated by this skill for an uncontrolled diabetic and hypertensive patient.

### Patient Case Scenario:
*A 62-year-old male with Type 2 Diabetes (diagnosed 5 years ago) and Hypertension (diagnosed 3 years ago) presents for an MTM review. He complains of frequent urination at night and occasional dizziness when standing up. He takes Metformin 500 mg BID and Enalapril 5 mg once daily. He admits to eating white rice and high-sodium curries frequently, and does not exercise regularly. He sometimes forgets his evening Metformin dose due to working late. Vital signs: BP 146/92 mmHg (seated), HR 72 bpm, Wt 80 kg, Ht 170 cm (BMI 27.7 kg/m²). Labs: $SCr$ 1.2 mg/dL, HbA1c 8.2%, FBS 165 mg/dL. calculated $Cl_{cr}$ = 68.3 mL/min.*

```markdown
# CLINICAL PHARMACY SOAP NOTE
**Date:** 2026-06-02 | **Pharmacist:** Jane Doe, Pharm.D.

## PATIENT DEMOGRAPHICS
- **Patient Name/ID:** T.S. | **Age/Gender:** 62 / Male
- **Height/Weight:** 170 cm / 80 kg | **BMI:** 27.7 kg/m² (Overweight)
- **Calculated CrCl:** 68.3 mL/min (using Cockcroft-Gault equation with actual body weight)

---

## S: SUBJECTIVE DATA
- **Chief Complaint (CC):** "I have frequent urination at night, and sometimes feel dizzy when I stand up quickly."
- **History of Present Illness (HPI):** 62-year-old male with a history of T2DM (5 years) and HTN (3 years) presents for a routine Medication Therapy Management (MTM) visit. Reports mild nocturia (3-4 times per night) and orthostatic lightheadedness when changing positions rapidly. Denies chest pain, dyspnea, headaches, or palpitations.
- **Past Medical History (PMH):** Type 2 Diabetes Mellitus (T2DM) x 5 years, Hypertension (HTN) x 3 years. No history of cardiovascular disease, stroke, or chronic kidney disease.
- **Social History (SH):** Consumes high-carbohydrate meals (white rice) and high-sodium Thai curries. Sedentary lifestyle with no regular exercise. Non-smoker, denies alcohol use.
- **Allergies & ADR History:** NKDA (No Known Drug Allergies).
- **Current Medications & Adherence:**
  | Medication | Regimen | Indication | Self-Reported Adherence |
  | :--- | :--- | :--- | :--- |
  | Metformin | 500 mg PO BID (after breakfast & dinner) | Type 2 Diabetes | Suboptimal (forgets ~2-3 evening doses per week due to late work hours) |
  | Enalapril | 5 mg PO daily (after breakfast) | Hypertension | High (takes consistently every morning) |

---

## O: OBJECTIVE DATA
- **Vital Signs:** 
  - BP: 146/92 mmHg (seated, right arm, repeat 144/90 mmHg)
  - HR: 72 bpm (regular rhythm)
  - RR: 16 breaths/min
  - Temp: 36.6 °C
- **Physical Examination (PE):**
  - Extremities: Warm, dry, no peripheral edema. 
  - Foot Examination: Normal sensation to 10-g monofilament bilaterally; skin intact, no ulcers or calluses.
- **Laboratory Values:**
  - HbA1c: 8.2% (Date: 2026-06-01)
  - Fasting Blood Sugar (FBS): 165 mg/dL (Date: 2026-06-02)
  - Serum Creatinine (SCr): 1.2 mg/dL (Date: 2026-06-01)
  - Potassium ($K^+$): 4.1 mEq/L (Date: 2026-06-01)
  - Lipid Panel: TC 210 mg/dL, TG 180 mg/dL, HDL 42 mg/dL, LDL-C 132 mg/dL

---

## A: ASSESSMENT

### Problem 1: Uncontrolled Type 2 Diabetes Mellitus (Status: Uncontrolled)
- **Etiology:** Suboptimal glycemic control due to suboptimal medication dosing, patient non-adherence (missing evening Metformin), and poor dietary habits (high carbohydrate intake).
- **Risk Factors:** Age (62), overweight status (BMI 27.7), elevated baseline LDL-C (132 mg/dL), and co-existing HTN increase the risk of macrovascular (ASCVD) and microvascular (nephropathy, neuropathy) complications.
- **Severity:** Moderate | **Urgency:** Chronic, requires therapy optimization over the next 1-3 months.
- **Therapeutic Evaluation (IESAC):**
  - *Indication:* Indicated. Metformin is appropriate. However, there is an **untreated indication** for cardiovascular risk reduction. Based on the 2026 ADA Standards of Care, patients with T2DM and high cardiovascular risk (age ≥ 50, HTN, dyslipidemia) require primary prevention with a moderate-to-high intensity statin.
  - *Efficacy:* Suboptimal. Fasting glucose (165 mg/dL; target 80-130) and HbA1c (8.2%; target < 7.0%) are elevated. The current dose of Metformin (500 mg BID = 1000 mg/day) is below the typical therapeutic target dose of 2,000 mg/day. Optimization of Metformin is the primary strategy before adding a second oral glucose-lowering agent.
  - *Safety:* Metformin is safe at this renal clearance ($CrCl$ 68.3 mL/min). Metformin is only contraindicated if $eGFR$ or $CrCl$ falls below 30 mL/min, with caution and dose reduction advised if it is between 30-45 mL/min. No signs of lactic acidosis or severe gastrointestinal upset.
  - *Adherence:* Suboptimal. The patient forgets the evening dose due to late working hours. Simplifying the regimen (e.g., using extended-release Metformin XR once daily in the morning) would overcome this barrier.
  - *Cost:* Highly cost-effective; Metformin is available as a low-cost generic under the national universal coverage scheme in Thailand.

### Problem 2: Uncontrolled Hypertension (Status: Uncontrolled)
- **Etiology:** Elevated BP due to suboptimal dose of antihypertensive therapy, high dietary sodium intake, and lack of exercise.
- **Risk Factors:** Diabetes, age, high sodium intake.
- **Severity:** Moderate | **Urgency:** Chronic, requires drug titration and monitoring over 2-4 weeks.
- **Therapeutic Evaluation (IESAC):**
  - *Indication:* Indicated. Enalapril is highly appropriate as first-line therapy because ACE inhibitors provide renal protection in patients with diabetes.
  - *Efficacy:* Suboptimal. Seated BP is 146/92 mmHg, which is above the guideline-directed target of < 130/80 mmHg for patients with diabetes (ACC/AHA and ADA Guidelines). The current dose of Enalapril (5 mg daily) is low; the maximum effective dose is 40 mg daily (typically dosed 10-20 mg once or twice daily). Titration is warranted.
  - *Safety:* Currently safe. Serum potassium (4.1 mEq/L) is within normal range (3.5-5.0 mEq/L) and renal function is stable ($SCr$ 1.2 mg/dL). ACE inhibitors carry risks of hyperkalemia, acute kidney injury (AKI), and dry cough. Titrating Enalapril requires checking renal function and electrolytes within 1-2 weeks. The patient's reported "dizziness when standing up" suggests mild orthostasis; BP should be monitored closely during titration.
  - *Adherence:* High. The patient consistently takes his morning dose.
  - *Cost:* Highly cost-effective; generic Enalapril is fully covered under national health insurance.

---

## P: PLAN

### Problem 1: Uncontrolled Type 2 Diabetes Mellitus
- **Therapeutic Goals:**
  - HbA1c < 7.0% (ADA Guidelines)
  - Fasting Blood Sugar (FBS) 80 - 130 mg/dL
  - Prevent microvascular and macrovascular complications
- **Therapeutic Plan:**
  - *Pharmacological:* 
    1. **Discontinue** Metformin (immediate-release) 500 mg BID.
    2. **Initiate** Metformin XR (extended-release) 1,000 mg PO daily with breakfast. (Simplifies regimen to morning-only dosing to resolve late-night non-adherence. Titrate to 2,000 mg daily in 2 weeks if tolerated).
    3. **Initiate** Atorvastatin 20 mg PO daily at bedtime (Moderate-intensity statin for primary prevention of ASCVD in a diabetic patient aged 40-75 with LDL-C > 70 mg/dL per ADA guidelines).
  - *Non-Pharmacological:* Dietary counseling focusing on portion control, substituting white rice with brown rice, reducing sugar-sweetened beverages, and increasing dietary fiber. Recommend a minimum of 150 minutes per week of moderate-intensity aerobic physical activity (e.g., brisk walking 30 minutes, 5 days/week).
- **Monitoring Plan:**
  - *Efficacy:* Fasting blood glucose (target 80-130 mg/dL) measured via SMBG 2-3 times per week. Follow-up HbA1c in 3 months.
  - *Safety:* Monitor for gastrointestinal side effects (bloating, diarrhea - minimized by XR formulation). Monitor for muscle pain, soreness, or weakness (statin-associated muscle symptoms) and evaluate baseline liver enzymes (ALT/AST) if symptoms occur.
- **Patient Education:** Counsel on the importance of taking Metformin XR with a meal to minimize GI upset. Educate on signs of hypoglycemia (sweating, shakiness, confusion) and the "Rule of 15" treatment (15g rapid-acting carbs, recheck glucose in 15 mins), although hypoglycemia risk is low with Metformin monotherapy.
- **Future Plan:** If HbA1c remains > 7.0% after 3 months on Metformin XR 2,000 mg daily, consider adding an SGLT2 inhibitor (e.g., Empagliflozin 10 mg daily) or a GLP-1 receptor agonist, which provide cardiorenal benefits.

### Problem 2: Uncontrolled Hypertension
- **Therapeutic Goals:**
  - Target BP < 130/80 mmHg (ACC/AHA and ADA Guidelines)
  - Prevent stroke, myocardial infarction, and diabetic nephropathy
- **Therapeutic Plan:**
  - *Pharmacological:* 
    1. **Titrate** Enalapril from 5 mg daily to 10 mg PO daily in the morning (after breakfast).
  - *Non-Pharmacological:* DASH (Dietary Approaches to Stop Hypertension) diet, restricting sodium intake to < 2,300 mg/day (ideally < 1,500 mg/day). Counsel the patient on slowly rising from a seated or lying position to minimize orthostatic dizziness.
- **Monitoring Plan:**
  - *Efficacy:* Home BP monitoring twice daily (morning and evening, seated, after 5 minutes of rest). Target BP < 130/80 mmHg.
  - *Safety:* Recheck $SCr$ and Serum Potassium levels in 1-2 weeks to screen for drug-induced hyperkalemia or acute renal impairment (an increase in $SCr$ of up to 30% from baseline is acceptable). Monitor for the development of a dry, hacking cough (ACE inhibitor class effect).
- **Patient Education:** Inform the patient that Enalapril protects his kidneys from diabetes-related damage. Advise him to report any dry cough, facial swelling (angioedema - emergency), or severe lightheadedness immediately.
- **Future Plan:** If BP remains > 130/80 mmHg at 4-week follow-up despite Enalapril 10 mg daily, consider titrating Enalapril to 20 mg daily, or adding a calcium channel blocker (e.g., Amlodipine 5 mg daily) or a thiazide-like diuretic (e.g., Chlorthalidone 1.25-2.5 mg daily).
```

---

## 6. Edge Case and Conflict Resolution
- **Incomplete Patient Data**: If vitals or lab values are missing, explicitly highlight the missing data in the **Objective** section and add a recommendation in the **Plan** to obtain them (e.g., "Order HbA1c and Serum Creatinine for the next clinic visit"). Do not assume or fabricate normal values.
- **Patient Discrepancies**: If a patient's self-reported adherence contradicts pharmacy dispensing records, document both (e.g., "Patient reports high adherence, but PDC calculated from dispensing logs is 0.45 [low]"). Address the discrepancy empathetically in the **Assessment** under Adherence and include a supportive adherence intervention in the **Plan**.
- **Clinical Urgency / Red Flags**: If the patient presents with hypertensive crisis (BP > 180/120 mmHg with target organ damage signs), severe hypoglycemia (confusion, unconsciousness), or symptoms of angioedema, bypass routine outpatient planning and recommend immediate referral to the Emergency Department.

---

## 7. Verified Academic and Clinical References
The guidelines and standards contained within this skill are derived from verified clinical publications and the national pharmacy practice curriculum:

1. **Hospital Pharmacy Association of Thailand.** *Pharmaceutical Care for Hospitalized Patients.* In: Ningsanond T, Duangngern T, Chaichanamongkol W, Monthakantikul P, editors. Essential Guidelines for Pharmaceutical Care. 1st ed. Bangkok: Prachachon Co., Ltd.; 2015. p. 19-32.
2. **Duangngern T.** *Drug-Related Problems and Classification.* In: Ningsanond T, Duangngern T, Chaichanamongkol W, Monthakantikul P, editors. Essential Guidelines for Pharmaceutical Care. 1st ed. Bangkok: Prachachon Co., Ltd.; 2015. p. 197-206.
3. **Strand LM, Morley PC, Cipolle RJ, Ramsey R, Lamsam GD.** *Drug-related problems: their structure and function.* DICP (Annals of Pharmacotherapy). 1990 Nov; 24(11):1093-7. [PMID: 2275231](https://pubmed.ncbi.nlm.nih.gov/2275231) | [DOI: 10.1177/106002809002401117](https://doi.org/10.1177/106002809002401117)
4. **Kirsten KV, Hege SB, Trond AM, et al.** *Interview of patients by pharmacist contributes significantly to the identification of drug-related problem (DRPs).* Pharmacoepidemiol Drug Saf. 2006 Sep; 15(9):667-74. [PMID: 16736502](https://pubmed.ncbi.nlm.nih.gov/16736502) | [DOI: 10.1002/pds.1272](https://doi.org/10.1002/pds.1272)
5. **Sontisombat P.** *Guidelines for SOAP Note Documentation.* In: Working Group for the Development of Clerkship Practice in Pharmaceutical Care for Health Promotion, editors. Handbook of Clerkship Practice in Pharmaceutical Care. n.p.: Clerkship Network for Health Promotion; 2009. p. 56-69.
6. **American Diabetes Association (ADA).** *Standards of Care in Diabetes—2026.* Diabetes Care. 2026 Jan; 49(Suppl 1):S1-S312. [Standards of Care 2026](https://professional.diabetes.org/standards-of-care)
7. **Whelton PK, Carey RM, Aronow WS, et al.** *2017 ACC/AHA/AAPA/ABC/ACPM/AGS/APhA/ASH/ASPC/NMA/PCNA Guideline for the Prevention, Detection, Evaluation, and Management of High Blood Pressure in Adults.* J Am Coll Cardiol. 2018 May; 71(19):e127-e248. [PMID: 29146535](https://pubmed.ncbi.nlm.nih.gov/29146535) | [DOI: 10.1016/j.jacc.2017.11.006](https://doi.org/10.1016/j.jacc.2017.11.006)
8. **Thai Hypertension Society.** *2019 Thai Guidelines on the Treatment of Hypertension.* Bangkok: Thai Hypertension Society; 2019. [Thai Hypertension Guidelines](http://www.thaihypertension.org)
