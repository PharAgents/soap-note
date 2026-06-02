---
name: soap-note
description: Standardized clinical pharmacist SOAP note generator and drug therapy assessment tool. Assists pharmacists in documenting, evaluating, and reviewing patient drug therapy using the IESAC framework and the 7-category Drug Therapy Problem (DTP) methodology based on clinical guidelines.
license: MIT
metadata:
  author: Natapol Pornputtapong
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

## 5. information Gathering Rules

- Acquire all subjective data from the patient's history and self-reports. Do not infer or assume any information that is not explicitly provided.
- Only include objective data that is verifiable and documented in the patient's medical record or pharmacy dispensing logs. Do not fabricate or assume normal values for missing data.
- Ensure that all assessments and plans are directly supported by the subjective and objective data. Do not make clinical judgments that are not grounded in the provided information.
- Always reference current clinical guidelines and evidence-based practices when evaluating drug therapies and formulating plans. Do not recommend therapies that are not supported by guidelines or that contradict the patient's specific clinical context.
- When evaluating drug therapies, strictly apply the IESAC framework and reference current clinical guidelines. Do not recommend therapies that are not supported by evidence-based guidelines or that contradict the patient's specific clinical context.
- Always prioritize patient safety and adherence when formulating plans. Do not recommend changes that could increase the risk of adverse effects or reduce the likelihood of patient compliance without a clear therapeutic benefit.

---

## 6. Edge Case and Conflict Resolution
- **Incomplete Patient Data**: If vitals or lab values are missing, explicitly highlight the missing data in the **Objective** section and add a recommendation in the **Plan** to obtain them (e.g., "Order HbA1c and Serum Creatinine for the next clinic visit"). Do not assume or fabricate normal values.
- **Patient Discrepancies**: If a patient's self-reported adherence contradicts pharmacy dispensing records, document both (e.g., "Patient reports high adherence, but PDC calculated from dispensing logs is 0.45 [low]"). Address the discrepancy empathetically in the **Assessment** under Adherence and include a supportive adherence intervention in the **Plan**.
- **Clinical Urgency / Red Flags**: If the patient presents with hypertensive crisis (BP > 180/120 mmHg with target organ damage signs), severe hypoglycemia (confusion, unconsciousness), or symptoms of angioedema, bypass routine outpatient planning and recommend immediate referral to the Emergency Department.

---

## 7. Verified Academic and Clinical References
The guidelines and standards contained within this skill are derived from verified clinical publications and the national pharmacy practice curriculum:

1. **Hospital Pharmacy Association of Thailand.** *Pharmaceutical Care for Hospitalized Patients.* In: Ningsanond T, Duangngern T, Chaichanamongkol W, Monthakantikul P, editors. Essential Guidelines for Pharmaceutical Care. 1st ed. Bangkok: Prachachon Co., Ltd.; 2015. p. 19-32.
2. **Sontisombat P.** *Guidelines for SOAP Note Documentation.* In: Working Group for the Development of Clerkship Practice in Pharmaceutical Care for Health Promotion, editors. Handbook of Clerkship Practice in Pharmaceutical Care. n.p.: Clerkship Network for Health Promotion; 2009. p. 56-69.