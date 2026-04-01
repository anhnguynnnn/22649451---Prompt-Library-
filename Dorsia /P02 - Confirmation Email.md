# P02 · Wholesale Inquiry Confirmation Email

**Section:** 01 — Customer Onboarding  
**Workflow step:** Step 2 of 5  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

You are an operations assistant at Dorsia, a fashion wholesale and curation platform.

Your task is to write a confirmation email to acknowledge receipt of a wholesale inquiry.

Use ONLY the structured data provided below.

Instructions:

Do NOT infer or add any information that is not provided

If the representative_name is "Not provided", use a neutral greeting (e.g. "Hello")

Keep the tone professional, welcoming, and formal

Keep the email concise (maximum 150 words)

Email must include:

Acknowledgement that the inquiry has been received

Appreciation for their interest in Dorsia

A statement that the team will review and respond shortly

A clear point of contact: dorsia.contact@gmail.com

Structure guideline:

Greeting

Thank the sender for their inquiry

Confirm receipt of inquiry

Inform that the team will respond shortly

Provide contact email

Professional closing

Example style (do not copy exactly):

Dear [Business name],

Thank you for reaching out to Dorsia...

Best regards,

Dorsia

Output format:

Subject: Wholesale Inquiry Received — Dorsia

Email:

[Write full email here]

Structured data:

[EXTRACTED_DATA]


---

## 📥 Placeholders to fill

| Placeholder | Source | Example |
|------------|--------|---------|
| `[EXTRACTED_DATA]` | Output from P01 (data extraction prompt) | `{ "business_type": "Boutique", "representative_name": "Anna", ... }` |
| `[DORSIA_EMAIL]` | Dorsia contact email | dorsia.contact@gmail.com |

---

## 🏢 Intended Workflow or Task

This prompt is the **second step** in the wholesale inquiry workflow.

- **Trigger:** Structured data is generated from P01  
- **Actor:** Dorsia operations/admin team  
- **Timing:** Immediately after inquiry is received and processed  
- **Next step:** Email is reviewed (optional) and sent to customer  
Customer submits inquiry → P01 (data extraction)
→ [P02 RUNS] → Confirmation email generated
→ Staff review (optional) → Email sent to customer

---

## ❗ Problem Being Solved

Responding to wholesale inquiries manually creates inconsistency in communication and delays in response time. Staff often spend **3–5 minutes per email**, and tone varies depending on who writes it, leading to inconsistent brand representation.

Delayed responses can negatively impact first impressions, especially when dealing with potential brand or boutique partners.

This prompt standardises communication and reduces response time to **under 1 minute**, improving both efficiency and professionalism.

### Pain points addressed:
- Inconsistent tone across emails  
- Delayed response to potential partners  
- Manual effort in drafting repetitive emails  

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | Very high — same structure for every inquiry |
| Data availability | High — structured data from P01 |
| Human judgment needed | Low — standardised response |
| Integration possibility | High — can connect to email systems or CRM |
| Estimated time saving | ~80% (3–5 min → <1 min per email) |

**Human-in-the-loop role:**  
Staff may quickly review the email before sending, especially for high-value partners, but review is optional for standard inquiries.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Missing representative name leads to generic greeting | Low | Fallback rule ("Hello") included |
| Overly generic tone reduces personalization | Medium | Maintain warm and brand-aligned tone |
| Incorrect structured data from P01 affects output | Medium | Ensure P01 validation before use |
| Over-reliance on automation without review | Low–Medium | Optional human review step before sending |

**Overall risk rating:** LOW–MEDIUM — low-risk communication task, but dependent on input accuracy.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Write a confirmation email for inquiry submissions  

**Output:**  
Emails were generally correct but inconsistent in tone and structure. Some responses were too long or lacked key elements such as clear acknowledgment or contact details.  

**Observed effect:**  
Required manual editing to standardise tone and ensure completeness.  

**Lesson learned:**  
Without clear constraints and structure, outputs vary significantly in quality and consistency.  

---

### v1.1 — Structured constraints + workflow integration ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Added structured input (from P01), strict constraints (tone, length), required content points, and fallback greeting logic.  

**Output:**  
Emails are now consistent, concise, and aligned with brand tone. All required elements are included in every output.  

**Observed effect:**  
Reduced manual editing to near zero. Emails can be used immediately with minimal or no adjustment.  

**Lesson learned:**  
Providing structured inputs and explicit constraints significantly improves output reliability and usability in automated workflows.  

---
