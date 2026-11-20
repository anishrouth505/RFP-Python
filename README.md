# AI-Powered Requirements Extraction and Prompt Generation

## Overview

This repository provides an end-to-end AI-driven requirements engineering pipeline that transforms client requirement documents into structured development prompts using **AWS Textract** and **AWS Bedrock**.

The solution processes business requirement documents (BRDs), functional requirement documents (FRDs), system design documents, process flow diagrams, workflow charts, wireframes, and other project artifacts. It combines AWS Textract's document extraction capabilities with AWS Bedrock's multimodal foundation models to understand both textual and visual content, generating a comprehensive `prompt.md` file that can later be provided to **Claude** for automated application development.

---

## Key Features

### Document Ingestion & Extraction

- Supports PDFs, scanned documents, images, Word documents, and mixed-content files.
- Uses AWS Textract to extract:
  - Text
  - Tables
  - Forms
  - Key-value pairs
  - Document layout information

### Multimodal Requirement Analysis

Leverages AWS Bedrock foundation models to analyze:

- Business requirements
- Functional requirements
- Non-functional requirements
- Use cases
- User stories
- Acceptance criteria
- Domain terminology

#### Visual Content Analysis

AWS Bedrock analyzes visual artifacts within the requirement documents, including:

- Process flow diagrams
- Workflow charts
- Sequence diagrams
- Architecture diagrams
- System interaction diagrams
- UI wireframes
- Decision trees
- Process maps
- Data flow diagrams

The solution converts visual information into structured, machine-readable requirements, ensuring that critical business logic and workflows represented in diagrams are included in the final specification.

---

## Prompt Generation

Based on the extracted textual and visual requirements, the system creates a comprehensive `prompt.md` file containing:

- Project overview
- Business context
- Functional requirements
- Non-functional requirements
- Domain entities
- Business workflows
- User journeys
- Data models
- Integration requirements
- Technical constraints
- Acceptance criteria
- Development guidelines
- Implementation instructions

The generated prompt serves as a complete project blueprint and is optimized for AI-assisted software development.

---

## High-Level Workflow

```text
Client Requirement Documents
(PDFs, Images, Word Docs)
            │
            ▼
      AWS Textract
            │
            ▼
     Document Extraction
(Text, Tables, Forms, Layout)
            │
            ▼
       AWS Bedrock
            │
    ┌───────┴────────┐
    │                │
    ▼                ▼
Text Analysis   Diagram Analysis
    │                │
    └───────┬────────┘
            ▼
 Structured Requirement Model
            │
            ▼
      Prompt Builder
            │
            ▼
        prompt.md
            │
            ▼
          Claude
            │
            ▼
 Application Implementation
```

---

## Technology Stack

- Python 3.11+
- AWS Textract
- AWS Bedrock
- Anthropic Claude (via AWS Bedrock)
- Boto3
- Pydantic
- FastAPI
- Markdown Generation Engine

---

## Repository Objective

The primary objective of this project is to automate the conversion of unstructured client documentation into AI-consumable development specifications.

By combining:

- Intelligent document extraction
- Multimodal diagram understanding
- Requirement interpretation
- Prompt generation

the platform significantly reduces manual effort during requirement analysis and accelerates the software development lifecycle.

The generated `prompt.md` serves as a complete implementation blueprint that enables Claude to produce accurate, requirement-aligned applications while preserving the business intent captured in both textual and visual artifacts from the original client documentation.

---

## Expected Deliverables

### Input

- Business Requirement Documents (BRDs)
- Functional Requirement Documents (FRDs)
- Solution Design Documents
- Workflow Diagrams
- Architecture Diagrams
- Wireframes
- PDFs and Scanned Documents

### Output

#### prompt.md

A comprehensive AI-ready development specification containing:

- Business requirements
- Functional requirements
- Non-functional requirements
- Workflow definitions
- Domain entities
- Data models
- Integration requirements
- Technical constraints
- Acceptance criteria
- Detailed implementation instructions

This file serves as the primary input for Claude to generate the required application.

---

## Vision

Transform client documentation into executable software specifications by leveraging AWS AI services to understand both text and diagrams, ultimately enabling rapid application development through AI-powered code generation.
