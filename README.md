# MTO Engineering Survey Validation Tool

**Automated Quality Assurance for Highway Control Surveys**

## 📌 Project Overview
The integrity of transportation engineering databases relies on the precise integration of external survey data. Manual validation of CAD (`.dwg`) submissions is time-consuming and prone to human error.

This project implements a **Python (ArcPy) automated validation tool** designed to rigorously stress-test incoming survey control files against Ministry standards. It acts as a "Gatekeeper," ensuring only compliant, high-precision data enters the master engineering environment.

## 🚀 Features
* **Projection Validation:** Programmatically enforces **NAD83 (CSRS) UTM Zone 16N** (EPSG: 3160) compliance.
* **In-Memory Processing:** Loads Master Control datasets into RAM for high-speed analysis.
* **Proximity Algorithms:** Uses Euclidean distance logic to detect spatial drift.
* **Automated Reporting:** Generates detailed Pass/Fail logs flagging any point exceeding the **0.05m (5cm)** engineering tolerance.

## 📊 Test Results (Simulated Sabotage)
The tool was tested against a dataset where specific surveyor errors were intentionally introduced to verify detection logic.

```text
MTO ENGINEERING SURVEY QA REPORT
================================
[PASS] Projection Verified: NAD_1983_CSRS_UTM_Zone_16N

[PASS] CAD_ID: Pt_1 | MATCH: MTO-001 | DELTA: 0.000m
[FAIL] CAD_ID: Pt_2 | MATCH: MTO-002 | DELTA: 29.988m  <-- Gross Error Detected
[FAIL] CAD_ID: Pt_3 | MATCH: MTO-003 | DELTA: 66.321m  <-- Drift Error Detected
[PASS] CAD_ID: Pt_4 | MATCH: MTO-004 | DELTA: 0.000m
[PASS] CAD_ID: Pt_5 | MATCH: MTO-005 | DELTA: 0.000m

## 🛠️ Technical Stack
* **Language:** Python 3.13.7
* **Library:** Esri ArcPy (Data Access Module)
* **Software:** ArcGIS Pro 3.6

## 👤 Author
**Mirza Ibrahim**
*GIS Technician / Geomatics Specialist*
