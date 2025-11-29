# cc-skill-gemini-cli

A Claude Code skill that enables Claude to use Gemini CLI for tasks requiring large context windows, deep reasoning, or fine-grained domain knowledge.

## Purpose

Gemini offers 1M+ token context and strong multi-step reasoning capabilities. This skill allows Claude to delegate specific tasks to Gemini when beneficial:

- Processing large files or PDFs
- Tasks requiring 1M+ token context
- Complex reasoning chains
- Queries needing detailed domain knowledge

## Installation

### Prerequisites

Ensure [Gemini CLI](https://github.com/google-gemini/gemini-cli) is installed and configured.

### Install / Update

```bash
mkdir -p ~/.claude/skills/gemini-cli && \
curl -o ~/.claude/skills/gemini-cli/SKILL.md https://raw.githubusercontent.com/metrovoc/cc-skill-gemini-cli/main/skills/gemini-cli/SKILL.md
```
