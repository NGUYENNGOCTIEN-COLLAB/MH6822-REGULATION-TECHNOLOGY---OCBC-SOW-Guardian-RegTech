# Pseudocode Decision Logic

```python
def evaluate_case(case):
    active_rules = []
    warnings = []

    if case.booking_location == "Singapore" or case.sg_touchpoint:
        active_rules.extend(["SG-AML-626", "SG-AI-MRM", "SG-FEAT", "SG-Veritas"])

    if case.booking_location == "United States" or case.us_touchpoint:
        active_rules.append("US-CDD-FINCEN")

    if case.ai_system_type in ["generative_ai", "agentic_ai"]:
        if case.booking_location == "Singapore" or case.sg_touchpoint:
            active_rules.append("SG-AI-MRM")
        if case.booking_location == "United States" or case.us_touchpoint:
            active_rules.append("US-AI-GAP")
            warnings.append("Governance gap: generative/agentic AI is outside the specific 2026 US model-risk guidance scope.")
    else:
        if case.booking_location == "United States" or case.us_touchpoint:
            active_rules.append("US-MRM-SR26-2")

    if case.sg_touchpoint and case.us_touchpoint:
        active_rules.append("DUAL-RULE-REVIEW")
        warnings.append("Cross-border case: apply additive controls; do not silently downgrade to the lighter rule set.")

    if case.model_drift_flag:
        return "RED_FRICTION", active_rules, warnings + ["Model drift review required."]

    if case.contradiction_count >= 2:
        return "RED_FRICTION", active_rules, warnings + ["Material contradictions require senior compliance review."]

    if case.evidence_coverage_ratio < 0.70:
        return "RED_FRICTION", active_rules, warnings + ["Evidence coverage below minimum threshold."]

    if case.unsupported_claim_rate > 0.20:
        return "RED_FRICTION", active_rules, warnings + ["Unsupported claim rate above threshold."]

    if "US-AI-GAP" in active_rules:
        return "AMBER_WITH_GOVERNANCE_GAP", active_rules, warnings

    if case.evidence_coverage_ratio < 0.85 or case.unsupported_claim_rate > 0.10 or case.contradiction_count == 1:
        return "AMBER", active_rules, warnings

    return "GREEN", active_rules, warnings
```
