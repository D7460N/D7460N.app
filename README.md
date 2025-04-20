
# 🧠 D7460N Copilot Context

This repository contains the **canonical shared context** file for GitHub Copilot Agent Mode, used across all D7460N-based projects.

---

## ✅ Purpose

The file [`copilot-context.md`](./copilot-context.md) defines strict architectural and behavioral rules for Copilot to follow, ensuring:

- Consistent recommendations across environments
- Enforcement of D7460N project standards
- No framework dependencies
- Accessible, semantic, and declarative UI logic

---

## 🌐 How to Use It

In any GitHub Copilot Chat-enabled project (VS Code, desktop or vscode.dev):

1. Download or sync the file:
   ```bash
   curl -sSL https://copilot.d7460n.app/copilot-context.md -o copilot-context.md
   ```

2. In Copilot Chat, type:
   ```
   /remember copilot-context.md
   ```

This will load the canonical project rules into Copilot’s working memory.

---

## 🔒 Why This Matters

This file enforces:
- Zero-guess policy
- Native HTML/CSS-only UI logic
- Strict separation of concerns
- Scroll containment rules
- Role-based rendering
- PWA & CI/CD compatibility
- 508/WCAG-compliant design patterns

---

## 🌍 Hosted Access

This file is hosted at:
```
https://copilot.d7460n.app/copilot-context.md
```

Use that link directly in scripts or dev containers.

---

## 🛠️ Maintainer Note

If this file changes, update all connected repos by re-running the curl command above or using a CI pull task.
