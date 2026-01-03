# Claude Skills

A collection of custom skills that extend Claude's capabilities with specialized workflows, methods, and domain knowledge.

📚 **[View Full Documentation](https://robertguss.github.io/claude-skills/)**

## Quick Start

### Claude Code (CLI)

```markdown
# CLAUDE.md

When brainstorming, read and follow /path/to/claude-skills/brainstorm/SKILL.md.
```

### Claude.ai (Web/Mobile/Desktop)

```bash
python build.py brainstorm
# Upload dist/brainstorm.skill to Claude.ai → Settings → Skills
```

## Available Skills

| Category | Skills | Description |
|----------|--------|-------------|
| **Standalone** | [brainstorm](brainstorm/) | Multi-session ideation with 25+ thinking methods |
| **Book Factory** | 6 skills | Full pipeline from idea to chapter architecture |
| **Ebook Factory** | 2 skills | Focused ebook creation pipeline |
| **Writing** | 2 skills | Voice capture and ghost writing |

## Documentation

- [Getting Started](https://robertguss.github.io/claude-skills/getting-started/)
- [All Skills](https://robertguss.github.io/claude-skills/skills/)
- [Developer Guide](https://robertguss.github.io/claude-skills/developer-guide/)

## Local Documentation

```bash
pip install -r requirements-docs.txt
mkdocs serve
# Visit http://localhost:8000
```

## License

Personal use. Modify freely.
