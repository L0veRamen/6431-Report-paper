# Large Language Models in Software Security: Vulnerability Introduction, Detection, and Repair

SOEN6431 course report, Group 7: Chen Qian, Seyed Amir Kiarash Abbasi, and Yourun Lan.

## Overview

This report reviews five studies to assess what large language models (LLMs) contribute to software security and whether their judgments can support merge decisions. Coding assistants produced insecure code and recommended nonexistent packages. In a randomized study, users with assistant access rated their code as more secure than controls on all five tasks, yet submitted fully secure solutions less often on four. In detection tests, models missed vulnerabilities, flagged patched code, and gave incorrect explanations. Models generated viable repair candidates, although some patches passed automated checks and failed closer inspection.

The report recommends retaining human approval for security-sensitive changes, using model findings to direct inspection, and verifying the provenance of new dependencies separately.

## Studies Reviewed

| Study | Finding discussed in the report |
| --- | --- |
| Pearce et al., *Asleep at the Keyboard? Assessing the Security of GitHub Copilot's Code Contributions* (Communications of the ACM, 2025) | Copilot suggested vulnerable implementations in security-sensitive programming scenarios. |
| Perry et al., *Do Users Write More Insecure Code with AI Assistants?* (ACM CCS, 2023) | Participants with assistant access submitted fully secure solutions less often on four of five tasks and rated their code as more secure on every task. |
| Spracklen et al., *We Have a Package for You! A Comprehensive Analysis of Package Hallucinations by Code Generating LLMs* (USENIX Security, 2025) | Models recommended nonexistent packages, highlighting the need to verify a dependency's identity and source. |
| Ullah et al., *LLMs Cannot Reliably Identify and Reason About Security Vulnerabilities (Yet?): A Comprehensive Evaluation, Framework, and Benchmarks* (IEEE Symposium on Security and Privacy, 2024) | Models missed vulnerabilities, flagged patched code, and sometimes reached correct verdicts with faulty explanations. |
| Pearce et al., *Examining Zero-Shot Vulnerability Repair with Large Language Models* (IEEE Symposium on Security and Privacy, 2023) | Models could propose repairs without worked examples, but producing correct patches for historical vulnerabilities remained difficult. |

The report proposes an offline trial comparing human review, LLM review without a human reviewer, and human review with LLM assistance, all using identical automated checks. Assessors unaware of the review method would measure how often vulnerable changes are approved and sound changes are blocked, how long reviews take, and whether accepted repairs preserve behavior while removing the weakness.

## LaTeX Sources

- The main document contains the title page, contributions table, abstract, introduction, background, discussion, and conclusions. [Main LaTeX source](IEEE-conference-template-062824/IEEE-conference-template-062824.tex)
- Part 3 reviews package hallucinations by code-generating LLMs (Yourun Lan). [Part 3 source](IEEE-conference-template-062824/part3-package-hallucinations.tex)
- Part 4 reviews the SecLLMHolmes vulnerability detection and reasoning benchmark (Chen Qian). [Part 4 source](IEEE-conference-template-062824/part4-vulnerability-detection.tex)
- Part 5 reviews zero-shot vulnerability repair (Seyed Amir Kiarash Abbasi). [Part 5 source](IEEE-conference-template-062824/part5-vulnerability-repair.tex)
- The bibliography contains publication details for all five studies. [BibTeX references](IEEE-conference-template-062824/references.bib)

**Draft status.** The introduction, background, discussion, conclusions, and the individual reviews for Parts 3, 4, and 5 are written. The individual reviews for Parts 1 and 2 are pending, and their contributors are not yet assigned in the contributions table.

## Build the PDF

Use a LaTeX distribution with `latexmk`, `pdflatex`, BibTeX, and the `IEEEtran.bst` bibliography style. Run these commands from the repository root.

```sh
cd IEEE-conference-template-062824
latexmk -pdf IEEE-conference-template-062824.tex
```

The build generates `IEEE-conference-template-062824.pdf` in the LaTeX directory. Git ignores the PDF and intermediate build files.
