# DataCV2026 Code Release and Cross-Review

This repository serves as the central place to publish the **public code repositories of the top-5 teams in each DataCV2026 Challenge track**, together with the review scope, compliance principles, and reporting instructions for cross-checking.

Submitted repositories will be listed here for cross-checking by other participating teams. If any potential violation is identified, teams may submit evidence following the instructions in this document. The organizing committee will then conduct a unified review and make the final decision.

> Note: this repository is intended as a public index and review notice. It does not replace the official challenge rules or evaluation platform.

## Official Link

- Challenge page: https://sites.google.com/view/datacv-2026-cvpr/challenge?authuser=0

## Repository Purpose

- Publish the code repositories of the top-5 teams in both tracks
- Clarify the review scope and compliance boundaries
- Provide a unified channel for cross-checking and issue reporting
- Keep a public and traceable record of the review process

## Review Targets

This round of public review covers the top-5 teams in the following two tracks:

- **Task 1**: Classic Illusion Understanding
- **Task 2**: Real-World Visual Illusions and Anomalies Understanding

## Review Focus

The organizing committee and participating teams may focus on the following aspects:

- The actual inference entry points and scripts used to generate submissions
- Prompts, system prompts, templates, role settings, and output constraints
- Data loading, image preprocessing, postprocessing, and result generation logic
- External model, API, and tool usage, including version information
- Retrieval resources, caches, example banks, rule bases, and intermediate artifacts
- Hidden dependencies, automated workflows, or external services that may affect compliance

## Compliance Principles

This review prioritizes competition fairness and consistency with the official rules. The following items are key review criteria.

### 1. No Training of Any Kind

All submissions must satisfy the **inference-only** requirement. Any form of training, fine-tuning, or parameter updating is prohibited, including but not limited to:

- Continued pretraining, supervised fine-tuning, or instruction tuning
- LoRA, adapters, prefix tuning, prompt tuning, P-Tuning, or similar parameter-learning methods
- Distillation, alignment training, preference optimization, or reinforcement learning
- Any retraining process based on competition data, test data, or their derived variants

If a base model or third-party API is used, it must be used directly for inference rather than as a version additionally adapted or trained for this challenge.

### 2. Prompt Engineering Is Allowed, but Test Information Must Not Be Injected

The following are allowed as long as no model training is involved:

- System prompt and user prompt design
- In-context learning, routing, tool use, and agent-style pipelines
- Compliant input organization, output parsing, and rule-based postprocessing

However, such methods must not explicitly or implicitly encode, absorb, or exploit hidden validation or test information.

### 3. Test Samples Must Not Be Annotated or Repackaged

The following are considered high-risk behaviors and will be closely reviewed:

- Manual or semi-automatic annotation of test samples
- Adding answers, labels, categories, attributes, or explanations to test samples
- Building rules, heuristics, templates, or answer banks from test content
- Producing reference answers through internal annotation, outsourcing, or crowdsourcing

### 4. Test Samples Must Not Be Used as Few-Shot, Memory, or Retrieval Resources

Hidden validation samples, test samples, and their variants must not be included in any of the following:

- Few-shot examples
- Example banks or memory banks
- Retrieval corpora or caches
- Rule templates or prompt templates

If an official exemplar pool is provided for `task1`, only that officially allowed resource may be used. Hidden validation and test content must not be added to it in any form.

### 5. Test Leakage and Undisclosed External Adaptation Are Prohibited

The review will specifically look for, but is not limited to, the following:

- Using test answers, pseudo-labels, or human observations to tune prompts
- Constructing specialized rules from test-set distributions, screenshots, or prompt fragments
- Calling undisclosed external services that have already been adapted to this challenge
- Introducing test-related clues through private knowledge bases, hidden scripts, or middle-layer services

### 6. Task 1 Must Not Be Solved by Explicit Measurement or Calculation Rules

`task1` is perception-focused. Any method that derives answers through explicit measurement, geometric calculation, or pixel-level statistics should not be considered compliant, including but not limited to:

- Measuring length, angle, distance, or area to decide the answer
- Using rulers, grids, coordinates, or edge fitting for quantitative judgment
- Making decisions directly from pixel ratios, area statistics, color statistics, or manual thresholds
- Wrapping such logic inside scripts, tools, or agent pipelines to bypass review

