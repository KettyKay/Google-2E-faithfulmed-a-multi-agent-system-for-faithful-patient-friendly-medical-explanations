# FaithfulMed: A Multi-Agent System for Faithful, Patient-Friendly Medical Explanations

### Break Through Tech AI Studio | Google | Fall 2026

**Project Type:** Generative AI, Multi-Agent Systems, Natural Language Processing, Healthcare AI

**My Role:** Break Through Tech AI Fellow — Data Exploration, Verifier Agent Development, Baseline Pipeline, and Ablation Study

**Original Team Repository:** [FaithfulMed — Google 2E](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations)

## Project Overview

Medical documents often contain complex terminology and technical language that can be difficult for patients to understand. Although large language models (LLMs) can simplify medical information, they may also introduce unsupported claims, omit important details, or change the meaning of the original text.

FaithfulMed explores a multi-agent AI approach to generating medical explanations that are both accessible to patients and faithful to the original clinical information.

The project investigates whether specialized AI agents can improve the quality of medical explanations compared with a single-LLM baseline, particularly in terms of factual faithfulness and readability.

## Project Objectives

The primary objectives of FaithfulMed are to:

- Generate patient-friendly explanations of complex medical information.
- Preserve the factual meaning of the original medical text.
- Identify unsupported, inaccurate, or omitted information in generated explanations.
- Compare a multi-agent approach against a single-LLM baseline.
- Investigate how individual agents contribute to the system's overall performance.
- Evaluate the trade-offs between readability and factual faithfulness.

## Proposed System Architecture

The FaithfulMed project brief describes a pipeline of specialized agents, each responsible for a different part of the explanation process.

| Agent | Responsibility |
|---|---|
| Extractor | Identifies important clinical facts from the source document. |
| Simplifier | Translates complex medical language into more accessible explanations. |
| Verifier | Evaluates whether generated explanations are supported by the original medical information. |
| Refiner | Addresses issues identified during verification. |
| Readability | Evaluates and improves the accessibility of the final explanation. |

The project also investigates the value of individual agents through controlled comparisons and ablation experiments.

## My Individual Contributions

As a Break Through Tech AI Fellow, I contributed to the project's data exploration, AI agent development, and experimental evaluation.

### 1. Exploratory Data Analysis

Conducted exploratory data analysis to better understand the datasets used in the project.

This work supported my understanding of the available medical text, dataset characteristics, and the information needed to develop and evaluate the system.

### 2. Verifier Agent Development

Worked on developing the Verifier agent, a component designed to evaluate the factual faithfulness of AI-generated medical explanations.

The Verifier's purpose is to assess whether generated content is supported by the original medical information and identify potential inaccuracies or unsupported statements.

This work focused on the challenge of maintaining factual reliability while using generative AI to simplify complex medical information.

### 3. Baseline Pipeline Development

Created a baseline pipeline to provide a reference point for evaluating the multi-agent system.

The baseline supports comparisons between a simpler approach and the multi-agent architecture, helping assess whether the additional system components provide measurable improvements.

### 4. Ablation Study: Pipeline Without the Verifier

Developed an ablation version of the pipeline that excludes the Verifier agent.

The purpose of this experiment was to investigate the Verifier's contribution to the system by comparing the pipeline with and without that component.

This comparison helps examine the role of verification in maintaining factual faithfulness and understanding the trade-offs involved in the multi-agent architecture.

## Datasets and Evaluation

The FaithfulMed project brief identifies several public, de-identified, synthetic, and expert-curated datasets relevant to medical text simplification and evaluation.

These include:

- **MedAESQA:** Medical question-answering data containing expert answers and human judgments of accuracy and evidence support.
- **MTSamples:** De-identified transcribed medical reports.
- **PLABA:** Biomedical text paired with plain-language adaptations.
- **MedQuAD:** Consumer health questions and answers.
- **Synthea:** Synthetic patient health records.

The project emphasizes evaluating generated explanations for both readability and factual faithfulness.

The proposed evaluation framework includes:

- **Faithfulness:** Whether generated statements are supported by source information.
- **Hallucinations:** Whether explanations introduce unsupported medical claims.
- **Readability:** How accessible the generated explanations are to non-specialist readers.
- **Ablation comparisons:** How system behavior changes when an agent is removed.

Dataset descriptions and evaluation goals are documented in the Break Through Tech project brief. The datasets used in my individual experiments should be verified against the implementation.

## Experimental Approach

My contributions supported three main comparisons:

| Experiment | Purpose |
|---|---|
| Baseline pipeline | Establish a reference point for evaluating the multi-agent system. |
| Multi-agent pipeline | Examine the behavior of the system with its specialized components. |
| Pipeline without Verifier | Investigate the contribution of the Verifier agent. |

The ablation experiment is particularly important because it isolates one component of the architecture and allows its contribution to be studied.

## Results and Key Findings

**Results to be added from the team's completed experiments.**

The project is designed to investigate:

- Whether the multi-agent system improves faithfulness compared with the baseline.
- How removing the Verifier affects generated explanations.
- Whether improvements in readability can be achieved while preserving factual accuracy.

Quantitative results and conclusions will be documented here using actual experimental outputs.

## Visualizations

Relevant visualizations for this project include comparisons of faithfulness and readability across the baseline, complete pipeline, and pipeline without the Verifier.

**Add actual experimental plots or tables here when available.**

## Reproducing the Project

The implementation, dependencies, notebooks, and available setup instructions are maintained in the [original team repository](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations).

Refer to that repository for the project files and instructions. Exact commands for running the baseline, Verifier, and ablation experiments should be documented after confirming the relevant scripts and dependencies.

## Potential Next Steps

Potential future directions include:

- Further evaluating the Verifier's ability to identify unsupported medical claims.
- Expanding ablation experiments to investigate other agents.
- Comparing the system across additional medical text datasets.
- Exploring the trade-offs between readability, faithfulness, and computational cost.
- Improving the transparency and interpretability of the verification process.

## Skills and Experience

Through this project, I gained practical experience with:

- Exploratory Data Analysis
- Generative AI and Large Language Models
- Multi-Agent AI Systems
- AI Agent Development
- Baseline Pipeline Development
- Ablation Studies
- Experimental Design and Model Evaluation
- Healthcare Natural Language Processing
- Collaborative AI Research and Development

## Acknowledgments

FaithfulMed is a collaborative project completed through **Break Through Tech AI Studio in partnership with Google**.

I acknowledge the contributions of my teammates, project advisors, and the Break Through Tech community.

This README highlights my individual contributions while recognizing the project as a collaborative effort.

**Original Project:** [Break Through Tech — Google 2E FaithfulMed](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations)

