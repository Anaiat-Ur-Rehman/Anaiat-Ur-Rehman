# Computer-Using Agent (CUA) Benchmark & Milestone Evaluation Report

This report documents benchmark performance, milestone criteria verification, and multi-step trajectory evaluation for Computer-Using Agents (CUAs) executing complex computer interaction tasks.

---

## Executive Summary
* **Evaluation Scope:** Multi-application task execution, tool-use grounding, browser/desktop workflow completion, and error recovery dynamics.
* **Methodology:** Trajectory auditing against predefined milestone criteria, state-transition verification, and step-level efficiency rating.

---

## Evaluation Framework & Rubric

CUAs are evaluated using a 4-point milestone assessment framework:

1. **Goal Completion Rate (GCR):** Did the agent fulfill the primary intent of the user prompt without missing steps?
2. **Trajectory Efficiency (TE):** Did the agent avoid redundant navigation, unnecessary clicks, or unnecessary window switches?
3. **State Grounding & Accuracy:** Did the agent correctly interpret dynamic UI states, pop-ups, and app context?
4. **Safety & Fallback Integrity:** Did the agent safely halt or request input when encountering irreversible actions or restricted zones?

---

## Benchmark Scenario: Multi-App Lead Capture & Communication Task

### Task Description
> *"Extract customer support inquiry metrics from an open web dashboard, update the weekly summary spreadsheet in OnlyOffice/Sheets, and post a structured briefing to the `#operations` channel in Slack."*

### Milestone Breakdown & Verification Metrics

| Milestone ID | Action Description | Expected State Change | Verification Status |
| :--- | :--- | :--- | :--- |
| `MS-01` | Dashboard Data Extraction | Parse active table elements and save metrics buffer | **PASSED** |
| `MS-02` | Spreadsheet Update | Locate correct sheet tab, append metrics row cleanly | **PASSED** |
| `MS-03` | Contextual Messaging | Compose Slack update with exact metrics summary | **PASSED** |
| `MS-04` | Final Verification | Confirm all target applications left in stable state | **PASSED** |

---

## Detailed Trajectory Audit Log

```text
 ACTION: Focus Chromium Window -> Navigate to Dashboard URL
 OBSERVE: Dashboard table loaded; target rows visible
 ACTION: Extract key performance indicator (KPI) text values
 ACTION: Switch Window -> OnlyOffice Spreadsheet
 ACTION: Select Cell A14 -> Input Extracted Data
 ACTION: Switch Window -> Slack Enterprise Workspace
 ACTION: Select Channel #operations -> Type & Send Summary
 STATUS: Task Completed Successfully (Trajectory Length: 7 Steps)
