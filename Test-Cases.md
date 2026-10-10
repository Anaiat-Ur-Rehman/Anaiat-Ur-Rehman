# Computer-Using Agent (CUA) & Multi-App Workflow Test Cases

This document outlines benchmark QA test scenarios designed to evaluate Computer-Using Agents (CUAs) and LLM-driven automation tools executing multi-step cross-application tasks.

---

## Test Suite Overview
* **Primary Objective:** Verify CUA accuracy, tool-use trajectory, and milestone completion across web browsers, desktop suites, and communication platforms.
* **Domain Focus:** Cross-Application Business Workflows, Data Extraction, and Multi-step Logistics.

---

## Test Case CUA-01: Cross-Platform Data Extraction & Reporting

* **Test Case ID:** `CUA-TC-001`
* **Title:** Extract Lead Data from Email Draft and Sync to Spreadsheet & Slack
* **Severity/Priority:** High
* **Environment:** OnlyOffice Spreadsheet / Google Sheets, Outlook Web, Slack Enterprise Grid

### Pre-conditions
1. CUA has active authorization for browser session, spreadsheet access, and Slack environment.
2. Target lead email is open in the client view containing unstructured contact details.

### Test Steps & Trajectory
1. **Step 1:** Scan and parse text in email body to extract: `Client Name`, `Company Name`, `Estimated Deal Value`, and `Follow-up Date`.
2. **Step 2:** Open target tracking spreadsheet (`Sales_Pipeline_2026.xlsx`).
3. **Step 3:** Locate the first empty row and append extracted values into designated columns.
4. **Step 4:** Switch to Slack client, navigate to channel `#sales-updates`, and compose a summary notification referencing the updated row.

### Expected Behavior
* Agent extracts data with 100% field accuracy without dropping context.
* Spreadsheet row formatting remains intact.
* Slack notification is dispatched successfully with precise parameters.

### Failure Criteria
* Hallucination of deal values or misaligned column placement.
* Failure to locate application windows or loss of browser focus.

---

## Test Case CUA-02: Multi-Hop Research & Document Synthesis

* **Test Case ID:** `CUA-TC-002`
* **Title:** BrowseComp Multi-Hop Data Retrieval & Structured Summary Verification
* **Severity/Priority:** Medium-High
* **Environment:** Chromium Web Browser, OnlyOffice Document / Google Docs

### Pre-conditions
1. Web browser initialized with network access enabled.
2. Target prompt specifies ambiguous search parameters requiring iterative multi-hop retrieval.

### Test Steps & Trajectory
1. **Step 1:** Execute primary search query to locate official clinical guidance parameters.
2. **Step 2:** Cross-reference retrieved policy against secondary source to verify factual consistency.
3. **Step 3:** Synthesize verified facts into a structured Markdown summary report.

### Expected Behavior
* Agent identifies authoritative sources without falling into hallucination traps.
* Trajectory path avoids infinite browsing loops or dead links.

---

## Execution Log & Status
| Test ID | Environment | Execution Status | Benchmark Score |
| :--- | :--- | :--- | :--- |
| `CUA-TC-001` | Multi-App (Email/Sheet/Slack) | **PASSED** | 98.5% |
| `CUA-TC-002` | Browser Multi-Hop Research | **PASSED** | 96.0% |
