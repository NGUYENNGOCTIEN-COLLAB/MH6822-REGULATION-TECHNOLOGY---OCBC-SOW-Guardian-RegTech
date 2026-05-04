# Scoring Thresholds

## Core formulas

```text
Evidence Coverage Ratio = supported material claims / total material claims

Unsupported Claim Rate = unsupported AI-generated material claims / total AI-generated material claims

Contradiction Count = number of material conflicts between the AI narrative and source documents

Human Challenge Rate = cases where a human reviewer amended, rejected, or escalated an AI output / total AI-assisted cases

Override Quality Score = percentage of overrides with case-specific reasons rather than generic approval text
```

## Output thresholds

| Condition | Tool output |
|---|---|
| Evidence coverage >= 85%, unsupported claim rate <= 10%, contradiction count = 0, no governance gap | Green |
| Evidence coverage 70-84%, unsupported claim rate 11-20%, contradiction count <= 1 | Amber |
| Evidence coverage < 70%, unsupported claim rate > 20%, or contradiction count >= 2 | Red friction |
| Any US case using generative AI or agentic AI | Add governance gap warning |
| Cross-border case with Singapore and US touchpoints | Activate dual-rule review |
| Human challenge rate below 20% for the reviewer or team | Human-overreliance warning |
| Model drift flag = true | Freeze straight-through approval and require model-risk review |

## Design principle

A case cannot receive a Green output if the AI-generated source-of-wealth narrative contains unresolved material contradictions, even if all mandatory form fields are complete.
