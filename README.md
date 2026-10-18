# 🍷 My Tasty Club — QA & Usability Case Study

![App Preview](assets/app-preview.png)

## 📌 About the Project
[My Tasty Club](https://mytastyclub.app) is a Portuguese web platform dedicated to sharing culinary experiences, wine tastings, festivals, workshops, and exclusive member perks.

This case study presents a **Heuristic Usability Evaluation and Specialized QA Assessment** focused on exploring available events, applying multi-parameter search filters, and validating the event submission workflow.

---

## 🛠️ Test Environment
* **Platform / Website:** `mytastyclub.app`
* **Browser:** Brave
* **Operating System:** Windows 10 Home
* **Methodology:** Heuristic Evaluation (Nielsen’s Principles) + Black-Box Exploratory Testing
* **Target Persona:** Food and wine enthusiasts looking for curated events across Portugal

---

## 📊 Summary of Results

| Test Scenarios Executed | Passed | Usability / Logic Issues |
| :---: | :---: | :---: |
| **3** | **1** | **3** |

### Key Issues Identified
* **[USAB-01]** Redundant secondary filter box creating visual clutter and user friction (*Severity: Medium*).
* **[USAB-02]** Filter state conflict causing secondary recommendations to overwrite primary location filters (*Severity: High*).
* **[USAB-03]** Ambiguous event submission form wording and missing status turnaround SLA (*Severity: Low*).

👉 *For step-by-step reproduction, evidence, and heuristic mapping, view the full [Usability Report](docs/usability-report.md).*

---

## 💡 Top Recommendations
1. **Unify Search & Filter UI:** Consolidate redundant location and filter controls into a single intuitive hero header component, allowing users to filter directly by Portuguese districts.
2. **Synchronise Filter Queries:** Ensure secondary suggestion filters inherit active primary filters (e.g., preserving `Location = Lisboa`) to prevent returning conflicting result sets.
3. **Optimise Submission Copy & Feedback:** Rephrase "About You" fields to welcome community suggestions and display a expected review timeline upon submission.

---

## 📄 Documentation Structure
* 📂 [Test Cases](docs/testcases)
* 📂 [Usability & Bug Report](docs/usability-report.md)
* 📂 [Media & Evidence](assets/)

---

## 👤 Credits & Acknowledgements
* **Platform:** My Tasty Club
* **QA & Usability Analyst:** Juliara Vasconcelos
