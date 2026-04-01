# P10 · Weekly Payslip Email

**Section:** 02 — HR / Employee Operations  
**Workflow step:** Step 4 of 4  
**Current version:** v1.1  
**Status:** 🔄 In progress  
**Last updated:** 1 April 2026  

---

## 📌 Prompt Text (v1.1 — current)

```text
You are an HR operations assistant at Dorsia, a fashion wholesale and curation platform.

Your task is to write a weekly payslip email to an employee.

Use ONLY the structured data provided below.

Instructions:
- Do NOT infer or add any information that is not provided
- If employee_name is "Not provided", use a neutral greeting (e.g. "Hello")
- Keep the tone professional, clear, and friendly
- Keep the email concise (maximum 100 words)

Email must include:
- Notification that the weekly payslip is attached
- The pay period (if provided)
- A reminder to review the payslip
- A support contact: hr@dorsia.com
- A professional closing

Structure guideline:
- Greeting
- Payslip notification
- Pay period (if available)
- Instruction to review attachment
- Contact support
- Professional closing

Example style (do not copy exactly):
Dear [Employee Name],  
Please find your weekly payslip attached...

Best regards,  
Dorsia   

Output format:

Subject: Weekly Payslip — Dorsia

Email:
[Write full email here]

Structured data:
[PAYROLL_DATA]
```

---

## 📥 Placeholders to fill

| Placeholder | Source | Example |
|------------|--------|---------|
| `[PAYROLL_DATA]` | Payroll system | `{ "employee_name": "Anna Nguyen", "pay_period": "25 Mar – 31 Mar 2026" }` |

---

## 🏢 Intended Workflow or Task

This prompt is triggered automatically every Wednesday when payslips are generated.

- **Trigger:** Weekly payroll processing completed  
- **Actor:** HR / payroll system  
- **Timing:** Every Wednesday after payslip generation  
- **Next step:** Email is sent with payslip attachment  

```text
Payroll processed → Payslips generated
→ [P10 RUNS] → Email drafted
→ Payslip attached → Email sent to employee
```

---

## ❗ Problem Being Solved

Payroll teams often manually notify employees about payslips, which can be repetitive and time-consuming. Inconsistent communication may lead to confusion about pay periods or missed payslip reviews.

This prompt automates payslip communication, ensuring timely and consistent delivery every week.

### Pain points addressed:
- Manual payslip notifications  
- Inconsistent communication  
- Risk of employees overlooking payslips  

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|-----------|------------|
| Repetitiveness | Very high — weekly recurring task |
| Data availability | High — from payroll system |
| Human judgment needed | Low — standardised communication |
| Integration possibility | High — integrates with payroll/email systems |
| Estimated time saving | ~80–90% (2–3 min → <30 sec per email) |

**Human-in-the-loop role:**  
Minimal — payroll team verifies payslip accuracy before sending.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|-------|------------|
| Sending incorrect payslip attachment | High | Validate payroll system before sending |
| Missing pay period information | Medium | Include fallback if not provided |
| Employees overlooking email | Medium | Encourage regular checking of payslips |
| Data privacy concerns | High | Ensure secure email handling |

**Overall risk rating:** HIGH — involves sensitive payroll information.

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 1 April 2026  

**Prompt:**  
Send payslip notification email  

**Output:**  
Basic email but lacked structure and clarity  

**Observed effect:**  
Some emails unclear about pay period or instructions  

**Lesson learned:**  
Clear structure improves communication and reduces confusion  

---

### v1.1 — Structured payslip email + clarity improvements ✅ Current  
**Date:** 1 April 2026  

**Change:**  
Added structured format, defined required elements, and improved clarity of messaging  

**Output:**  
Consistent and clear payslip emails  

**Observed effect:**  
Improved employee understanding and reduced payroll-related inquiries  

**Lesson learned:**  
Structured communication ensures consistency and reduces operational errors  

---
