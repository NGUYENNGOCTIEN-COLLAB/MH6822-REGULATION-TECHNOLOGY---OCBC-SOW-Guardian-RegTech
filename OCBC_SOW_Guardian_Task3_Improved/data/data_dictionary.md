# Synthetic Data Dictionary

The file `synthetic_sow_cases.csv` contains simulated KYC/source-of-wealth governance cases. The data is synthetic and does not contain real customer, OCBC, or Bank of Singapore information.

| Column | Type | Description |
|---|---|---|
| case_id | string | Synthetic case identifier. |
| jurisdiction | string | Primary jurisdiction label: Singapore, United States, or Cross-border. |
| booking_location | string | Where the relationship is booked or primarily reviewed. |
| sg_touchpoint | boolean | Whether the case has a Singapore regulatory touchpoint. |
| us_touchpoint | boolean | Whether the case has a US regulatory touchpoint. |
| customer_type | string | Synthetic customer category. |
| ai_system_type | string | Type of AI system used: agentic_ai, generative_ai, non_generative_ai, or traditional_statistical_model. |
| evidence_coverage_ratio | float | Supported material claims divided by total material claims. |
| unsupported_claim_rate | float | Unsupported AI-generated material claims divided by all material AI claims. |
| contradiction_count | integer | Number of material conflicts between AI narrative and source documents. |
| human_challenge_rate | float | Whether and how often reviewers challenged AI outputs, represented as a percentage for demonstration. |
| model_drift_flag | boolean | Whether the case is affected by a drift warning. |
| jurisdiction_conflict_flag | boolean | Whether cross-border or contradictory jurisdiction handling is required. |
| privacy_exception_flag | boolean | Whether a data-handling or privacy exception is present. |
| rule_set_triggered | string | Simulated rule modules triggered by the case. |
| final_tool_output | string | Tool output: Green, Amber, Red friction, Amber + governance gap, or Red friction + governance gap. |
| human_owner | string | Primary human owner responsible for the next decision. |
| explanation | string | Plain-language reason for the output. |
