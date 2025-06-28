# Universal AI Rules (.ai/ai-rules.yaml) Project

**One rules file for all your AI coding assistants** 🤖

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Project Status: Concept](https://img.shields.io/badge/Project%20Status-Concept-orange.svg)](https://github.com/Universal-AI-Rules)
[![Looking for Contributors](https://img.shields.io/badge/Looking%20for-Contributors-brightgreen.svg)](https://github.com/Universal-AI-Rules)

## The Problem We're Solving

Every AI coding tool uses its own format for rules and instructions:

- **GitHub Copilot**: `.github/copilot-instructions.md`
- **Claude (Anthropic)**: `CLAUDE.md` or `~/.claude/CLAUDE.md`
- **Cursor**: `.cursor/rules/` directory or legacy `.cursorrules`
- **Windsurf**: `.windsurf/rules/` directory
- **Cline**: `.clinerules/` directory
- **OpenAI Codex & Jules**: `AGENTS.md`
- **Aider**: `CONVENTIONS.md` or `.aider.conf.yml`
- **Sourcegraph Cody**: `.sourcegraph/memory.md`
- **And dozens more...**

This fragmentation leads to:
- 🔄 **Duplication of effort** - Same rules written multiple times
- ⚠️ **Inconsistency and drift** - Rules get out of sync across tools
- 🚧 **Onboarding friction** - New tools require creating yet another rules file
- 📝 **Maintenance overhead** - Updates must be replicated everywhere

## Our Proposed Solution

Universal AI Rules aims to provide a **single source of truth** for all your AI coding assistants:

- 📄 **Unified Format**: `.ai/ai-rules.yaml` - one file to rule them all
- 🔄 **Automatic Sync**: Generate tool-specific files from your master rules
- ✅ **Schema Validation**: Ensure your rules are properly formatted
- 🤝 **Standards-Based**: Open specification that anyone can adopt
- 🛠️ **CLI Tools**: Easy setup, sync, and maintenance
- 🔌 **Extensible**: Support for new AI tools as they emerge

## Vision: How It Would Work

> **⚠️ Note: This is currently a concept. The CLI and tools described below don't exist yet - we're looking for contributors to help build them!**

```bash
# Future CLI usage (not yet implemented)
npm install -g @universal-ai-rules/cli

# Initialize in your project
ai-rules init

# Sync to all supported tools
ai-rules sync

# Validate your rules
ai-rules validate
```

The vision is that your `.ai/ai-rules.yaml` would become the master source, and tool-specific files would be auto-generated:

```yaml
# .ai/ai-rules.yaml
version: "1.0"
project:
  name: "My Awesome Project"
  description: "A fintech application with microservices architecture"

rules:
  - name: "Language and Framework"
    content: "Use TypeScript 5.8+ and Next.js 15.3+ for frontend"
    applies_to: ["frontend", "typescript"]
  
  - name: "Security Guidelines"
    content: "Always validate input for SQL injection. Never hardcode secrets."
    applies_to: ["security", "backend"]

tools:
  enabled: ["cursor", "claude", "copilot", "windsurf"]
  cursor:
    output_path: ".cursor/rules/"
  claude:
    output_path: "CLAUDE.md"
```

## Why AI Rule Files Matter

AI rule files serve as a **persistent knowledge base** for your AI coding assistants, providing:

### 🎯 **Consistency**
Every team member and AI tool gets the same guidance, leading to uniform code suggestions that match your project's standards.

### ⚡ **Reduced Overhead**
No more re-explaining context in every prompt. The AI already "knows" your setup, preferences, and constraints.

### 🔒 **Enhanced Security**
Centralize security guidelines to steer AI away from common vulnerabilities. Research shows well-crafted prompts significantly reduce security flaws in generated code.

### 🧠 **Project Context Memory**
Convey high-level context the AI might not infer from code alone - domain knowledge, architecture decisions, and business constraints.

## Planned AI Tool Support

| Tool | Status | Config File |
|------|--------|-------------|
| **GitHub Copilot** | 📋 Planned | `.github/copilot-instructions.md` |
| **Claude (Anthropic)** | 📋 Planned | `CLAUDE.md`, `CLAUDE.local.md` |
| **Cursor** | 📋 Planned | `.cursor/rules/*.md` |
| **Windsurf** | 📋 Planned | `.windsurf/rules/*.md` |
| **Cline** | 📋 Planned | `.clinerules/*.md` |
| **OpenAI Codex** | 📋 Planned | `AGENTS.md` |
| **Google Jules** | 📋 Planned | `AGENTS.md` |
| **Aider** | 📋 Planned | `CONVENTIONS.md` |
| **Sourcegraph Cody** | 📋 Planned | `.sourcegraph/memory.md` |
| **JetBrains AI** | 📋 Planned | `.junie/instructions.md` |

*Want to help implement support for these tools? We need contributors to build the adapters!*

## Project Structure

This is a monorepo containing multiple packages (currently empty repos - looking for contributors!):

```
Universal AI Rules/
├── 📦 ai-rules-spec/          # Core specification and schema (TODO)
├── 🛠️ ai-rules-cli/           # Command-line interface (TODO)
├── 🔌 ai-rules-adapters/      # Tool-specific adapters (TODO)
├── 🌐 universal-ai-rules-site/ # Documentation website (TODO)
└── ⭐ awesome-ai-rules/       # Curated examples and templates (TODO)
```

## Best Practices for Writing Rules

Based on analysis of successful AI rule implementations:

### ✅ **Do**
- Write clear, concise, actionable rules
- Use specific examples and exceptions
- Keep rules scoped and relevant to context
- Break complex guidelines into atomic rules
- Evolve rules over time based on AI feedback

### ❌ **Don't**
- Write overly long rules (keep under 500 lines total)
- Include irrelevant context that might confuse the AI
- Duplicate the same rule across multiple sections
- Use vague language - be specific about expectations

### 📝 **Example Structure**
```yaml
rules:
  - name: "Code Style"
    content: "Use Python 3.11+ with type hints. Prefer composition over inheritance."
    applies_to: ["python", "backend"]
    
  - name: "Security"
    content: "Use parameterized queries to prevent SQL injection. Store secrets in environment variables only."
    applies_to: ["security", "database"]
```

## Specification

The specification is still being developed. We plan to create detailed documentation covering:
- Schema definitions and validation rules
- File format specifications  
- Tool adapter requirements
- Extension mechanisms

*Want to help design the specification? Check out the [ai-rules-spec](./ai-rules-spec/) directory and contribute!*

## Get Involved

**This project needs YOU!** We're looking for contributors to help build the future of AI-assisted development:

- ⭐ **Star our repos** to show support for the concept
- 💡 **Share ideas** - what features would you want?
- 📝 **Help design the specification** - what should the YAML format look like?
- 🔧 **Build the CLI** - Node.js/TypeScript developers needed
- 🔌 **Create adapters** - help support your favorite AI tool
- 🐛 **Report issues** or suggest improvements
- 💬 **Join discussions** - let's figure this out together!

### Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## Roadmap

**Phase 1: Foundation** (Looking for contributors!)
- [ ] Define core specification (v1.0)
- [ ] Create basic CLI tool structure
- [ ] Implement YAML schema validation
- [ ] Build first few tool adapters (Cursor, Claude, Copilot)

**Phase 2: Core Features**
- [ ] Full CLI with sync functionality
- [ ] Support for all major AI tools
- [ ] Rule templates and examples
- [ ] Documentation website

**Phase 3: Advanced Features**
- [ ] VS Code extension for GUI management
- [ ] Team collaboration features
- [ ] Rule templates marketplace
- [ ] Advanced validation and linting
- [ ] Integration with popular frameworks

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

Special thanks to the AI coding community and the teams behind:
- GitHub Copilot for pioneering repository-specific instructions
- Anthropic Claude for demonstrating the power of persistent context
- Cursor, Windsurf, Cline, and other tools for advancing AI-assisted development
- The open source community for driving standardization efforts

---

> **Made with ❤️ by the Universal AI Rules community**  
> *One rules file to rule them all* 🤖 