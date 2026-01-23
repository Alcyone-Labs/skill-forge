# Core Structure

## Folder Layout

skill-forge/
├── skills/
│ └���─ {skill-name}/
│ ├── SKILL.md # CAPITALIZED manifest router
│ ├── README.md # Skill overview
│ └── references/ # {topic}/[README api config patterns gotchas].md
├── commands/
│ └── {skill-name}.md # OpenCode slash command
└── install.sh # Global installer for all skills in this folder

## SKILL.md YAML

```
---
name: kebab-case
description: <=200 chars NO colons what-when
references:
  - core-structure
  - build-patterns
  - install-script
---
```

Body: When Apply | Rules | Workflow Tree | 2-3 Examples

## Command Format

`commands/{skill-name}.md`

```
---
description: Load skill guide tasks
---

If $ARGUMENTS --update-skill: run install.sh --local/global; stop

skill({ name: '{skill-name}' })

Task type from $ARGUMENTS. Read relevant references/. Execute.
```
