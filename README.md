# Context OS Quickstart

**Build a knowledge system where your AI never forgets what you've taught it.**

Instead of re-explaining your business, preferences, and context every session, you build a structured knowledge base that compounds over time. Solve a problem once, save it, reuse it forever.

---

## Quick Start

```bash
git clone https://github.com/Rockhind/context-quickstart.git my-context-os
cd my-context-os
```

Open the folder in Cursor (or VS Code with Claude Code), then run:

```
/quickstart
```

The guide will walk you through setup in about 10 minutes.

---

## How This System Works

This plugin gives Claude the ability to build and maintain a structured knowledge base for you. Here's how the pieces fit together:

### The CLAUDE.md File

**What it is:** A navigation guide that Claude reads at the start of every session.

**How it works:** When you open a project folder, Claude automatically looks for a `CLAUDE.md` file in the root. This file tells Claude:
- What this project is about
- Where to find important files
- What rules to follow
- How knowledge is organized

Think of it as the "instruction manual" you give to Claude so it understands your system without you having to explain it every time.

**You'll create one during `/quickstart`** - it gets customized for your specific use case.

---

### The .claude Folder

This hidden folder contains the "superpowers" - custom commands, agents, and skills that extend what Claude can do.

```
.claude/
├── commands/       # Slash commands you can run
│   ├── quickstart.md    → /quickstart
│   ├── ingest.md        → /ingest
│   └── graph-health.md  → /graph-health
├── agents/         # Specialized helpers
│   └── ingestion-agent.md
└── skills/         # Reusable knowledge patterns
    └── context-os-basics/
```

**Commands** are actions you trigger with `/command-name`. They're like macros that tell Claude exactly how to handle specific tasks.

**Agents** are specialized helpers that commands can call. The ingestion agent knows how to transform raw content into structured knowledge nodes.

**Skills** are reusable knowledge patterns Claude can reference. The `context-os-basics` skill teaches Claude the foundational patterns for building context systems.

---

### The ingest Folder

**What it is:** Your inbox for raw content.

**How it works:** Drop files here that you want Claude to process:
- Meeting transcripts
- Documents and specs
- Notes and emails
- Any content you want to add to your knowledge base

Then run `/ingest` and Claude will transform them into structured knowledge nodes.

**Included:** A `sample-transcript.md` file so you can test the system.

---

### The templates Folder

**What it is:** Starter files used during setup.

**What's inside:**
- `CLAUDE_MD_STARTER.md` - Template for your navigation guide
- `taxonomy_starter.yaml` - Tag structure for organizing knowledge
- `ontology_starter.yaml` - Rules for how concepts relate
- `node_template.md` - Format for knowledge nodes

**Note:** After `/quickstart` completes, these get moved to their proper locations and this folder is deleted.

---

## Using the Commands

### /quickstart

**When to use:** Once, to set up your context OS.

**What it does:**
1. Asks what your system is for (Sales, Product, Research, or custom)
2. Creates the folder structure
3. Generates your CLAUDE.md navigation guide
4. Sets up taxonomy and ontology rules
5. Processes your first piece of content
6. Verifies everything works

### /ingest

**When to use:** Whenever you have new content to add.

**What it does:**
1. Reads the file(s) you specify (or everything in the `ingest/` folder)
2. Extracts key concepts and insights
3. Creates structured knowledge nodes with metadata
4. Links them to existing knowledge
5. Saves them to the appropriate domain folder

**Example:**
```
/ingest meeting-notes.md
```

### /graph-health

**When to use:** Periodically, to check your system's health.

**What it does:**
1. Scans your knowledge base for issues
2. Checks for broken links between nodes
3. Identifies orphaned content
4. Validates taxonomy compliance
5. Suggests improvements

---

## After Setup: Your Folder Structure

Once `/quickstart` completes, your context OS will look like this:

```
my-context-os/
├── CLAUDE.md              # Navigation guide (Claude reads this first)
├── knowledge_base/        # Layer 1: Atomic knowledge
│   ├── technical/         # Domain-specific folders
│   ├── business/          # (varies based on your choice)
│   └── methodology/
├── 00_foundation/         # Layer 2: Strategic documents
│   ├── positioning/
│   └── _synthesis/
├── _system/               # Configuration
│   └── knowledge_graph/
│       ├── taxonomy.yaml  # Your tag structure
│       ├── ontology.yaml  # Relationship rules
│       └── node_template.md
├── ingest/                # Drop raw content here
└── .claude/               # Commands and agents
```

---

## Requirements

- **Editor:** VS Code or Cursor with Claude Code extension
- **Subscription:** Claude Pro ($20/month minimum)
  - Recommend $100-200/month plans for initial setup (uses more tokens)
- **Optional:** Foam extension for VS Code (enables [[wiki-links]])

---

## Learn More

**Anthropic Resources:**
- [Effective Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- [Tool Use Memory Cookbook](https://platform.claude.com/cookbook/tool-use-memory-cookbook)

**Original System:**
- Author: Jacob Dietle
- [GitHub Repository](https://github.com/jacob-dietle/gtm-context-os-quickstart)
- [YouTube Demo](https://youtu.be/acI1zRtpgEc)
- [Website](https://taste.systems)

---

## Troubleshooting

**Claude doesn't recognize the commands:**
- Make sure you're in the project folder
- Check that the `.claude/commands/` folder exists
- Try restarting Claude Code

**Ingestion creates empty or wrong nodes:**
- Check that your taxonomy.yaml has the right domains
- Run `/graph-health` to diagnose issues

**Knowledge isn't persisting between sessions:**
- Verify CLAUDE.md exists in the root folder
- Check that knowledge nodes were saved to `knowledge_base/`
