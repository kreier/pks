# pks
Personal Knowledge System - a local second brain.

## Structure

This system is designed to have 3 buckets and 2 stages plus an interactive llm interface. Here is what it looks like:

```
                    PERSONAL KNOWLEDGE SYSTEM (PKS)
                    ==============================

  External sources
  ┌──────────┬───────────┬──────────┬──────────────┐
  │  Emails  │ WhatsApp │   LLMs   │ Documents... │
  └────┬─────┴─────┬─────┴────┬─────┴──────┬───────┘
       └───────────┴──────────┴────────────┘
                         │
                         ▼
              ┌────────────────────┐
              │     RAW VAULT      │
              │ Original files     │
              │ Immutable sources  │
              └─────────┬──────────┘
                        │
                        ▼
              ┌─────────────────────┐
              │       CURATOR       │
              │ Deterministic       │
              │ parsing & validation│
              │ identity resolution │
              │ metadata & linking  │
              └─────────┬───────────┘
                        │
                        ▼
              ┌────────────────────┐
              │  CURATED ARCHIVE   │
              │ Normalized records │
              │ Known relationships│
              │ Counts & statistics│
              │ Source references  │
              └─────────┬──────────┘
                        │
                        ▼
              ┌────────────────────┐
              │    SYNTHESIZER     │◄──── Synthesis Playbook
              │ AI / LLM inference │◄──── Workboard
              │ Summaries & topics │◄──── Previous findings
              │ Insights & search  │
              └─────────┬──────────┘
                        │
                        ▼
              ┌────────────────────┐
              │   KNOWLEDGE BASE   │
              │ Summaries          │
              │ Topics & insights  │
              │ Inferences         │
              │ Semantic index     │
              └─────────┬──────────┘
                        │
                        ▼
              ┌────────────────────┐
              │     COMPANION      │
              │ Conversational LLM │
              │ Retrieval & tools  │
              └─────────┬──────────┘
                        │
                        ▼
                 Chat / Telegram
```

## 3 Buckets

### 1. Raw Vault

> Bucket 1 · Immutable source material

Stores imported emails, WhatsApp and other social messages, LLM transcripts, documents, images, and other files. Original content is preserved so it can be processed again.

### 2. Curated Archive

> Bucket 2 · Deterministic, normalized data

The output of the **Curator**: parsed records, normalized identities, timestamps, counts, relationships, metadata, and links to source files. This is the reliable, queryable foundation for everything downstream.

### 3. Knowledge Base

> Bucket 3 · AI-enriched knowledge

The output of the **Synthesizer**: summaries, topics, recurring themes, inferred relationships, open questions, insights, and semantic indexes. AI-generated claims remain distinguishable from verified facts.

# Personal Knowledge System (PKS)

A personal knowledge system that transforms raw personal data into structured, interconnected, AI-enriched knowledge that can be explored through a conversational interface.

## Overview

The Personal Knowledge System (PKS) collects information from multiple sources, processes it through a deterministic curation pipeline, enriches it with AI-generated knowledge, and makes it accessible through a conversational assistant.

The system is built around three data buckets and three actors:

- **Raw Vault:** Original, imported source material.
- **Curated Archive:** Deterministically parsed, normalized, and interconnected records.
- **Knowledge Base:** AI-enriched summaries, topics, relationships, and insights.

The processing actors are the **Curator**, the **Synthesizer**, and the **Companion**.

## Architecture

```text
Sources
  │
  ▼
┌──────────────────────┐
│      Raw Vault       │
│  Original materials  │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│       Curator        │
│ Deterministic parser │
│ Normalize & link     │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   Curated Archive    │
│ Structured records   │
│ Verified metadata     │
│ Identities & counts  │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐       ┌────────────────────┐
│     Synthesizer      │◄──────│ Synthesis Playbook │
│    AI / LLM engine   │◄──────│ Workboard          │
└──────────┬───────────┘       └────────────────────┘
           │
           ▼
┌──────────────────────┐
│    Knowledge Base    │
│ Summaries & topics   │
│ Inferences & insights│
│ Semantic retrieval   │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│      Companion       │
│ Conversational access│
└──────────┬───────────┘
           │
           ▼
     Chat / Telegram
```

## Components

### 1. Raw Vault

The Raw Vault stores original data imported from different sources, including:

