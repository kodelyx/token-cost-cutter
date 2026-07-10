# Token Cost Cutter (TCC)

Auto-optimize terminal outputs for Claude Code instantly. Save 60–90% tokens with zero manual setup.

🌐 **Website**: [https://tcc.kodelyx.in](https://tcc.kodelyx.in)

---

## ⚡ Quick Start

### 1. Install TCC globally
```bash
# Using Bun
bun install -g token-cost-cutter

# Using NPM
npm install -g token-cost-cutter
```

### 2. Connect to Claude Code
```bash
tcc init -g
```
*Restart Claude Code after running the hook command.*

---

## 🛠️ How It Works

1. **Auto-Intercept**: Runs silently in the background when Claude runs shell commands (tests, diffs, logs, etc.).
2. **Snip & Summarize**: Filters out ANSI progress bars, deduplicates logs, and strips empty lines.
3. **Save Tokens**: Delivers a highly compact, optimized summary to Claude, reducing token costs by up to 90%.

---

## 🧠 Accuracy & Reliability (Does it affect Claude's behavior?)

We understand that Claude Code users worry about losing critical details. Here is how TCC ensures **100% reliability** with zero accuracy loss:

* **Zero Loss of Crucial Details**: TCC only strips raw structural noise (like thousands of unchanged files in `git status`, progress bars, or repetitive logs). Critical compile errors, test failures, and line numbers are always preserved intact.
* **Actually Improves Accuracy**: LLMs can lose focus when bombarded with massive, noisy terminal logs (the "needle in a haystack" problem). By sending clean summaries, Claude pinpoints and fixes bugs faster and more accurately.
* **Fail-Safe Tee Mode**: If a command fails, TCC automatically writes the full, unfiltered raw output to a temporary file. If Claude needs to inspect the complete trace, it can access this file directly, ensuring zero loss of troubleshooting capability.
