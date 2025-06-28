# Universal AI Rules

**One rules file for all your AI coding assistants** 🤖

## Problem
Every AI coding tool uses its own format:
- GitHub Copilot: `.github/copilot-instructions.md`
- Claude: `CLAUDE.md`
- Cursor: `.cursorrules`
- And dozens more...

## Solution
Universal AI Rules provides:
- 📄 **Single source of truth**: `.ai/ai-rules.yaml`
- 🔄 **Automatic sync**: Generate tool-specific files
- ✅ **Validation**: Schema-based validation
- 🤝 **Standards-based**: Open specification

## Quick Start
```bash
npm install -g @universal-ai-rules/cli
ai-rules init
ai-rules sync
