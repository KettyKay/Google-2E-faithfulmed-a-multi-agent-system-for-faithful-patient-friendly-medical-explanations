# FaithfulMed: A Multi-Agent System for Faithful, Patient-Friendly Medical Explanations

**Break Through Tech AI Studio | Google | Fall 2026**

**My Role:** AI Fellow — Data Exploration, Verifier Agent Development, Baseline Pipeline Development, and Ablation Study

**Original Team Repository:** [FaithfulMed — Google 2E](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations)

## Project Overview

Medical information is often written in technical language that can be difficult for patients to understand. Clinical notes, lab reports, and discharge instructions frequently contain specialized terminology that creates barriers to health literacy.

Large language models (LLMs) offer opportunities to make this information more accessible. However, simplifying medical text using generative AI introduces an important challenge: ensuring that the generated explanations remain faithful to the original medical information without adding unsupported or potentially misleading claims.

**FaithfulMed** is a collaborative Break Through Tech AI Studio project in partnership with Google that explores a multi-agent LLM architecture for generating patient-friendly medical explanations.

The project combines specialized AI agents, retrieval-augmented generation (RAG), source-grounded verification, and iterative refinement to investigate how medical explanations can become easier to understand while maintaining factual accuracy.

### Core Research Question

> Does a pipeline of specialized agents produce explanations that are both more readable and more faithful than a single well-prompted LLM, and which agents contribute most to each goal?

## Project Objectives

The project aims to:

- Develop a multi-agent pipeline for transforming complex medical text into patient-friendly explanations.
- Preserve factual faithfulness to the original clinical information.
- Detect unsupported claims, omissions, and inaccuracies in AI-generated explanations.
- Compare the multi-agent pipeline against a single-LLM baseline.
- Evaluate the contribution of individual agents through ablation studies.
- Examine trade-offs between readability, factual faithfulness, latency, and computational cost.

## System Architecture

The proposed FaithfulMed architecture consists of five specialized agents working together.

| Agent | Responsibility |
|---|---|
| **Extractor** | Extracts important clinical facts from the source medical document. |
| **Simplifier** | Uses plain-language rewriting and retrieval-augmented generation to simplify medical terminology. |
| **Verifier** | Evaluates generated explanations for factual faithfulness, omissions, and unsupported information. |
| **Refiner** | Revises explanations based on issues identified during verification. |
| **Readability** | Evaluates and improves the accessibility of the generated explanations. |

The reference architecture uses Google's Agent Development Kit (ADK), with a sequential workflow and a bounded refinement loop between the Verifier and Refiner.

The project also investigates how individual agents affect system performance through controlled experiments.

## My Individual Contributions

As a Break Through Tech AI Fellow, I contributed to the development and evaluation of FaithfulMed, focusing on data exploration, verification, baseline development, and ablation analysis.

### 1. Exploratory Data Analysis

Conducted exploratory data analysis to understand the datasets supporting the project's medical text generation and evaluation tasks.

This work contributed to understanding the available data and its relevance to the development and assessment of the FaithfulMed pipeline.

### 2. Verifier Agent Development

Developed a Verifier agent designed to assess whether generated medical explanations remain faithful to their source information.

The Verifier focuses on identifying potential issues such as:

- Unsupported medical claims.
- Information that is inconsistent with the original source.
- Omission of important clinical details.
- Additional information not supported by the source text.

The project's verification approach uses LLM-based faithfulness evaluation, with human-annotated medical data identified as a reference for calibration.

This contribution focused on the reliability of AI-generated explanations, an important consideration when applying generative AI to healthcare information.

### 3. Baseline Pipeline Development

Created a baseline pipeline to establish a reference point for evaluating the multi-agent approach.

The baseline enables comparisons between a simpler LLM-based generation process and the proposed multi-agent system.

This work supports the project's central research question by providing a comparison against which the value of additional specialized agents can be assessed.

### 4. Ablation Study: Removing the Verifier Agent

Developed an ablation version of the pipeline without the Verifier agent.

The purpose of this experiment was to isolate the Verifier's contribution and investigate how removing verification affects system behavior.

The experiment was designed to support comparisons between:

- The complete multi-agent pipeline.
- A pipeline without the Verifier agent.

This work contributes to understanding the importance of verification within multi-agent AI systems.

## Datasets

The FaithfulMed challenge identifies several datasets for medical text simplification, retrieval, and evaluation.

