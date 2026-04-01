# P05 · Inquiry Routing & Assignment

**Section:** 01 — Customer Onboarding  
**Workflow step:** Step 5 of 5  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

```text
You are a Head of Operations at Dorsia, a fashion wholesale and curation platform.

Your task is to assign ownership and routing for a wholesale inquiry based on structured data and classification results.

Use ONLY the information provided below.

Determine the following:

1. assigned_team:
- "Sales"
- "Partnerships"
- "Account Management"
- "Operations"

2. owner_role:
- "Partnerships Lead"
- "Sales Manager"
- "Account Manager"
- "Operations Coordinator"

3. response_priority:
- "High"
- "Medium"
- "Low"

4. routing_reason:
- Short explanation of why this assignment was made (max 20 words)

Decision rules:
- If business_value = "New potential partner" → assign to "Partnerships"
- If business_value = "Existing partner support" → assign to "Account Management"
- If inquiry_category = "Stock request" → assign to "Sales"
- If inquiry_category = "General inquiry" or "Other" → assign to "Operations"

- If priority_level = "High" → response_priority = "High"
- If priority_level = "Medium" → response_priority = "Medium"
- If priority_level = "Low" → response_priority = "Low"

- Assign owner_role based on assigned_team:
  - Partnerships → Partnerships Lead
  - Sales → Sales Manager
  - Account Management → Account Manager
  - Operations → Operations Coordinator

Rules:
- Do NOT infer beyond provided data
- Follow decision rules strictly
- Keep routing_reason concise and factual
- Return ONLY JSON output with no explanation

Output format (STRICT JSON):

{
  "assigned_team": "",
  "owner_role": "",
  "response_priority": "",
  "routing_reason": ""
}

Structured data:
[EXTRACTED_DATA]

Classification data:
[CLASSIFICATION_DATA]
```

---

## 📥 Placeholders to fill

| Placeholder | Source | Example |
|------------|--------|---------|
| `[EXTRACTED_DATA]` | Output from P01 | `{ "business_type": "Brand", ... }` |
| `[CLASSIFICATION_DATA]` | Output from P03 | `{ "priority_level": "High", ... }` |

---

## 🏢 Intended Workflow or Task

This prompt is the **final step** in the wholesale inquiry workflow.

- **Trigger:** Classification and summary are completed (P03, P04)  
- **Actor:** Operations team / system automation  
- **Timing:** Immediately after classification  
- **Next step:** Inquiry is assigned to the appropriate team and owner  

```text
Customer submits inquiry → P01 (extract data)
→ P02 (confirmation email)
→ P03 (classify & prioritise)
→ P04 (internal summary)
→ [P05 RUNS] → Inquiry assigned to team & owner
→ Team takes action
```

---

## ❗ Problem Being Solved

After classification, inquiries still need to be manually assigned to the correct team and owner. This process is repetitive and prone to inconsistency, especially when handled by different staff members.

Without a clear routing system, high-value inquiries may be delayed or assigned incorrectly, leading to missed opportunities and inefficiencies.

This prompt automates assignment decisions, ensuring that every inquiry is routed consistently and quickly to the right team.

### Pain points addressed:
- Manual assignment of inquiries  
- Inconsistent routing decisions  
- Delays in handling high-priority inquiries  

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | Very high — required for every inquiry |
| Data availability | High — inputs from P01 and P03 |
| Human judgment needed | Low — rule-based assignment |
| Integration possibility | High — can integrate with CRM or task systems |
| Estimated time saving | ~70–80% (2 min → <30 sec per inquiry) |

**Human-in-the-loop role:**  
Managers may override assignment for exceptional or strategic cases.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Incorrect assignment due to rigid rules | Medium | Allow manual override |
| Misclassification from earlier steps affects routing | Medium | Validate P03 output |
| Oversimplification of complex inquiries | Medium | Flag edge cases for review |
| Over-reliance on automation | Low–Medium | Maintain human oversight |

**Overall risk rating:** MEDIUM — rule-based but dependent on upstream accuracy.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Assign inquiry to a team based on basic rules  

**Output:**  
Basic assignment but lacked consistency and clarity in ownership  

**Observed effect:**  
Staff still needed to interpret results manually  

**Lesson learned:**  
Clear mapping between classification and assignment is required  

---

### v1.1 — Structured routing rules + ownership mapping ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Introduced fixed assignment rules, mapped teams to owner roles, and enforced structured JSON output  

**Output:**  
Consistent and actionable routing decisions with clear ownership  

**Observed effect:**  
Reduced assignment time and improved workflow efficiency  

**Lesson learned:**  
Explicit decision rules and ownership mapping significantly improve operational clarity  

---
