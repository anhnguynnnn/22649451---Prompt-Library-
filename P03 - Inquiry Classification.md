# P03 · Wholesale Inquiry Classification & Prioritisation

**Section:** 01 — Customer Onboarding  
**Workflow step:** Step 3 of 5  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

```
You are an operations analyst at Dorsia, a fashion wholesale and curation platform.

Your task is to classify and prioritise a wholesale inquiry based on structured data.

Use ONLY the information provided below.

Classify the inquiry into the following categories:

1. inquiry_category:
- "Wholesale partnership"
- "Stock request"
- "Collaboration"
- "General inquiry"
- "Other"

2. priority_level:
- "High"
- "Medium"
- "Low"

3. business_value:
- "New potential partner"
- "Existing partner support"
- "Low-value inquiry"

4. recommended_action:
- "Assign to sales team"
- "Assign to account manager"
- "Respond within 24 hours"
- "Respond within 48 hours"
- "No urgent action required"

Rules:
- Do NOT infer or generate information not present in the data
- If inquiry_type is provided, use it directly to determine category
- If relationship_status is "New inquiry", prioritise as potential partner
- If relationship_status is "Current partner", prioritise as support case
- If insufficient information is available, classify as:
  - inquiry_category: "Other"
  - priority_level: "Low"
  - business_value: "Low-value inquiry"
- Return ONLY JSON output with no explanation

Output format (STRICT JSON):

{
  "inquiry_category": "",
  "priority_level": "",
  "business_value": "",
  "recommended_action": ""
}

Structured data:
[EXTRACTED_DATA]
```

---

## 📥 Placeholders to fill

| Placeholder | Source | Example |
|------------|--------|---------|
| `[EXTRACTED_DATA]` | Output from P01 | `{ "business_type": "Brand", "relationship_status": "New inquiry", ... }` |

---

## 🏢 Intended Workflow or Task

This prompt is the **third step** in the wholesale inquiry workflow.

- **Trigger:** Structured data is available from P01  
- **Actor:** Dorsia operations/admin team  
- **Timing:** After confirmation email is generated (P02)  
- **Next step:** Output used for internal routing and prioritisation  

```
Customer submits inquiry → P01 (extract data)
→ P02 (confirmation email)
→ [P03 RUNS] → Inquiry classified & prioritised
→ Routed to appropriate team
```

---

## ❗ Problem Being Solved

Wholesale inquiries vary significantly in importance and urgency. Currently, staff must manually review each inquiry to determine priority and assign it to the appropriate team, which takes time and introduces inconsistency.

Without a structured system, high-value opportunities (e.g. new brand partnerships) may be delayed, while low-priority inquiries may consume unnecessary attention.

This prompt introduces a consistent classification system, enabling faster decision-making and more efficient allocation of internal resources.

### Pain points addressed:
- Manual decision-making for inquiry prioritisation  
- Inconsistent handling of inquiries across staff  
- Risk of delaying high-value partnership opportunities  

---

## ⚡ Automation Potential

**Level:** High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | High — every inquiry requires classification |
| Data availability | High — structured data from P01 |
| Human judgment needed | Medium — strategic decisions may require oversight |
| Integration possibility | High — can feed into CRM or task management systems |
| Estimated time saving | ~60–70% (2–3 min → <1 min per inquiry) |

**Human-in-the-loop role:**  
Staff review classifications for high-priority or high-value inquiries before actioning decisions.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Incorrect prioritisation due to limited context | Medium | Human review for high-value cases |
| Over-simplification of inquiry complexity | Medium | Allow fallback to "Other" category |
| Misclassification of business value | Medium | Use relationship_status as guiding rule |
| Over-reliance on AI decisions | Low–Medium | Require oversight for strategic decisions |

**Overall risk rating:** MEDIUM — supports decision-making but should not fully replace human judgment.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Classify inquiry priority and type based on input data  

**Output:**  
Basic classification but inconsistent logic and unclear categories  

**Observed effect:**  
Required manual interpretation and adjustment  

**Lesson learned:**  
Clear classification rules and defined categories are necessary for consistent outputs  

---

### v1.1 — Defined categories + structured decision rules ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Introduced fixed classification categories, added prioritisation logic based on relationship status, and enforced structured JSON output  

**Output:**  
Consistent, actionable classifications that can be directly used for workflow routing  

**Observed effect:**  
Reduced decision-making time and improved consistency across inquiries  

**Lesson learned:**  
Explicit decision rules significantly improve reliability and usefulness of AI-driven classification  

---
