# Task3_One_Page_Summary - Soteria SOW Guardian

**Option selected:** Option B - Architecture Design  
**Entity:** OCBC Bank Ltd  
**Jurisdictions:** Singapore and United States  
**Domain:** AI model risk management and AI governance for AML/KYC source-of-wealth due diligence  
**Tool name:** Soteria SOW Guardian - Jurisdiction-Aware AI Governance Monitor for KYC Source-of-Wealth Review

Soteria SOW Guardian is a governance layer for banks using AI in KYC source-of-wealth review. It is designed around OCBC Bank Ltd and its private banking arm, Bank of Singapore. This is a realistic use case because Bank of Singapore has publicly announced a Source of Wealth Assistant, described as an agentic AI tool that can reduce source-of-wealth report preparation from around 10 days to one hour while relationship managers still review and refine the AI-generated drafts before internal AML/CFT review [R2]. OCBC also has US agencies in New York and Los Angeles, making a Singapore-US jurisdiction comparison operationally relevant [R1].

The tool does not replace the bank's AI drafting assistant. Instead, it sits around the AI-assisted workflow and asks five questions: What jurisdiction is active? What type of AI is being used? Are the AI-generated wealth claims supported by evidence? Did a human reviewer meaningfully challenge the output? What audit record shows that the bank governed the workflow properly?

The core design issue is that AI can make weak evidence look strong. A polished source-of-wealth narrative may still be unsupported by documents. The tool therefore calculates an Evidence Coverage Ratio, Unsupported Claim Rate, Contradiction Count, Human Challenge Rate, Override Quality Score, and Model Drift Flag. If evidence coverage is below threshold, unsupported claims are above threshold, or material contradictions remain unresolved, the case enters a Red Friction state and cannot proceed to straight-through approval.

The jurisdiction logic is real rather than decorative. In Singapore mode, the tool activates MAS AI Model Risk Management, FEAT/Veritas-style responsible AI checks, and MAS Notice 626 AML/KYC controls [R3-R6]. In US mode, the tool activates FinCEN CDD controls and distinguishes between traditional/non-generative models and generative or agentic AI [R7-R9]. For US cases involving generative or agentic AI, the tool does not falsely mark the system as fully covered by the 2026 model-risk guidance. Instead, it issues a governance gap warning and requires internal AI governance, AML compliance owner approval, and human final approval.

The same synthetic case produces different outputs. A Singapore case using agentic AI triggers MAS AI governance and AML/KYC source-of-wealth controls. A US case using the same agentic AI triggers FinCEN CDD controls plus a governance gap warning because the specific 2026 US model-risk guidance does not cover generative or agentic AI. A cross-border case activates dual-rule review and applies a no-silent-downgrade rule: where one jurisdiction creates a governance gap and the other requires active controls, the tool does not treat the gap as permission to reduce controls.

The tool's main outputs are Green, Amber, Red Friction, Amber + Governance Gap, and Red Friction + Governance Gap. It also produces a case audit pack showing active rule versions, evidence maps, unresolved contradictions, reviewer actions, model drift alerts, and privacy exceptions. This solves a problem that a memo or spreadsheet cannot: continuous claim-to-evidence checking, rule versioning, drift monitoring, human challenge monitoring, and jurisdiction-specific control selection.

The tool does not approve customers automatically, file STRs/SARs automatically, certify that a case is "MAS compliant" or "US compliant," replace relationship managers or compliance officers, or prove that wealth is legitimate. Its narrower purpose is to show whether the bank's source-of-wealth conclusion is supported by available evidence, whether humans exercised judgment, and whether the correct jurisdictional governance logic was applied.

