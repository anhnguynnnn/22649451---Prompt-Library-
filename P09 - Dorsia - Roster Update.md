# P09 · Roster Update Notification Email

**Section:** 02 — HR / Employee Operations  
**Workflow step:** Step 3 of 4  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

```text
You are an HR operations assistant at Dorsia, a fashion wholesale and curation platform.

Your task is to write an email notifying an employee about a roster being posted or updated.

Use ONLY the structured data provided below.

Instructions:
- Do NOT infer or add any information that is not provided
- Keep the tone professional, clear, and informative
- Keep the email concise (maximum 100 words)

Email must include:
- Notification that the roster has been posted or updated
- Relevant roster details (if provided)
- Instruction to review the roster
- A point of contact: hr@dorsia.com
- A professional closing

Structure guideline:
- Greeting
- Announcement of roster update
- Key details (if available)
- Instruction to check roster
- Contact support
- Professional closing: Dorsia 

Example style (do not copy exactly):
Dear [Employee Name],  
Your roster has been updated. Please review your schedule...

Best regards,  
Dorsia  

Output format:

Subject: Roster Update Notification — Dorsia

Email:
[Write full email here]

Structured data:
[ROSTER_DATA]
```

---

## 📥 Placeholders to fill

| Placeholder | Source | Example |
|------------|--------|---------|
| `[ROSTER_DATA]` | Scheduling / HR system | `{ "employee_name": "Anna Nguyen", "roster_type": "Updated", "shift_details": "Monday 9AM–5PM" }` |

---

## 🏢 Intended Workflow or Task

This prompt is triggered whenever employee rosters are posted or updated.

- **Trigger:** New roster published or existing roster updated  
- **Actor:** HR / operations system  
- **Timing:** Immediately after roster update  
- **Next step:** Employee reviews updated schedule  

```text
Roster created/updated → [P09 RUNS]
→ Notification email generated
→ Employee receives notification
→ Employee reviews schedule
```

---

## ❗ Problem Being Solved

Employees are often unaware of roster updates if communication is inconsistent or delayed. HR teams may manually notify employees, which is time-consuming and unreliable.

This leads to missed shifts, confusion, and operational inefficiencies.

This prompt automates roster notifications, ensuring timely and consistent communication across all employees.

### Pain points addressed:
- Manual notification of roster updates  
- Delayed communication  
- Risk of employees missing schedule changes  

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | Very high — occurs regularly |
| Data availability | High — from scheduling systems |
| Human judgment needed | Low — standardised message |
| Integration possibility | High — can integrate with HR systems |
| Estimated time saving | ~80% (2–3 min → <30 sec per notification) |

**Human-in-the-loop role:**  
Minimal — system-generated notification with optional HR oversight.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Missing or unclear roster details | Medium | Include only provided data |
| Employees overlook email | Medium | Consider multi-channel alerts (e.g. SMS, app) |
| Incorrect roster data | Medium | Ensure system accuracy before sending |
| Over-reliance on email communication | Low–Medium | Encourage system login checks |

**Overall risk rating:** MEDIUM — low complexity but dependent on data accuracy and user attention.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Notify employees about roster updates  

**Output:**  
Basic notification emails with inconsistent structure  

**Observed effect:**  
Some emails lacked clarity or key instructions  

**Lesson learned:**  
Clear structure and instruction improve communication effectiveness  

---

### v1.1 — Structured notification format + clarity improvements ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Added structured format, defined required elements, and improved clarity of instructions  

**Output:**  
Consistent and clear notification emails  

**Observed effect:**  
Improved employee awareness and reduced confusion  

**Lesson learned:**  
Structured communication enhances clarity and reduces operational errors  

---
