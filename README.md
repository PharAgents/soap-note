# Pharmacist SOAP Note Agent Skill

Standardized clinical pharmacy agent skill designed to assist pharmacists and healthcare AI agents in drafting, evaluating, and reviewing structured Subjective, Objective, Assessment, and Plan (SOAP) notes. 

This repository implements the **Agent Skills Specification** (fully defined in [SKILL.md](SKILL.md)) and integrates standard clinical pharmacy practices in Thailand.

---

## 📂 Repository Structure

```
soap-note/
├── SKILL.md              # Core skill: clinical rules, IESAC guidelines, & patient case study
└── README.md             # Repository documentation (this file)
```

---

## ⚙️ Installation

To use this skill, ensure your AI agent or development environment supports the [Agent Skills](https://agentskills.io) specification (e.g., Claude Code, VS Code Agent extensions, or custom clinical assistants).

### Loading the Skill

1. **Clone this repository** into your local agent skills path or your project directory:
   ```bash
   git clone https://github.com/your-username/soap-note.git
   ```

2. **Configure your AI Agent** to load the skill directory:
   - For CLI-based agents, pass the skill directory in your system configuration or project environment.
   - The agent will automatically detect and parse the `SKILL.md` frontmatter at startup to register the `soap-note` skill trigger.

3. **Verify the installation**:
   To validate that the `SKILL.md` frontmatter and formatting are correct, you can use the reference library:
   ```bash
   npx skills-ref validate ./soap-note
   ```

---

## 🚀 Usage

Once installed, the AI agent will automatically activate this skill when presented with clinical patient cases, medication reconciliation tasks, or requests to write pharmacy documentation.

### Triggering the Skill (Example Prompts)

You can trigger the skill by providing prompts such as:
- *"Draft a pharmacist SOAP note for a 65-year-old female with uncontrolled hypertension and diabetes who is non-compliant with her metformin."*
- *"Evaluate the following patient drug regimen for drug-related problems (DTPs) using the IESAC framework."*
- *"Format a clinical note based on these vitals and lab results: BP 155/95, HbA1c 8.5%, taking Enalapril 5mg daily."*

### Standard Output Structure

The skill guides the agent to format all outputs using the standardized clinical layout below:

1. **Patient Demographics**: Key indices, weight/height, and calculated Cockcroft-Gault Creatinine Clearance ($Cl_{cr}$).
2. **Subjective (S)**: Chief Complaint, HPI, PMH, Social History (diet, exercise), Allergies, and Medication Reconciliation.
3. **Objective (O)**: Vital signs, physical exams, laboratory values (HbA1c, fasting glucose, serum creatinine, electrolytes), and dispensing history.
4. **Assessment (A)**: Prioritized medical problem list. For each disease, the agent performs:
   - **Etiology (สาเหตุ)**: Investigating pathophysiological causes and classifying the DRP type.
   - **Risk Factors (ปัจจัยเสี่ยง)**: Pre-disposing conditions.
   - **Severity & Urgency (ความรุนแรง)**: Clinical severity classification.
   - **Therapeutic Evaluation (IESAC)**: In-depth evaluation against Clinical Guidelines (e.g., ADA, ACC/AHA, Thai Hypertension Guidelines) on:
     - **Indication**: Checking for untreated or unnecessary drug therapies.
     - **Efficacy**: Reviewing the optimal drug selection, correct dosing (adjusted for clearance), dosage form, and duration.
     - **Safety**: Monitoring ADRs, high doses, and drug interactions.
     - **Adherence & Cost**: Identifying patient-specific barriers and cost-effectiveness.
5. **Plan (P)**: Specific therapeutic goals, pharmacological changes, non-pharmacological lifestyle recommendations, monitoring parameters (split into efficacy and toxicity), and concrete patient counseling (e.g., managing hypoglycemia).

---

## 📚 References

The clinical logic, DRP classifications, and documentation rules are derived from verified clinical texts:
* **Strand LM, et al.** *Drug-related problems: their structure and function.* DICP. 1990 Nov; 24(11):1093-7.
* **Hospital Pharmacy Association of Thailand.** *Pharmaceutical Care for Hospitalized Patients.* In: Essential Guidelines for Pharmaceutical Care; 2015.
* **American Diabetes Association (ADA).** *Standards of Care in Diabetes—2026.*
* **ACC/AHA Joint Committee.** *Guidelines for the Prevention, Detection, Evaluation, and Management of High Blood Pressure.*
