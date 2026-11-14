# FaithfulMed: A Multi-Agent System for Faithful, Patient-Friendly Medical Explanations

### Break Through Tech AI Studio × Google | Fall 2026

**Project Status:** In Progress

**My Role:** Break Through Tech AI Fellow — Data Exploration, Verifier Agent Development, Baseline Pipeline Development, and Ablation Study

**Original Team Repository:** [FaithfulMed — Google 2E](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations)

---

## Project Overview

Medical information is often written in complex language that can be difficult for patients to understand. Clinical notes, lab reports, and discharge instructions frequently contain specialized terminology that creates barriers to health literacy.

Large language models (LLMs) offer opportunities to make medical information more accessible. However, AI-generated explanations can introduce unsupported claims, omit important clinical details, or change the meaning of the original information.

**FaithfulMed** is a collaborative project developed through Break Through Tech AI Studio in partnership with Google. The project explores whether a multi-agent AI system can generate medical explanations that are both easy for patients to understand and faithful to the original clinical information.

The proposed approach combines specialized AI agents, retrieval-augmented generation (RAG), source-grounded verification, and iterative refinement to improve the reliability and accessibility of AI-generated medical explanations.

### Core Research Question

> Does a pipeline of specialized agents produce explanations that are both more readable and more faithful than a single well-prompted LLM, and which agents actually matter for each goal?

---

## Project Objectives

The project aims to:

- Develop a multi-agent pipeline for generating patient-friendly medical explanations.
- Preserve the factual meaning of the original medical information.
- Identify unsupported claims, omissions, and inaccuracies in generated explanations.
- Compare the multi-agent system against a single-LLM baseline.
- Investigate the contribution of individual agents through ablation experiments.
- Evaluate trade-offs between readability, factual faithfulness, latency, and computational cost.

---

## System Architecture

The FaithfulMed project proposes a pipeline consisting of five specialized AI agents.

| Agent | Role |
|---|---|
| **Extractor** | Identifies and extracts important clinical facts from the source document. |
| **Simplifier** | Translates complex medical terminology into more accessible language using retrieval-augmented generation. |
| **Verifier** | Evaluates generated explanations for factual faithfulness, omissions, and unsupported claims. |
| **Refiner** | Revises explanations based on issues identified during verification. |
| **Readability** | Evaluates and improves the accessibility of the final explanation. |

### Proposed Pipeline

**Clinical Document → Extractor → Simplifier → Verifier → Refiner → Readability → Patient-Friendly Explanation**

The reference architecture uses Google's Agent Development Kit (ADK), with a sequential workflow and a bounded refinement loop between the Verifier and Refiner.

The project investigates how these specialized components contribute to the overall quality of generated medical explanations.

---

## My Individual Contributions

As a Break Through Tech AI Fellow, I have contributed to the development and evaluation of FaithfulMed through exploratory data analysis, AI agent development, baseline implementation, and experimental design.

### 1. Exploratory Data Analysis

Conducted exploratory data analysis to better understand the datasets supporting the project's medical text generation and evaluation tasks.

This work helped establish an understanding of the available data and its relevance to the system's development and evaluation.

### 2. Verifier Agent Development

Worked on developing the **Verifier agent**, a component designed to evaluate whether AI-generated medical explanations remain faithful to the original source information.

The Verifier is intended to identify:

- Unsupported or potentially hallucinated medical claims.
- Information inconsistent with the original clinical document.
- Omission of important medical details.
- Additional claims that are not supported by the source.

This work focuses on the challenge of improving the factual reliability of generative AI systems in healthcare applications.

### 3. Baseline Pipeline Development

Created a baseline pipeline to establish a reference point for evaluating the multi-agent system.

The baseline supports comparisons between a simpler LLM-based approach and the multi-agent architecture, helping investigate whether additional specialized agents provide measurable improvements.

### 4. Verifier Ablation Study

Developed an ablation version of the pipeline that removes the Verifier agent.

The purpose of this experiment is to investigate the Verifier's contribution to the overall system by comparing pipeline behavior with and without verification.

This work supports the project's broader research goal of understanding which agents are most important for factual faithfulness and readability.

---

## Datasets and Data Exploration

