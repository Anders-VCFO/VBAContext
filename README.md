# Context OS Quickstart

**Build a context operating system where your AI never forgets what you've taught it.**

A context operating system centralizes your scatter documents, transcripts and other working context sources into an living source of truth that eliminates the endless context switching and constantly having to tell your AI the same thing over and over. 

Instead, you get a compounding intelligence asset that gets smarter the more you use it, since once you solve a problem with your context OS you can save it and reuse it forever. 

## The Problem

Every new AI session starts from scratch. You re-explain your business, re-teach your preferences, re-provide context. Knowledge doesn't compound.

## The Solution

A Context OS structures your knowledge so AI:
- Remembers everything across sessions
- Links concepts together (graph, not files)
- Compounds intelligence over time

## Get Started

```bash
git clone https://github.com/Rockhind/context-quickstart.git
cd context-quickstart
```

Open in Cursor (or any editor with Claude Code), then run:

```
/quickstart
```

In 10 minutes you'll have:
- Structured knowledge base
- Navigation guide for AI
- Your first processed content
- Working system that persists

## What's Included

### Commands
- `/quickstart` - Guided setup (10 min)
- `/ingest` - Process content into knowledge
- `/graph-health` - Check system health

### Templates
- CLAUDE.md starter
- Taxonomy configuration
- Ontology rules
- Knowledge node format

### Skill
- `context-os-basics` - Foundation patterns

## How It Works

**Two Layers:**

1. **Atomic Knowledge** (knowledge_base/)
   - Individual concepts with metadata
   - Linked via [[wiki-links]]
   - Lifecycle: emergent → validated → canonical

2. **Operational Docs** (00_foundation/)
   - Strategic documents that compose atomic concepts
   - Positioning, messaging, processes

**Constitutional Docs:**
- `taxonomy.yaml` - Your blessed tags
- `ontology.yaml` - How concepts relate

## Requirements
- VSCode or Cursor IDE with Foam extension installed
- Claude Code CLI or Claude Code extension
- Obsidian Notes or Google Sheets for generating markdown source content
- Claude Pro subscription ($20/month), recommend one of the $100 or $200 a month subscriptions for initial setup as we'll be burning a bit of tokens quickly to get going and play with the system. Also if you want to setup multiple contexts

## Learn More

https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents

https://platform.claude.com/cookbook/tool-use-memory-cookbook

**Original Bootstrap Memory and Context System:**
- Author: Jacob Dietle
- GitHub: https://github.com/jacob-dietle/gtm-context-os-quickstart
- YouTube Demo: https://youtu.be/acI1zRtpgEc
- Website: https://taste.systems
- Sales Copy: For advanced patterns (multi-agent orchestration, team governance, enterprise taxonomy).
