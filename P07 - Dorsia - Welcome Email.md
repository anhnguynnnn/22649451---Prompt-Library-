# P07 · New Employee Onboarding Welcome Email

**Section:** 02 — HR / Employee Onboarding  
**Workflow step:** Step 1 of 3  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

```text
You are an HR operations assistant at Dorsia, a fashion wholesale and curation platform.

Your task is to write a welcome onboarding email for a new employee who has successfully accepted a job offer.

Use ONLY the structured data provided below.

Instructions:
- Do NOT infer or add any information that is not provided
- If employee_name is "Not provided", use a neutral greeting (e.g. "Hello")
- Keep the tone professional, welcoming, and supportive
- Keep the email concise (maximum 150 words)

Email must include:
- A warm welcome to the company
- Mention of the employee’s role
- A short statement expressing excitement about them joining
- Information that further onboarding details will be shared soon
- A point of contact: hr@dorsia.com
- A professional closing

Structure guideline:
- Greeting
- Welcome message
- Role acknowledgment
- Next steps (onboarding info coming soon)
- Contact information
- Professional closing: Dorsia 

Example style (do not copy exactly):
Dear [Employee Name],  
Welcome to Dorsia. We are excited to have you join us as [Role]...

Best regards,  
Dorsia Team  

Output format:

Subject: Welcome to Dorsia — Your Onboarding Begins

Email:
[Write full email here]

Structured data:
[EMPLOYEE_DATA]
```

---

## 📥 Placeholders to fill

| Placeholder | Source | Example |
|------------|--------|---------|
| `[EMPLOYEE_DATA]` | HR system (new hire record) | `{ "employee_name": "Anna Nguyen", "email": "anna@gmail.com", "role": "Marketing Assistant" }` |

---

## 🏢 Intended Workflow or Task

This prompt is the **first step** in the employee onboarding communication workflow.

- **Trigger:** Candidate successfully accepts job offer  
- **Actor:** HR / operations team  
- **Timing:** Immediately after offer acceptance  
- **Next step:** Email is sent to employee → onboarding process begins  

```text
Candidate accepts offer → HR system updates
→ [P07 RUNS] → Welcome email generated
→ HR reviews (optional) → Email sent to employee
→ Onboarding process continues
```

---

## ❗ Problem Being Solved

HR teams often manually draft onboarding emails, which leads to inconsistencies in tone and messaging. This process takes approximately **3–5 minutes per employee** and may result in missing important information.

Delays or poorly written onboarding emails can negatively affect the employee’s first impression of the company.

This prompt standardises onboarding communication and reduces drafting time to **under 1 minute**, ensuring a consistent and professional experience.

### Pain points addressed:
- Inconsistent onboarding communication  
- Manual drafting effort  
- Risk of missing key onboarding information  

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | Very high — required for every new hire |
| Data availability | High — available in HR system |
| Human judgment needed | Low — standardised message |
| Integration possibility | High — can integrate with HR systems or email tools |
| Estimated time saving | ~80% (3–5 min → <1 min per email) |

**Human-in-the-loop role:**  
HR may review email for senior roles or customised onboarding cases.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Missing employee name leads to generic greeting | Low | Fallback greeting ("Hello") |
| Overly generic tone | Medium | Maintain structured but warm tone |
| Incorrect input data from HR system | Medium | Verify employee data before sending |
| Over-reliance on automation | Low–Medium | Optional HR review before sending |

**Overall risk rating:** LOW–MEDIUM — low-risk communication but dependent on data accuracy.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Write a welcome email for new employees  

**Output:**  
Emails were correct but inconsistent in tone and structure  

**Observed effect:**  
Required manual adjustments for professionalism and clarity  

**Lesson learned:**  
Clear structure and constraints are necessary for consistent onboarding communication  

---

### v1.1 — Structured onboarding email + tone control ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Added structured input, tone constraints, required content elements, and fallback greeting logic  

**Output:**  
Consistent, professional, and welcoming onboarding emails  

**Observed effect:**  
Reduced drafting time and improved onboarding experience  

**Lesson learned:**  
Structured prompts with clear guidelines significantly improve communication quality  

---