The FaithfulMed challenge identifies several publicly available, de-identified, synthetic, and expert-curated datasets for medical text simplification and evaluation.

| Dataset | Intended Use |
|---|---|
| **MedAESQA** | Faithfulness evaluation and Verifier calibration using human-annotated judgments. |
| **MTSamples** | De-identified medical reports for text simplification. |
| **PLABA** | Biomedical text paired with plain-language adaptations. |
| **MedQuAD** | Consumer health questions and answers for grounding and evaluation. |
| **Synthea** | Synthetic patient records for testing clinical document workflows. |
| **MedlinePlus** | Plain-language medical terminology for retrieval-augmented generation. |

These datasets are identified in the official project challenge. Not all datasets are necessarily used in every experiment.

### Data Exploration

My exploratory data analysis focused on understanding the data available for the project and how it could support the development and evaluation of the FaithfulMed system.

Additional exploratory visualizations and dataset-specific findings will be documented as the project progresses.

---

## Technical Approach

FaithfulMed investigates several techniques for developing trustworthy AI-generated medical explanations.

### Multi-Agent Orchestration

The proposed system uses Google's Agent Development Kit (ADK) to coordinate specialized agents responsible for extraction, simplification, verification, refinement, and readability.

### Retrieval-Augmented Generation

The architecture incorporates retrieval from authoritative medical information resources to support source-grounded explanations.

### Faithfulness Verification

The Verifier evaluates whether generated explanations are supported by the original clinical information.

The project's evaluation plan uses human-annotated evidence-support judgments as a reference for assessing verification quality.

### Baseline Comparison

A single-LLM baseline provides a reference for evaluating the benefits and limitations of the multi-agent architecture.

### Ablation Analysis

Ablation experiments investigate the role of individual components by removing agents and examining changes in system performance.

My ablation work specifically focuses on the pipeline without the Verifier.

---

## Evaluation Framework

The project evaluates system performance across several dimensions.

| Evaluation Dimension | Proposed Metric or Approach |
|---|---|
| **Readability** | Flesch-Kincaid Grade Level and SMOG |
| **Faithfulness** | Agreement with human-annotated evidence-support judgments |
| **Verifier Reliability** | Accuracy and Cohen's kappa |
| **Hallucination** | Frequency of unsupported or clinically meaningful inaccurate claims |
| **Agent Contribution** | Ablation comparisons |
| **System Efficiency** | Latency and computational cost |

### Project Performance Targets

The official project challenge defines the following targets:

- At least **80%** of outputs at or below an eighth-grade reading level.
- At least **85%** factual fidelity on the human-annotated test set.
- Fewer than **10%** of outputs containing clinically meaningful unsupported claims.
- At least **15 percentage points** of improvement in faithfulness compared with the single-agent baseline.
- At least **80%** agreement between the Verifier and human annotators, with a target Cohen's kappa of **0.6 or higher**.

**Note:** These are the project's intended success criteria, not completed experimental results.

---

## Results and Ongoing Evaluation

## 📊 Preliminary Results and Ongoing Evaluation

FaithfulMed is currently under active development. As part of my individual contribution, I developed and tested a Verifier agent designed to identify factual inconsistencies, unsupported claims, and missing information in patient-friendly medical explanations.

### Initial Verifier Test

I tested the Verifier using a fictional hospital discharge summary and a patient-friendly explanation containing intentionally introduced factual errors.

The Verifier produced the following preliminary results:

| Evaluation Category | Number of Claims |
|---|---:|
| Supported claims | 22 |
| Distorted claims | 3 |
| Unsupported claims | 1 |
| **Total claims evaluated** | **26** |
| Important omissions identified | 3 |

The Verifier reported an internal faithfulness score of **0.85** for this example, representing the proportion of claims it labeled as supported.

### Key Findings

The Verifier identified several potentially significant problems in the generated explanation:

- An incorrect medication dosing frequency.
- Advice to discontinue a blood thinner without consulting a healthcare professional.
- An unsupported exercise recommendation.
- A suspected medical condition incorrectly presented as a confirmed diagnosis.
- Missing information about medication duration and home-care instructions.

These preliminary findings demonstrate the Verifier's ability to flag different categories of potential factual errors in an illustrative test.

However, the judgments are generated by the Verifier itself and have not yet been validated against human annotations. Therefore, these results should not be interpreted as a measure of overall model accuracy.

