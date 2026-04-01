# P04 · Internal Inquiry Summary

**Section:** 01 — Customer Onboarding  
**Workflow step:** Step 4 of 5  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

```text
You are an operations assistant at Dorsia, a fashion wholesale and curation platform.

Your task is to generate a concise internal summary of a wholesale inquiry for the team.

Use ONLY the structured data and classification provided below.

Instructions:
- Do NOT infer or add any information that is not provided
- Keep the summary clear, structured, and easy to scan
- Use bullet points where appropriate
- Keep the total length under 120 words

The summary must include:
- Business name and type
- Relationship status
- Inquiry category
- Priority level
- Key contact details (if available)
- Short description of inquiry
- Recommended action

If any field is "Not provided", omit it or clearly indicate "Not provided"

Output format:

Internal Inquiry Summary:

Business: [business_name] ([business_type])  
Status: [relationship_status]  
Category: [inquiry_category]  
Priority: [priority_level]  

Key Details:
- Representative: [representative_name]
- Email: [email]
- Phone: [phone_number]

Inquiry:
- Type: [inquiry_type]
- Notes: [other_inquiry_text]

Recommended Action:
[recommended_action]

Structured data:
[EXTRACTED_DATA]

Classification data:
[CLASSIFICATION_DATA]
```

---

## 📥 Placeholders to fill

| Placeholder | Source | Example |
|------------|--------|---------|
| `[EXTRACTED_DATA]` | Output from P01 | `{ "business_name": "Silk Archive", ... }` |
| `[CLASSIFICATION_DATA]` | Output from P03 | `{ "priority_level": "High", ... }` |

---

## 🏢 Intended Workflow or Task

This prompt is the **fourth step** in the wholesale inquiry workflow.

- **Trigger:** Classification data is generated from P03  
- **Actor:** Dorsia operations/admin or sales team  
- **Timing:** After inquiry has been classified and prioritised  
- **Next step:** Summary is used by internal team to take action  

```text
Customer submits inquiry → P01 (extract data)
→ P02 (confirmation email)
→ P03 (classify & prioritise)
→ [P04 RUNS] → Internal summary generated
→ Team reviews and takes action
```

---

## ❗ Problem Being Solved

After classification, team members still need to manually interpret raw data and outputs to understand each inquiry. This creates inefficiency, especially when handling multiple inquiries per day.

Without a clear summary, staff spend additional time reviewing details, which can delay response time and reduce productivity.

This prompt consolidates all relevant information into a single, easy-to-read summary, enabling faster decision-making and smoother internal communication.

### Pain points addressed:
- Time spent interpreting raw data and classifications  
- Lack of standardised internal communication  
- Delays in actioning inquiries  

---

## ⚡ Automation Potential

**Level:** High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | High — required for every inquiry |
| Data availability | High — inputs from P01 and P03 |
| Human judgment needed | Low — summarisation task |
| Integration possibility | High — can feed into dashboards or CRM |
| Estimated time saving | ~60–70% (2–3 min → <1 min per inquiry) |

**Human-in-the-loop role:**  
Team members review the summary before taking action, especially for high-priority inquiries.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Missing or incomplete data leads to weak summaries | Medium | Clearly label "Not provided" |
| Over-simplification of inquiry context | Medium | Include key fields explicitly |
| Misinterpretation of structured inputs | Low–Medium | Use strict "no inference" rule |
| Over-reliance on summary without checking raw data | Low–Medium | Encourage verification for important cases |

**Overall risk rating:** MEDIUM — summarisation is low-risk but dependent on input completeness.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Summarise inquiry into a short paragraph  

**Output:**  
Readable but inconsistent structure and sometimes missing key details  

**Observed effect:**  
Staff needed to reformat summaries and cross-check missing information  

**Lesson learned:**  
Structured formatting is necessary for clarity and usability  

---

### v1.1 — Structured summary format + field coverage ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Introduced structured layout with fixed sections and ensured all key fields are included  

**Output:**  
Clear, consistent summaries that are easy to scan and act on  

**Observed effect:**  
Reduced time needed to understand each inquiry and improved internal workflow efficiency  

**Lesson learned:**  
Structured summarisation significantly improves clarity and decision-making speed in business workflows  

---
