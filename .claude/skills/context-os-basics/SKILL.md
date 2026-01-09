---
name: context-os-basics
description: Foundation patterns for building context operating systems
model: inherit
---

# Context OS Basics

## What is a Context OS?

A context operating system is a structured knowledge system where:
- AI compounds intelligence over time (never re-teach)
- Knowledge persists across sessions
- Concepts link to each other (graph, not files)
- Two layers separate reusable knowledge from operational docs

## The Two-Layer Architecture

### Layer 1: Atomic Knowledge Graph (knowledge_base/)

Individual reusable concepts:
- Technical knowledge
- Business insights
- Methodologies and patterns

Each node:
- Has structured frontmatter (metadata)
- Links to related concepts via [[wiki-links]]
- Follows lifecycle: emergent → validated → canonical

### Layer 2: Operational Documents (00_foundation/)

Strategic artifacts that COMPOSE Layer 1:
- Positioning documents
- Messaging frameworks
- Process documentation

Key principle: Operational docs REFERENCE atomic concepts, they don't redefine them.

## Constitutional Documents

### taxonomy.yaml

Defines blessed tags for your system:
- Domains (technical, business, methodology)
- Node types (concept, pattern, case-study)
- Status values (emergent, validated, canonical)
- Your custom topic library

Start small. Add tags only after 3+ nodes demonstrate need.

### ontology.yaml

Defines how concepts relate:
- Relationship types (enables, supports, implements)
- Linking requirements (minimum links per node)
- Quality thresholds

## Evidence-Based Attribution

Every claim needs a source:

- [VERIFIED: file:line] - Direct evidence
- [INFERRED: logic] - Deduced from evidence
- [UNVERIFIABLE] - Cannot confirm (be honest)

Quality standard: If you can't cite a source, don't claim it.

## The 4-Phase Framework (Summary)

1. **Reconnaissance** - Understand domain and requirements
2. **Architecture** - Design two-layer structure
3. **Construction** - Build knowledge graph and ops docs
4. **Validation** - Test and document system

## Key Anti-Patterns

### 1. One Continuous Thread
**Problem:** Single long conversation without writing to files
**Fix:** Write intermediate results to files, preserve attribution chains

### 2. Context Explosion
**Problem:** "Need to read all files to answer this"
**Fix:** Use synthesis docs (5% of content answers 95% of questions)

### 3. Vague Attribution
**Problem:** "Many customers want this" (no source)
**Fix:** Quantify everything: "14 of 166 (8.4%)" not "many"

## The 3-5 Sample Rule

Never automate without sampling first:
1. Run broad search
2. Sample 3-5 results with context
3. Validate patterns are accurate
4. Refine and scale

## Advanced Patterns (Not Covered Here)

For complex implementations:
- Chief of Staff orchestration
- Forcing functions and calibration
- Team governance patterns
- Enterprise taxonomy design
- Multi-agent coordination

These require customization for your specific context.
Learn more: https://taste.systems
