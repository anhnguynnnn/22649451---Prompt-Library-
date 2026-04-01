# P06 · Follow-up Email (Action Layer)

**Section:** 01 — Customer Onboarding  
**Workflow step:** Step 6 of 6  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

```text
You are an operations assistant at Dorsia, a fashion wholesale and curation platform.

Your task is to write a tailored follow-up email responding to a wholesale inquiry.

Use ONLY the structured data and classification provided below.

The email should be adapted based on the type of inquiry and business value.

Instructions:
- Do NOT infer or add any information that is not provided
- Keep tone professional, welcoming, and brand-aligned
- Keep the email concise (maximum 150 words)
- Personalise using available data (business_name or representative_name)
- If name is "Not provided", use a neutral greeting (e.g. "Hello")

Response logic:

1. If business_value = "New potential partner":
- Welcome them
- Introduce Dorsia briefly
- Express interest in collaboration
- Mention next steps (e.g. onboarding, reviewing brand)

2. If business_value = "Existing partner support":
- Acknowledge their request
- Confirm support is being handled
- Provide reassurance and next steps

3. If inquiry_category = "Stock request":
- Acknowledge request
- Mention product availability or next communication
- Indicate follow-up from sales team

4. If inquiry_category = "General inquiry" or "Other":
- Provide a general acknowledgement
- Confirm team will respond with more details shortly

Email must include:
- Greeting
- Clear response based on inquiry type
- Next steps or expectation
- Contact email: dorsia.contact@gmail.com
- Professional closing

Output format:

Subject: Re: Your Inquiry with Dorsia

Email:
[Write full email here]

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
| `[CLASSIFICATION_DATA]` | Output from P03 | `{ "business_value": "New potential partner", ... }` |

---

## 🏢 Intended Workflow or Task

This prompt is the **final action step** in the wholesale inquiry workflow.

- **Trigger:** Inquiry has been classified and assigned (P03, P05)  
- **Actor:** Sales / Partnerships / Account team  
- **Timing:** After routing decision is made  
- **Next step:** Email is sent to customer as official response  

```text
Customer submits inquiry → P01 (extract data)
→ P02 (confirmation email)
→ P03 (classify & prioritise)
→ P04 (internal summary)
→ P05 (routing & assignment)
→ [P06 RUNS] → Follow-up email sent
```

---

## ❗ Problem Being Solved

While confirmation emails acknowledge receipt, they do not address the actual needs of the customer. Staff must manually draft follow-up responses based on inquiry type, which is time-consuming and inconsistent.

Different types of inquiries require different responses, and without a structured system, communication quality varies significantly.

This prompt automates tailored responses, ensuring faster turnaround and consistent communication aligned with business goals.

### Pain points addressed:
- Manual drafting of follow-up emails  
- Inconsistent communication quality  
- Delays in responding to customer needs  

---

## ⚡ Automation Potential

**Level:** High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | High — common response patterns |
| Data availability | High — structured + classified data |
| Human judgment needed | Medium — some cases require nuance |
| Integration possibility | High — can connect to email systems |
| Estimated time saving | ~70–80% (3–5 min → <1 min per email) |

**Human-in-the-loop role:**  
Staff review and adjust email for high-value partners or complex inquiries before sending.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Over-generalised responses | Medium | Use structured logic + personalization |
| Misinterpretation of inquiry type | Medium | Ensure P03 accuracy |
| Lack of nuance in complex cases | Medium | Allow manual edits |
| Over-reliance on automation | Low–Medium | Require review for high-priority cases |

**Overall risk rating:** MEDIUM — adds value but requires oversight for important cases.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Write a follow-up email based on inquiry  

**Output:**  
Generic responses with limited variation based on inquiry type  

**Observed effect:**  
Staff needed to heavily edit emails for relevance  

**Lesson learned:**  
Context-based logic is necessary to produce meaningful responses  

---

### v1.1 — Context-based response logic + structured output ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Added response rules based on business value and inquiry category, included personalization and structured guidance  

**Output:**  
More relevant, tailored responses aligned with business needs  

**Observed effect:**  
Reduced editing time and improved response quality  

**Lesson learned:**  
Incorporating business logic into prompts significantly enhances output usefulness  

---
