---
name: gemini-cli
description: "Use Gemini CLI when processing images, PDFs, large files, needing 1M+ token context, or requiring Gemini's strong reasoning and fine-grained domain knowledge.
allowed-tools: Bash, Read
---

# Gemini CLI

**Caveat**: Gemini's knowledge cutoff means it may struggle with very recent events or factual details. For latest information, prefer web search.

**Note**: Always max timeout limit because it can take quite long time for responses. If it still times out, use exponential backoff when waiting(`sleep`) for bash output.

## New Conversation (clears context and creates new session)

Gemini won't remember any previous context. Use this tool to start a new conversation.

```bash
gemini "$(cat << 'EOF'
hi
EOF
)"
```

## Continue conversation from latest session

```bash
gemini -r latest -p "$(cat << 'EOF'
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

## List sessions

```bash
gemini --list-sessions
```

## Continue from session

```bash
gemini -r 1 -p "$(cat << 'EOF'
follow up
EOF
)"
```

## Delete session

```bash
gemini --delete-session 1
```