### Visualizations

The Verifier development notebook includes code for visualizing the distribution of supported, distorted, and unsupported claims in the initial test.

### Ongoing Evaluation

I am continuing to investigate the Verifier's performance using Gemini baseline outputs and a pipeline variant without the Verifier.

Future evaluation will focus on:

- Comparing the complete multi-agent pipeline with the baseline.
- Measuring the effect of removing the Verifier.
- Evaluating agreement with human-annotated judgments.
- Analyzing factual faithfulness and readability across experiments.

Final quantitative results will be added once evaluation is complete.

### Notebook

See [`verifier_agent.ipynb`](notebooks/verifier_agent.ipynb) for the Verifier implementation, test cases, preliminary results, and visualization code.

### Current Contributions

My completed development work includes:

- Exploratory data analysis supporting the project.
- Development of the Verifier agent.
- Implementation of a baseline pipeline for comparison.
- Development of a pipeline variant without the Verifier for ablation analysis.

### Evaluation Questions

The ongoing experiments aim to investigate:

1. How does the complete multi-agent system compare with the baseline pipeline?
2. How does removing the Verifier affect the factual faithfulness of generated explanations?
3. Does verification introduce trade-offs in readability or system efficiency?
4. Which components contribute most to producing accurate, patient-friendly explanations?

### Planned Results and Visualizations

As experimental evaluation progresses, this section will be updated with:

- **Baseline vs. Multi-Agent Comparison:** Faithfulness and readability scores across pipeline configurations.
- **Verifier Ablation Results:** A comparison of the complete pipeline and the pipeline without the Verifier.
- **Readability Analysis:** Flesch-Kincaid and other readability metrics.
- **Faithfulness Evaluation:** Results comparing automated verification against human-annotated judgments.
- **Experimental Summary:** Tables and visualizations documenting observed performance differences.

Final conclusions will be reported after the experiments are completed and evaluated.

---

## Setup and Installation

The original FaithfulMed team repository contains the project implementation, supporting files, and an experimental Streamlit pipeline visualizer.

For the available setup instructions, refer to:

- [Original FaithfulMed Repository](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations)
- [Streamlit Setup and Demo Guide](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations/blob/main/DEMO.md)

The demo guide describes dependencies, API key configuration, the prepared Chroma database, and platform-specific commands.

The project visualizer is an experimental prototype and is **not intended to provide medical advice**. Only fictional or approved de-identified medical notes should be used. Submitted text is sent to the configured model provider.

Detailed reproduction instructions for the baseline and ablation experiments will be added after the corresponding workflows have been verified.

---

## Future Work

As development and evaluation continue, potential next steps include:

- Completing quantitative comparisons between the baseline and multi-agent pipelines.
- Evaluating the Verifier's effectiveness in identifying unsupported medical claims.
- Analyzing the impact of removing the Verifier through ablation experiments.
- Investigating additional agent ablations.
- Comparing performance across different LLMs.
- Examining trade-offs between readability, factual faithfulness, latency, and cost.
- Improving the transparency of generated explanations through evidence attribution.
- Exploring multilingual patient-friendly medical explanations.

---

## Skills and Experience

Through my contributions to FaithfulMed, I have gained experience in:

- Exploratory Data Analysis
- Generative AI and Large Language Models
- Multi-Agent AI Systems
- AI Agent Development
- Baseline Pipeline Development
- Ablation Studies
- Experimental Design
- AI System Evaluation
- Healthcare Natural Language Processing
- Collaborative Software Development

---

## Acknowledgments

FaithfulMed is a collaborative project developed through **Break Through Tech AI Studio in partnership with Google**.

I would like to acknowledge my fellow AI Studio team members, our AI Studio Coach **Jenna Hunte**, our Challenge Advisor **Samaneh Kazemi Nafchi**, and the Break Through Tech community for their guidance and contributions.

This personal repository highlights my individual contributions while recognizing the work of the full team.

**Original Team Repository:** [FaithfulMed — Break Through Tech / Google 2E](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations)

---

*FaithfulMed is an educational and research project exploring trustworthy AI-generated medical explanations. It is not intended to provide medical advice or replace professional clinical judgment.*
