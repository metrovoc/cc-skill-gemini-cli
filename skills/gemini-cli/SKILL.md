---
name: gemini-cli
description: "Use Gemini CLI when processing images, PDFs, large files, needing 1M+ token context, or requiring Gemini's strong reasoning and fine-grained domain knowledge.
allowed-tools: Bash, Read
---

# Gemini CLI

**Note**:

- Gemini's knowledge cutoff means it may struggle with very recent events or factual details. For latest information, prefer web search.

- Always max timeout limit because it can take quite long time for responses. If it still times out, use exponential backoff when waiting(`sleep`) for bash output.

- Gemini might return empty response sometimes, try explicitly ask it to continue.

## New Conversation (clears context and creates new session)

Gemini won't remember any previous context! Use this tool only to start a new conversation.

```bash
gemini "$(cat << 'EOF'
hello
EOF
)"
```

## List sessions

Use to check session id for continue from session.

```bash
gemini --list-sessions
```

## Continue from session

Use to continue conversation.

```bash
gemini -r 1 -p "$(cat << 'EOF'
follow up
EOF
)"
```

## File Reference

```bash
gemini "$(cat << 'EOF'
@file.ts explain this code
EOF
)"
```
