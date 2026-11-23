# Large Language Models in Software Security: Vulnerability Introduction, Detection, and Repair

SOEN6431 course report (Group 7)

## Overview

This report reviews five studies on how large language models (LLMs) introduce software security risks and how they can help detect and repair vulnerabilities. Coding assistants can suggest insecure implementations and nonexistent dependencies, while developers may overestimate the security of AI-assisted code. LLMs can flag suspicious code and propose patches, but their findings, explanations, and fixes can be wrong.

The report argues that model output can help reviewers decide where to look and which fixes to consider. Approval of security-sensitive changes should depend on verified code behavior and dependency provenance, supported by tests and established analysis tools.

## Studies Reviewed

| Study | Finding discussed in the report |
| --- | --- |
| Pearce et al., *Asleep at the Keyboard? Assessing the Security of GitHub Copilot's Code Contributions* (Communications of the ACM, 2025) | Copilot suggested vulnerable implementations in security-sensitive programming scenarios. |
| Perry et al., *Do Users Write More Insecure Code with AI Assistants?* (ACM CCS, 2023) | In the study's programming tasks, participants with an AI assistant wrote less secure code overall and were more likely to believe their solutions were secure. |
| Spracklen et al., *We Have a Package for You! A Comprehensive Analysis of Package Hallucinations by Code Generating LLMs* (USENIX Security, 2025) | Models recommended nonexistent packages, highlighting the need to verify a dependency's identity and source. |
| Ullah et al., *LLMs Cannot Reliably Identify and Reason About Security Vulnerabilities (Yet?): A Comprehensive Evaluation, Framework, and Benchmarks* (IEEE Symposium on Security and Privacy, 2024) | Models missed vulnerabilities, flagged patched code, and sometimes reached correct verdicts with faulty explanations. |
| Pearce et al., *Examining Zero-Shot Vulnerability Repair with Large Language Models* (IEEE Symposium on Security and Privacy, 2023) | Models could propose repairs without worked examples, but producing correct patches for historical vulnerabilities remained difficult. |

The report proposes a controlled study comparing standard code review with the same workflow assisted by an LLM. Independent assessors would measure confirmed findings, missed vulnerabilities, false alarms, review time, and whether accepted repairs remove the weakness while preserving intended behavior.

## LaTeX Sources

- The main document contains the abstract, background, discussion, and conclusions. [Main LaTeX source](IEEE-conference-template-062824/IEEE-conference-template-062824.tex)
- Part 4 reviews the SecLLMHolmes vulnerability detection and reasoning benchmark. [Part 4 source](IEEE-conference-template-062824/part4-vulnerability-detection.tex)
- The bibliography contains publication details for all five studies. [BibTeX references](IEEE-conference-template-062824/references.bib)

**Draft status.** The individual review for Part 4 is written. The individual reviews for Parts 1, 2, 3, and 5 are pending.

## Build the PDF

Use a LaTeX distribution with `latexmk`, `pdflatex`, BibTeX, and the `IEEEtran.bst` bibliography style. Run these commands from the repository root.

```sh
cd IEEE-conference-template-062824
latexmk -pdf IEEE-conference-template-062824.tex
```

The build generates `IEEE-conference-template-062824.pdf` in the LaTeX directory. Git ignores the PDF and intermediate build files.