| Dataset | Intended Role |
|---|---|
| **MedAESQA** | Faithfulness evaluation and Verifier calibration using human-annotated judgments. |
| **MTSamples** | De-identified clinical reports for medical text simplification. |
| **PLABA** | Biomedical text and corresponding plain-language adaptations. |
| **MedQuAD** | Consumer health questions and answers for grounding and evaluation. |
| **Synthea** | Synthetic patient records for testing clinical document workflows. |
| **MedlinePlus** | Lay-language medical terminology for retrieval-augmented generation. |

These are the datasets identified in the project challenge. Their inclusion here does not imply that every dataset was used in each experiment.

The project emphasizes the use of publicly available, de-identified, synthetic, or expert-curated data rather than identifiable patient information.

## Technical Approach

The project combines several techniques for developing and evaluating trustworthy generative AI systems.

### Multi-Agent Orchestration

The reference architecture uses Google's Agent Development Kit to coordinate specialized agents responsible for extraction, simplification, verification, refinement, and readability.

### Retrieval-Augmented Generation

The proposed system incorporates retrieval from authoritative health information resources to support explanations grounded in medical terminology and source material.

### Faithfulness Verification

The Verifier evaluates whether generated explanations are supported by the original medical information.

The project proposes using human-annotated evidence-support judgments to assess the quality of automated verification.

### Baseline Comparison

A single-LLM approach provides a reference for determining whether a more complex multi-agent architecture offers measurable improvements.

### Ablation Analysis

Ablation studies investigate the contribution of individual agents by removing components and comparing the resulting system behavior.

My ablation work focused specifically on removing the Verifier.

## Evaluation Framework

The project challenge defines several evaluation dimensions:

| Evaluation Dimension | Metric or Approach |
|---|---|
| Readability | Flesch-Kincaid Grade Level and SMOG |
| Faithfulness | Agreement with human-annotated evidence-support judgments |
| Verifier Reliability | Accuracy and Cohen's kappa |
| Hallucination | Unsupported or clinically meaningful inaccurate claims |
| Agent Contribution | Ablation comparisons |
| System Efficiency | Latency and computational cost |

### Project Performance Targets

The official challenge establishes the following targets:

- At least **80%** of outputs at or below an eighth-grade reading level.
- At least **85%** factual fidelity on the human-annotated test set.
- Fewer than **10%** of outputs containing a clinically meaningful unsupported claim.
- At least **15 percentage points** of improvement in faithfulness compared with the single-agent baseline.
- At least **80%** agreement between the Verifier and human annotators, with a target Cohen's kappa of at least **0.6**.

**These are project goals, not reported experimental results.**

## Results and Findings

The completed experimental results are not included in the project documents used to prepare this README.

The baseline and Verifier ablation were developed to investigate the following questions:

1. How does the multi-agent approach compare with a baseline pipeline?
2. How does removing the Verifier affect the factual faithfulness of generated explanations?
3. What trade-offs emerge between readability and faithfulness?

Quantitative findings, experimental tables, and visualizations should be added from the team's actual evaluation outputs.

## Project Setup and Reproduction

The original team repository contains the project implementation and an experimental Streamlit pipeline visualizer.

For setup instructions, see:

- [Original FaithfulMed Repository](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations)
- [Streamlit Setup and Demo Guide](https://github.com/Break-Through-Tech/Google-2E-faithfulmed-a-multi-agent-system-for-faithful-patient-friendly-medical-explanations/blob/main/DEMO.md)

The demo guide covers dependencies, API key configuration, a prepared Chroma database, and platform-specific commands.

The original team README notes that the Streamlit visualizer is an experimental prototype and should not be used for medical advice.

Only fictional or approved de-identified medical notes should be submitted. Text entered into the visualizer is sent to the configured model provider.

## Future Work

Potential directions identified by the project include:

- Further calibrating the Verifier against human-annotated faithfulness labels.
- Expanding ablation studies to investigate the contributions of other agents.
- Comparing Gemini, Gemma, and an additional open model.
- Analyzing hallucination patterns across different types of medical information.
- Investigating the relationship between readability and factual faithfulness.
- Exploring multilingual medical explanations.
- Improving transparency through evidence attribution and agent-level traces.

## Skills and Experience

My work on FaithfulMed provided practical experience in:

- Exploratory Data Analysis
- Generative AI and Large Language Models
- Multi-Agent Systems
- AI Agent Development
- Baseline Pipeline Development
- Ablation Studies
- Experimental Design
- AI

