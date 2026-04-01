# P01 · Wholesale Inquiry Data Extraction

**Section:** 01 — Customer Onboarding  
**Workflow step:** Step 1 of 5  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

You are an operations assistant at Dorsia, a fashion wholesale and curation platform.

Your task is to extract and standardise key information from a submitted wholesale inquiry form.

Using ONLY the information provided below, extract the following fields:
- business_type
- relationship_status
- business_name
- representative_name
- email
- phone_number
- inquiry_type
- other_inquiry_text

Rules:
- Do NOT infer, assume, or generate information that is not explicitly stated in the form
- Copy selected options exactly where possible
- Standardise business_type as either "Brand" or "Boutique" only
- Standardise relationship_status as either:
  - "Current partner"
  - "New inquiry"
- If a field is missing, blank, or not shown in the form response, return "Not provided"
- If "Other" is selected for inquiry type, extract the written explanation into "other_inquiry_text"
- If "Other" is not selected or no text is provided, return "Not provided" for "other_inquiry_text"
- Copy email address and phone number exactly as written
- Return ONLY the JSON object with no extra text

Output format (STRICT JSON):

{
  "business_type": "",
  "relationship_status": "",
  "business_name": "",
  "representative_name": "",
  "email": "",
  "phone_number": "",
  "inquiry_type": "",
  "other_inquiry_text": ""
}

Wholesale inquiry form:
[INQUIRY_FORM]



---

## 🏢 Intended Workflow or Task

This is the **first step** in the wholesale inquiry handling workflow.

- **Trigger:** Customer submits wholesale inquiry form  
- **Actor:** Dorsia operations/admin team  
- **Timing:** Immediately upon receiving inquiry  
- **Next step:** Output feeds into confirmation email prompt (P02)  

Customer submits inquiry → [P01 RUNS]
→ Structured data generated → P02 runs
→ Data stored in CRM


---

## ❗ Problem Being Solved

Wholesale inquiry data is often submitted in **unstructured formats** (free text, inconsistent fields, missing labels). Staff must manually read and extract key details, which takes approximately **3–5 minutes per inquiry**.

This leads to:
- inconsistent data entry  
- risk of missing contact details  
- delays in responding to potential partners  

By automating extraction, Dorsia can standardise incoming data and reduce processing time to **under 30 seconds per inquiry**.

### Pain points addressed:
- Manual data extraction from messy inputs  
- Inconsistent formatting across staff  
- Risk of missing or misreading key contact information  

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | Very high — every inquiry requires the same fields |
| Data availability | High — information is provided in form submissions |
| Human judgment needed | Low — task is rule-based extraction |
| Integration possibility | High — output can feed directly into CRM or next prompt |
| Estimated time saving | ~80–90% (5 min → <30 sec per inquiry) |

**Human-in-the-loop role:**  
Staff quickly review extracted data for accuracy before using it for communication or storing in CRM.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Model incorrectly classifies business type | Medium | Restrict output to "Brand" or "Boutique" only |
| Missing or unclear input data | Medium | Use "Not provided" fallback |
| Extraction errors from messy text | Medium | Human verification before use |
| Over-reliance on AI output without checking | Low–Medium | Require quick manual review before sending email |

**Overall risk rating:** MEDIUM — low complexity task but input quality can affect accuracy.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Extract key details from inquiry form  

**Output:**  
Generally accurate but inconsistent formatting and occasional missing fields  

**Observed effect:**  
Required manual cleanup before use  

**Lesson learned:**  
Need stricter structure and enforced output format  

---

### v1.1 — Structured JSON output + fallback rules added ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Added strict JSON output format and fallback rules ("Not provided") for missing fields  

**Output:**  
More consistent and machine-readable  

**Observed effect:**  
Reduced manual editing time  

**Lesson learned:**  
Structured outputs significantly improve usability in workflows  

---
