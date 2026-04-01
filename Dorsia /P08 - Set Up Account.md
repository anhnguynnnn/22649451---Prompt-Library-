# P08 · Employee Account Setup Email

**Section:** 02 — HR / Employee Onboarding  
**Workflow step:** Step 2 of 3  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

```text
You are an HR operations assistant at Dorsia, a fashion wholesale and curation platform.

Your task is to write an account setup email for a new employee, providing their work email and temporary password.

Use ONLY the structured data provided below.

Instructions:
- Do NOT infer or add any information that is not provided
- If employee_name is "Not provided", use a neutral greeting (e.g. "Hello")
- Keep the tone professional, clear, and supportive
- Keep the email concise (maximum 150 words)

Email must include:
- A brief welcome
- The employee’s work email
- The temporary (default) password
- A clear instruction to log in and change password immediately
- A statement that the temporary password is valid for 48 hours only
- A support contact: hr@dorsia.com
- A professional closing

Structure guideline:
- Greeting
- Welcome message
- Account details (email + password)
- Instructions to log in and reset password
- Security note (48-hour validity)
- Support contact
- Professional closing: Dorsia 

Example style (do not copy exactly):
Dear [Employee Name],  
Your account has been created. Please find your login details below...

Best regards,  
Dorsia   

Output format:

Subject: Your Dorsia Account Details

Email:
[Write full email here]

Structured data:
[ACCOUNT_DATA]
```

---

## 📥 Placeholders to fill

| Placeholder | Source | Example |
|------------|--------|---------|
| `[ACCOUNT_DATA]` | IT / HR system | `{ "employee_name": "Anna Nguyen", "work_email": "anna@dorsia.com", "temporary_password": "Temp1234!" }` |

---

## 🏢 Intended Workflow or Task

This prompt is the **second step** in the employee onboarding workflow.

- **Trigger:** Employee onboarding initiated after welcome email (P07)  
- **Actor:** HR / IT operations team  
- **Timing:** Immediately after account creation  
- **Next step:** Employee logs in and sets a new password  

```text
Candidate accepts offer → P07 (welcome email)
→ Account created in system
→ [P08 RUNS] → Account details email generated
→ Employee logs in → Password updated
```

---

## ❗ Problem Being Solved

Providing account credentials manually is repetitive and prone to inconsistency. HR or IT teams typically spend **2–3 minutes per employee** composing emails with login details.

Without a structured process, important security instructions (e.g. password expiry) may be omitted, increasing security risks.

This prompt standardises communication and ensures all required information is included, reducing time to **under 1 minute**.

### Pain points addressed:
- Manual drafting of account setup emails  
- Risk of missing critical security instructions  
- Inconsistent onboarding communication  

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | Very high — required for every new employee |
| Data availability | High — available in HR/IT systems |
| Human judgment needed | Low — standardised message |
| Integration possibility | High — can integrate with HR or identity systems |
| Estimated time saving | ~70–80% (2–3 min → <1 min per email) |

**Human-in-the-loop role:**  
HR/IT may review credentials for accuracy before sending.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Exposure of sensitive credentials | High | Ensure secure transmission channel and limited access |
| Incorrect account data | Medium | Validate data before sending |
| Employee delays password change | Medium | Clearly state 48-hour expiry rule |
| Over-reliance on automation | Low–Medium | Require optional review step |

**Overall risk rating:** HIGH — involves sensitive information and requires strict security handling.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Send account details to new employee  

**Output:**  
Included credentials but lacked structured format and security emphasis  

**Observed effect:**  
Some emails missed important instructions (e.g. password expiry)  

**Lesson learned:**  
Security-related communication must be explicit and structured  

---

### v1.1 — Structured account email + security instruction ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Added structured format, included password expiry rule (48 hours), and enforced required content  

**Output:**  
Clear, consistent, and secure onboarding email  

**Observed effect:**  
Improved clarity and reduced risk of missing critical information  

**Lesson learned:**  
Explicit security instructions significantly improve compliance and reduce risk  

---
