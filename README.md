# Claude Skills

A collection of custom skills that extend Claude's capabilities with specialized workflows, methods, and domain knowledge.

## What Are Skills?

Skills are modular packages that transform Claude from a general-purpose assistant into a specialized collaborator. Each skill contains:

- **SKILL.md** — Core instructions and workflows
- **references/** — Documentation Claude loads as needed
- **assets/** — Templates, examples, and resources for output

## Repository Structure

```
claude-skills/
├── README.md
├── .gitignore
├── build.py              # Packages skills for Claude.ai
├── brainstorm/           # Each skill is a top-level folder
│   ├── SKILL.md
│   ├── references/
│   └── assets/
├── another-skill/
│   └── ...
└── dist/                 # Packaged .skill files (generated)
    └── brainstorm.skill
```

## Usage

### Option 1: Claude Code (CLI)

Claude Code reads skills directly from your filesystem. Reference them in your project's `CLAUDE.md`:

**If skills repo is inside your project:**
```markdown
# CLAUDE.md

## Skills
When brainstorming, read and follow `./claude-skills/brainstorm/SKILL.md`.
```

**If skills repo is standalone (recommended):**
```markdown
# CLAUDE.md

## Skills
When brainstorming, read and follow `/Users/robert/repos/claude-skills/brainstorm/SKILL.md`.
```

**Global access via ~/.claude/CLAUDE.md:**

Create `~/.claude/CLAUDE.md` to make skills available in all projects:
```markdown
# Global Claude Instructions

## Available Skills
- Brainstorming: Read `/Users/robert/repos/claude-skills/brainstorm/SKILL.md`
- [Other skills as you add them]
```

### Option 2: Claude.ai (Web/Mobile/Desktop)

The Claude.ai interface requires packaged `.skill` files.

**Build a single skill:**
```bash
python build.py brainstorm
```

**Build all skills:**
```bash
python build.py --all
```

**Output:** Packaged skills appear in `dist/` (e.g., `dist/brainstorm.skill`)

**To install:**
1. Open Claude.ai → Settings
2. Navigate to Skills (or Profile → Skills)
3. Upload the `.skill` file

## Creating New Skills

1. Create a new folder at the repo root:
   ```bash
   mkdir my-new-skill
   ```

2. Create the required `SKILL.md`:
   ```markdown
   ---
   name: my-new-skill
   description: What this skill does and when to use it. Be specific about triggers.
   ---

   # My New Skill

   [Instructions for Claude]
   ```

3. Add optional resources:
   - `references/` — Documentation to load as needed
   - `assets/` — Templates, examples, files for output

4. Package for Claude.ai:
   ```bash
   python build.py my-new-skill
   ```

## Skill Design Principles

1. **Concise is key** — Only include what Claude doesn't already know
2. **Progressive disclosure** — Core instructions in SKILL.md, details in references/
3. **Clear triggers** — The `description` field determines when the skill activates

## Available Skills

| Skill | Description |
|-------|-------------|
| `brainstorm` | Collaborative multi-session brainstorming with versioned documents, 25+ thinking methods, and decision tracking |

## Version Control Notes

- **Commit the source folders**, not the `.skill` files
- The `dist/` folder is gitignored by default
- Rebuild `.skill` files anytime with `build.py`

## License

Personal use. Modify freely.