Only presentation-oriented processing that does not produce decisive quantitative conclusions is allowed, such as resizing, normalization, or moderate zooming and cropping.

## Recommended Materials in Public Repositories

To facilitate review, teams entering the public review stage are recommended to provide at least the following:

- Environment instructions, including Python version, dependency installation, and system requirements
- A minimal reproducible command or clear run instructions
- The actual inference entry point corresponding to the submitted results
- Prompts, templates, configuration files, and related explanations
- The names, versions, and calling methods of external models or APIs
- The source and construction method of retrieval, cache, or rule systems
- The commit, tag, or version identifier corresponding to the final results

When necessary, the organizing committee may further request:

- Explanations of key scripts
- Screen recordings or live reproduction
- External dependency declarations
- A result generation workflow description
- Additional compliance materials

## Public Repository List


### Task 1: Classic Illusion Understanding

| Rank | Team | Repository | Status | Notes |
| --- | --- | --- | --- | --- |
| 1 | `ziplab` | [DDP](https://github.com/ziplab/DDP) | `Under Review` | `-` |
| 2 | `phi6kai` | [sf-illusion-aware-vlm](https://github.com/jasminezz/sf-illusion-aware-vlm) | `Under Review` | `-` |
| 3 | `yangfanqihang` | [DataCV2026-Task1-yangfanqihang](https://github.com/liangc001/DataCV2026-Task1-yangfanqihang) | `Under Review` | `-` |
| 4 | `snowpine007` | [cvpr_2026_datacv_submission](https://github.com/Davidxswang/cvpr_2026_datacv_submission) | `Under Review` | `-` |
| 5 | `sifan077` | [DataCV2026-task1](https://github.com/sifan077/DataCV2026-task1) | `Under Review` | `-` |

### Task 2: Real-World Visual Illusions and Anomalies Understanding

| Rank | Team | Repository | Status | Notes |
| --- | --- | --- | --- | --- |
| 1 | `hugh-bao` | [Edit-Crop-and-Prompt-Engineering](https://github.com/Jingwei-Bao/Edit-Crop-and-Prompt-Engineering) | `Under Review` | `-` |
| 2 | `yiming_zhang` | Not provided | `Pending Submission` | `-` |
| 3 | `ziplab` | [DDP](https://github.com/ziplab/DDP) | `Under Review` | `-` |
| 4 | `yangfanqihang` | [DataCV2026-Task2-yangfanqihang](https://github.com/liangc001/DataCV2026-Task2-yangfanqihang) | `Under Review` | `-` |
| 5 | `snowpine007` | [cvpr_2026_datacv_submission](https://github.com/Davidxswang/cvpr_2026_datacv_submission) | `Under Review` | `-` |

## Review Procedure

The public release and cross-review process is expected to proceed as follows:

1. The organizing committee asks the top-5 teams in both tracks to submit publicly accessible repositories.
2. The organizing committee conducts an initial review, focusing on training risks, test leakage risks, and few-shot compliance.
3. Repositories that pass the initial review are published in this repository.
4. Other participating teams conduct cross-checks during the public review period and submit issues, evidence, and reproduction details if needed.
5. The organizing committee performs follow-up review based on received feedback and may request additional materials, clarifications, or live demonstrations.
6. The organizing committee issues the final review decision and determines whether rankings should be retained, adjusted, or revoked.

## Issue Reporting

To improve review efficiency, issue reports are encouraged to include:

- The task and team involved
- The repository link, branch, commit, or relevant file path
- A description of the issue and the suspected type of violation
- Related screenshots, logs, code snippets, or reproduction steps

Suggested template:

```text
Task:
Team:
Repository:
Relevant commit:
Suspected violation type:
Description:
Evidence:
Reproduction steps (if any):
```


## Contact

- Contact email: `datacv2025@gmail.com`

## Statement

The information published in this repository is intended solely for result verification, academic communication, and compliance review for the DataCV2026 competition. Unless explicitly stated otherwise, the publication of repository links does not imply any additional authorization, nor does it indicate that the organizing committee has already reached a final conclusion on the corresponding method.
