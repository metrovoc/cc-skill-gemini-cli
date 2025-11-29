---
name: gemini-cli
description: "Use Gemini CLI for large context tasks, deep reasoning, and fine-grained knowledge queries. Activate when processing large files, PDFs, needing 1M+ token context, or requiring Gemini's strong reasoning and detailed domain knowledge. Note: Gemini's knowledge cutoff may lag behind on very recent information."
allowed-tools: Bash, Read
---

# Gemini CLI

Gemini offers 1M+ token context, strong multi-step reasoning, and fine-grained domain knowledge. Use it for large file analysis, complex reasoning chains, or when detailed factual knowledge is needed.

**Caveat**: Gemini's knowledge cutoff means it may struggle with very recent events or factual details. For latest information, prefer web search.

**Note**: Always max timeout limit because it can take quite long time for responses. If it still times out, use exponential backoff when waiting(`sleep`) for bash output.

## Basic Usage

```bash
gemini "$(cat << 'EOF'
your prompt here
EOF
)"
```

## File Reference

```bash
gemini "$(cat << 'EOF'
@filepath.ts explain this code
EOF
)"
```

## Session Management

```bash
# List sessions
gemini --list-sessions

# New conversation (auto-saved)
gemini "$(cat << 'EOF'
Remember: secret is APPLE
EOF
)"

# Continue conversation
gemini -r latest -p "$(cat << 'EOF'
What was the secret?
EOF
)"

# Delete session
gemini --delete-session 1
```
