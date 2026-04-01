# 📂 02 — Employee Onboarding & Operations Workflow

**Business function:** HR / Employee Operations  
**Trigger:** New employee successfully accepts job offer and becomes active in HR system  
**Prompts in this section:** P07, P08, P09, P10  

---

## Section Purpose

This workflow automates key communication touchpoints in the employee onboarding and ongoing operations process at Dorsia. It ensures that new hires receive consistent, timely, and professional communication from their first interaction through to ongoing employment updates.

By automating onboarding emails, account setup communication, roster notifications, and payroll distribution, this workflow reduces manual HR workload while improving employee experience, clarity, and operational efficiency.

---

## Chain Diagram

```text
Candidate accepts job offer
→ P07 (Welcome onboarding email)
→ P08 (Account setup email with login details)
→ Employee logs in & completes setup
→ P09 (Roster update notifications — recurring)
→ P10 (Weekly payslip email — every Wednesday)
```

---

## Workflow Overview

### Step 1 — Welcome Onboarding Email (P07)
Send a warm and professional welcome email to new employees after they accept their offer, setting expectations for onboarding and reinforcing a positive first impression.

### Step 2 — Account Setup Email (P08)
Provide employees with their work email and temporary password, along with clear instructions to log in and reset their password within 48 hours. This ensures secure and timely system access.

### Step 3 — Roster Notification (P09)
Automatically notify employees whenever their roster is created or updated, ensuring they are aware of their work schedule and reducing the risk of missed shifts.

### Step 4 — Weekly Payslip Email (P10)
Send employees their payslip every Wednesday with clear communication and attachment instructions, ensuring transparency and consistency in payroll operations.

---

## Notes

- All prompts are designed with **clear structure and constraints** to ensure consistency  
- Sensitive communications (e.g. account credentials, payslips) require secure handling practices  
- Workflow supports both onboarding and ongoing employee operations  
- Can be extended with reminders, analytics, or employee engagement tracking  