- Emails and email attachments.
- WhatsApp and other messaging platforms.
- Social media posts and interactions.
- Transcripts of conversations with LLMs.
- Documents, notes, and other personal files.

Original files are preserved so that data can be reprocessed when parsers, rules, or models change.

### 2. Curator

The Curator is a deterministic processing engine. Given the same input data and configuration, it should produce the same normalized output.

Its responsibilities include:

- Parsing files and extracting records.
- Counting messages, words, and other measurable attributes.
- Normalizing timestamps, names, and email addresses.
- Resolving identities across different data sources.
- Linking conversations, people, and related records.
- Applying configured inclusion and exclusion rules.
- Validating records and reporting processing errors.
- Maintaining provenance links to original source material.

Curator behavior is controlled by configuration files, including identity mappings, filters, and source-specific processing rules.

The Curator does not infer meaning from conversations. It establishes a reliable, structured foundation for subsequent analysis.

### 3. Curated Archive

The Curated Archive contains the normalized output of the Curator.

It provides a queryable source of truth for measurable facts, including message counts, interaction histories, timestamps, known identities, and relationships between records.

Every normalized record should retain a reference to its original source whenever possible.

### 4. Synthesizer

The Synthesizer is an AI-powered processing engine that transforms curated records into useful knowledge.

Its responsibilities include:

- Generating summaries of conversations and topics.
- Identifying recurring themes and interests.
- Discovering connections across different sources.
- Extracting relevant facts and contextual information.
- Developing insights and identifying unresolved questions.
- Maintaining an index for semantic retrieval.
- Revisiting earlier conclusions when new information becomes available.

The Synthesizer uses a persistent **Synthesis Playbook** to define its objectives, methods, output formats, and quality requirements.

A **Workboard** tracks processing progress, pending tasks, open questions, and findings that require further investigation. A **Synthesis Log** records the history of processing runs and changes.

AI-generated interpretations must remain distinguishable from directly observed facts. Important claims should include references to supporting source records and indicate uncertainty where appropriate.

### 5. Knowledge Base

The Knowledge Base contains the AI-enriched output of the Synthesizer.

It may include:

- People and their known relationships.
- Summaries of conversations and correspondence.
- Topics, interests, and recurring themes.
- Cross-source connections and contextual information.
- Inferences, insights, and open questions.
- Semantic indexes for retrieval.

The Knowledge Base is designed for efficient retrieval, not as a replacement for the original source data or the Curated Archive.

### 6. Companion

The Companion is the conversational interface to the PKS.

It accepts natural-language questions, retrieves relevant information from the Knowledge Base, and queries the Curated Archive when exact data is required.

Examples:

- How many emails have I exchanged with Mike?
- How many WhatsApp messages do we have?
- Which email accounts have I used to communicate with him?
- What topics do we discuss most frequently?
- What did we discuss about a particular project?
- Which people, conversations, and documents are connected to this topic?

The Companion combines retrieval, deterministic queries, and LLM reasoning to provide answers grounded in the available data.

## Design principles

1. **Preserve the source:** Never make AI-generated summaries the only surviving copy of important information.
2. **Separate facts from interpretations:** Exact counts and normalized metadata belong to the deterministic layer; inferred meaning belongs to the AI layer.
3. **Maintain provenance:** Make it possible to trace derived knowledge back to its source records.
4. **Make processing reproducible:** Version configurations, processing rules, and AI instructions.
5. **Support incremental updates:** Process new or changed data without unnecessarily rebuilding everything.
6. **Keep the system inspectable:** Store structured outputs, processing logs, and AI-generated knowledge in accessible formats.
7. **Protect personal data:** Keep private source material, credentials, and personal knowledge separate from public source code.

## Initial development goals

- Define the data model and storage layout for all three buckets.
- Implement the deterministic Curator for an initial set of source formats.
- Introduce configurable identity resolution and filtering.
- Add provenance, validation, and processing statistics.
- Implement the Synthesizer with a versioned Playbook and persistent Workboard.
- Generate source-linked summaries and topic indexes.
- Build the Companion with natural-language retrieval and exact database queries.
- Add automated tests and document deployment and backup procedures.

## Long-term vision

The PKS should become a continuously maintained, searchable representation of personal knowledge across communication channels and documents.

It should combine the reliability of deterministic data processing with the flexibility of AI-assisted interpretation, while preserving the ability to inspect, verify, and revisit every important conclusion.
