# 🐞 Usability & Bug Report

---

### [USAB-01] Redundant secondary filter component causing layout friction
* **Feature / Screen:** Event Discovery / Search Page
* **Severity Level:** Medium
* **Description:** Selecting a location filter (e.g., "Viseu") successfully displays matching events. However, a secondary filter box immediately below duplicates options from the main search bar, causing unnecessary cognitive load and user confusion.
* **Steps to Reproduce:**
  1. Navigate to `mytastyclub.app`.
  2. Select the location filter (e.g., "Viseu").
  3. Observe the search result page and the secondary filter box rendered beneath.
* **Expected vs. Actual Result:**
  * *Expected:* A single, consolidated filtering interface with direct district selection.
  * *Actual:* Duplicated filter options appearing across two distinct UI components on the same page.
* **Suggested Fix:** Integrate secondary filter controls directly into the primary top search bar to streamline the discovery experience.
* **Evidence:** ![duplicated filter](media/duplicated_filter.PNG)

---

### [USAB-02] Filter state conflict causing isolated recommendation lists
* **Feature / Screen:** Event Discovery / Interactive Suggestion Box
* **Severity Level:** High
* **Description:** Applying tags in the recommendation widget ignores existing active filters. For instance, filtering by "Lisboa" returns 4 events, but toggling recommendation tags ("weekend", "solo", "any budget") returns 5 events from all locations across Portugal, overriding the initial location criteria.
* **Steps to Reproduce:**
  1. Set location filter to **Lisboa** (returns 4 results).
  2. Scroll to the suggestion box and select **"Weekend"**, **"Solo"**, and **"Any budget"**.
  3. Observe the generated event list.
* **Expected vs. Actual Result:**
  * *Expected:* Display events in Lisboa matching weekend/solo criteria.
  * *Actual:* The recommendation widget resets location bounds and returns nationwide events, displaying two conflicting lists on the same page.
* **Suggested Fix:** Preserve active global filter states (e.g., location) when generating query parameters for the suggestion widget.
* **Evidence:** ![filter](media/sugestion.PNG) ![conflict sugestion](media/conflictant_sugestion.png)

---

### [USAB-03] Confusing form copy and missing turnaround timeline on event submission
* **Feature / Screen:** Event Submission / "Suggest an Event"
* **Severity Level:** Low
* **Description:** The AI event poster submission accurately parses uploaded posters, but the "About You" section uses wording that implies only official event owners can submit entries. Furthermore, upon submittal, the status changes to "Under Review" without providing an estimated review timeframe.
* **Steps to Reproduce:**
  1. Access the **Suggest an Event** option in the menu.
  2. Upload an event poster and wait for AI parsing.
  3. Fill in required fields (Website, Instagram) and submit.
* **Expected vs. Actual Result:**
  * *Expected:* Welcoming copy for community submissions and a confirmation banner specifying a expected review time (e.g., "Approved within 24–48 hours").
  * *Actual:* Copy discourages general users, and the "Under Review" message provides no expected completion date.
* **Suggested Fix:** Rephrase the "About You" section to encourage community submissions and add a clear turnaround SLA to the submission confirmation toast/dialogue.
* **Evidence:** ![message](media/submissão.PNG)

---

## 📐 Nielsen's Usability Heuristics Mapping

### [USAB-01] Redundant Filter Components
* **Heuristic Violated:** **#8 Aesthetic and Minimalist Design**
* **Analysis:** Repeating search inputs in close proximity adds visual noise and creates confusion over which control takes precedence.

### [USAB-02] Recommendation Filter Logic Conflict
* **Heuristic Violated:** **#4 Consistency and Standards** & **#2 Match Between System and the Real World**
* **Analysis:** Users expect secondary filters to narrow down current results, not reset global location settings silently.

### [USAB-03] Ambiguous Form Copy & Feedback
* **Heuristic Violated:** **#1 Visibility of System Status** & **#2 Match Between System and the Real World**
* **Analysis:** Providing no timeline for an "Under Review" state leaves users uncertain about task completion.
