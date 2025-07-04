# Bank Transaction Risk Profiling & Fraud Flagging

## Overview

This project demonstrates an end-to-end pipeline for analyzing bank transaction data to detect unusual behavior, generate risk flags, and simulate operational decisioning for fraud prevention.  
It highlights how domain knowledge, practical EDA, and simple rule-based profiling can help financial institutions identify transactions that may need further review.

---

## Objectives

- Perform exploratory data analysis (EDA) to understand customer transaction behavior.
- Define practical risk scenarios based on real-world banking context.
- Apply rule-based logic to flag suspicious transactions.
- Combine multiple signals to generate a clear `Transaction_Status` (Approve, Agent Review, Hold).
- Provide an explainable approach to support fraud operations and compliance checks.

---

## Dataset

**Key features include:**

- **Transaction Details:** ID, type (Spend, Remit, Withdraw, etc.), amount, location, time, destination country.
- **Customer Profile:** Account age, holder age, occupation, credit score, annual income, address change flag.
- **Behavior Patterns:** Average transaction amount, frequent transaction hour, average time gap, frequent device type.
- **Counterparty Info:** Sender/Payee ID, type, country, average send amount, relationship type.
- **Derived Output:** `Transaction_Status` based on generated risk flags.

---

## Analysis Steps

###  Exploratory Data Analysis (EDA)

- Summary statistics for numerical fields.
- Distribution checks for outliers, skews, and realistic ranges.
- Category frequency checks for occupation, transaction type, device usage, etc.

###  Bivariate Checks & Rule Logic

- Compare income vs. transaction amount.
- Check device consistency and city match.
- Monitor transaction timing and frequency patterns.
- Cross-check sender relationships and destinations.

### Risk Flags & Status

- Flags for low income + high spend, low credit + high spend, new accounts with large sums, students sending large amounts, suspicious destination countries, unknown relationships, device/location mismatches, and more.
- Multi-flag logic to escalate suspicious transactions.
- Final `Transaction_Status`:
  - **Approve** — passes all checks.
  - **Agent Review** — unusual but explainable.
  - **Hold** — multiple red flags or high risk.

---

## Tech Stack

- **Language:** Python 3
- **Libraries:** pandas, numpy, seaborn, matplotlib
- **Environment:** Google Colab

---

## Key Takeaways

- Majority of flagged transactions involved missing or unverified counterparties and unusual device patterns.
- Multiple overlapping flags are rare but highlight higher fraud risk.
- Domain-driven rule checks provide an interpretable framework to support fraud detection without relying on opaque models.

---

## Outcomes

This project demonstrates a clear, defensible approach to transaction risk profiling and highlights how simple rule-based checks can strengthen banking fraud prevention workflows.

---

## Keywords

Data Analysis • Banking • Fraud Detection • Risk Profiling • Anomaly Detection • EDA • Python

