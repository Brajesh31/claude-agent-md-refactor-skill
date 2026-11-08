# claude-agent-md-refactor-skill

A Claude Code skill for refactoring large agent instruction files into concise root guidance and focused linked documents using progressive disclosure.

## Overview

Agent instruction files such as `CLAUDE.md` and `AGENTS.md` can grow into large documents that mix project essentials, testing rules, architecture details, coding conventions, and temporary notes.

This skill helps identify contradictions, retain universal instructions in the root file, move specialized guidance into focused documents, and remove rules that are redundant or too vague to be useful.

## Main Capabilities

- Identify contradictory instructions.
- Separate universal rules from task-specific guidance.
- Group related instructions into logical topics.
- Create a concise root instruction file.
- Split detailed guidance into linked documents.
- Identify outdated or redundant rules.
- Verify links and file structure.
- Preserve important project-specific constraints.

## When to Use It

Use this skill when:

- A root agent instruction file has become too long.
- Instructions mix unrelated topics.
- The same rules are repeated in multiple files.
- Conflicting conventions have accumulated.
- A project needs a more maintainable instruction structure.
- You want to reduce unnecessary context loading.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-agent-md-refactor-skill.git ~/.claude/skills/agent-md-refactor
```

## Usage

Invoke the skill when reorganizing agent instructions:

```text
/agent-md-refactor
```

Provide the project root, relevant instruction files, and any constraints on what must be preserved.

## Five-Phase Refactoring Workflow

1. **Find contradictions:** Identify conflicting rules and resolve them before restructuring.
2. **Identify essentials:** Keep only information that applies to nearly every task in the root file.
3. **Group the rest:** Organize specialized guidance into focused topics.
4. **Create the file structure:** Generate linked documents with clear names and shallow hierarchy.
5. **Flag for deletion:** Identify redundant, vague, outdated, or default-behavior instructions.

## Suggested Structure

```text
project-root/
├── CLAUDE.md
└── .claude/
    └── instructions/
        ├── architecture.md
        ├── testing.md
        ├── code-style.md
        ├── frontend.md
        └── deployment.md
```

Adapt the structure to the project. Avoid creating many tiny files that make navigation harder.

## What Belongs in the Root File

- One-sentence project description.
- Non-standard package manager or build commands.
- Critical project-wide constraints.
- Universal rules that apply to nearly every task.
- Links to specialized instruction files.

Detailed framework conventions, test procedures, deployment rules, and domain-specific workflows usually belong in separate documents.

## Validation Checklist

- Root file contains only universal guidance.
- Important project-specific rules are preserved.
- Contradictions have been resolved.
- Links point to existing files.
- Specialized files are logically grouped.
- Instructions are specific and actionable.
- Redundant defaults are removed.
- Representative tasks still work with the new structure.

## Repository Contents

- `SKILL.md`: Main refactoring workflow and decision rules.
- `README.md`: Progressive disclosure strategy and validation checklist.

## Practical Principle

Refactoring instructions is not an excuse to delete useful context. Keep every rule that materially changes agent behavior, but move it to the right place and remove duplication.
