# Prefetch Analysis Home Lab – Investigation Walkthrough

## Table of Contents
- What are Prefetch Files?
- Attack Scenario
- Setting Up VM Environment
- Begin Analysis and Create Timeline
- Prefetch File Deep Dive
- Finalizing the Scope and Timeline
- Simple Write-Up of The Investigation
- Tools Used
- Methods Used

---

## What are Prefetch Files?
Regarding digital forensics, Windows Prefetch files represent a semi-hidden treasure trove of evidence for investigators analyzing system activity. Automatically created by Windows to optimize application loading times, these files inadvertently serve as detailed logs of program execution history. Prefetch files track when applications run, how often they execute, and which resources they access during startup.

“In this homelab project, we’ll explore the practical application of Prefetch file analysis, working through a hands-on investigation designed to build skills in extracting, interpreting, and leveraging this valuable evidence. The lab uses Prefetch files collected from a system involved in a simulated breach scenario.“

---

## Attack Scenario
I’m investigating a security incident involving a workstation belonging to Bill Lumbergh at Initech Software. “Bill is an IT technician with aspirations of transitioning into the cybersecurity field.”

While searching for free penetration testing resources, Bill used Reddit to locate a cracked version of BurpSuite Pro. Unfortunately, an unscrupulous Redditor appears to have provided Bill with malware instead of legitimate software.

In this lab, I’ve obtained crucial forensic artifacts from Bill’s system (post-compromise) to analyze what occurred after he executed the malicious file. This lab will specifically focus on the Prefetch files recovered from Bill’s computer. I’m investigating using this single artifact (prefetch files) reveals information about the attack sequence, methods, and timeline.

Throughout this lab, I’ll document my analysis process, tools used, and key findings to demonstrate how Prefetch files can provide valuable insights during cybersecurity investigations.

---

## Setting Up VM Environment
1. Downloading VMware Workstation Pro (Link):

2. Download and deploy a Windows 11 VM directly from Microsoft (Link):

3. I opened PowerShell in an Administrative window and typed the following command:

“IEX (New-Object Net.Webclient).downloadstring(“https://ec-blog.s3.us-east-1.amazonaws.com/DFIR-Lab/PF_Lab/prep_lab.ps1&#8221;)“

Press enter or click to view image in full size

^ This command executes a script that will automatically install .NET 6, Eric Zimmerman’s tools, as well as download the forensic evidence.

4. After verifying the evidence has been collected and is in the correct file location, I begin my analysis.

Press enter or click to view the image in full size


> **Screenshot placeholder:** `[ADD: setup-script-run.png]`  
> **Screenshot placeholder:** `[ADD: evidence-location.png]`

---

## Begin Analysis and Create Timeline
( paste this section )

> **Screenshot placeholder:** `[ADD: pecmd-directory-command.png]`  
> **Screenshot placeholder:** `[ADD: timeline-explorer-open-csv.png]`  
> **Screenshot placeholder:** `[ADD: prefetch-timeline-view.png]`  
> **Screenshot placeholder:** `[ADD: burpsuite-search-result.png]`  
> **Screenshot placeholder:** `[ADD: tagging-example.png]`

---

## Prefetch File Deep Dive
( paste this section )

> **Screenshot placeholder:** `[ADD: pecmd-7zg-ou]()
