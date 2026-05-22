# Soteria SOW Guardian - Option B Architecture Design

Name: NGUYEN NGOC TIEN
Matriculation ID: M2506667B
Email: NGOCTIEN001@E.NTU.EDU.SG

Data collaboration: None. Synthetic data was created individually for this submission.
Recording link: https://github.com/NGUYENNGOCTIEN-COLLAB/MH6822-REGULATION-TECHNOLOGY---OCBC-SOW-Guardian-RegTech/blob/main/Homework_1.mp3

## Project overview

Task 1 and 2: 

## What this tool does

The tool is a governance layer for AI-assisted source-of-wealth review. It checks whether AI-generated source-of-wealth narratives are supported by evidence, whether human reviewers are exercising real judgment, and whether the right Singapore or US regulatory logic is active.

## What this tool does not do

The tool does not make final legal determinations, approve customers automatically, file suspicious transaction or suspicious activity reports automatically, replace relationship managers or compliance officers, perform full AML transaction monitoring, or claim that a case is simply "MAS compliant" or "US compliant".

## Data note

The dataset in `data/synthetic_sow_cases.csv` is fully synthetic. It contains simulated KYC/source-of-wealth cases to demonstrate how the architecture would process evidence sufficiency, contradiction counts, human challenge, jurisdictional conflicts, and model drift. It does not contain real OCBC, Bank of Singapore, or customer data.

Task 3:

This repository contains the Task 3 submission for Assignment 1 in MH6822 Regulatory Technology.

The selected regulated entity is **OCBC Bank Ltd**. The selected jurisdictions are **Singapore** and the **United States**. The selected domain is **AI model risk management and AI governance for AML/KYC source-of-wealth due diligence**.

The tool design is called **Soteria SOW Guardian: Jurisdiction-Aware AI Governance Monitor for KYC Source-of-Wealth Review**.

I selected **Option B - Architecture Design**. The repository therefore contains a system architecture document, visual mockups, data-flow and decision-point materials, a jurisdiction rule engine, failure-mode analysis, synthetic data, and a senior-management pitch deck.

## Repository structure

```text
.
├── README.md
├── docs/
│   ├── Task3_One_Page_Summary.pdf
│   ├── Task3_One_Page_Summary.md
│   ├── Task3_Architecture_Design.pdf
│   └── Task3_Architecture_Design.md
├── deck/
│   ├── Task3_Senior_Management_Pitch.pdf
│   └── Task3_Senior_Management_Pitch.pptx
├── mockups/
│   ├── Mockup_0_System_Architecture.png
│   ├── Mockup_1_Senior_Dashboard.png
│   ├── Mockup_2_Case_Jurisdiction_Output.png
│   ├── Mockup_3_Evidence_Graph.png
│   ├── Mockup_4_Human_Challenge_Log.png
│   └── Mockup_5_Rule_Version_Diff.png
├── rule_engine/
│   ├── jurisdiction_rules_examples.yml
│   ├── pseudocode_decision_logic.md
│   └── scoring_thresholds.md
├── data/
│   ├── synthetic_sow_cases.csv
│   └── data_dictionary.md
├── failure_modes/
│   └── failure_mode_risk_register.md
└── sources/
    ├── regulatory_source_map.md
    └── references.md
```
