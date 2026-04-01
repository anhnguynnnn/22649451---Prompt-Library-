# 📂 01 — Wholesale Inquiry Workflow

**Business function:** Operations / Customer Onboarding  
**Trigger:** Customer submits a wholesale inquiry form via Dorsia website  
**Prompts in this section:** P01, P02, P03, P04, P05, P06  

---

## Section Purpose

This workflow automates the end-to-end handling of wholesale inquiries for Dorsia, from initial data intake to final response and internal routing. It ensures consistent communication, faster response times, and structured decision-making across all inquiries.

By integrating data extraction, customer communication, classification, internal summarisation, routing, and follow-up actions, this workflow reduces manual workload while improving operational efficiency and partner experience.

---

## Chain Diagram

```text
Customer submits inquiry form
→ P01 (Extract data from form)
→ P02 (Send confirmation email to customer)
→ P03 (Classify & prioritise inquiry)
→ P04 (Generate internal summary for team)
→ P05 (Assign & route inquiry to appropriate team)
→ P06 (Send tailored follow-up email)
→ Inquiry handled by internal team
```

---

## Workflow Overview

### Step 1 — Data Extraction (P01)
Extract structured data from inquiry form submissions, including business type, contact details, and inquiry type. This standardises input for downstream processes.

### Step 2 — Confirmation Email (P02)
Automatically acknowledge receipt of the inquiry to the customer, ensuring timely and professional communication.

### Step 3 — Classification & Prioritisation (P03)
Categorise the inquiry and determine its priority level and business value, enabling informed decision-making.

### Step 4 — Internal Summary (P04)
Generate a concise internal summary of the inquiry to help the team quickly understand key details and context.

### Step 5 — Routing & Assignment (P05)
Assign the inquiry to the appropriate team and owner based on classification and business rules.

### Step 6 — Follow-up Email (P06)
Send a tailored response to the customer based on their inquiry type and business value, ensuring relevant and actionable communication.

---

## Notes

- All prompts are designed with **human-in-the-loop validation** where necessary  
- Outputs are structured to integrate with CRM and internal systems  
- Workflow can be extended with analytics or tracking modules for further optimisation  

---
