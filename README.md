# SkillForge

Standardized skill creation framework for [Agent Skills](https://AgentSkills.io). Inspired by the structure of [dmmulroy/cloudflare-skill](https://github.com/dmmulroy/cloudflare-skill), this skill provides a systematic approach to building, refining, and packaging custom Agent Skills with consistent structure and installation patterns.

## Purpose

- Create production-ready custom Agent Skills following official guidelines
- Standardize skill structure across platforms (OpenCode, Gemini CLI, Claude, FactoryAI Droid)
- Provide systematic installation patterns with safety guards
- Enable easy skill updates and maintenance

## Structure

```
skill-forge/
├── skill/skill-forge/
│   ├── SKILL.md          # Skill manifest and workflow
│   └── references/       # Documentation for skill creation
│       ├── core-structure/
│       ├── build-patterns/
│       └── install-script/
├── command/skill-forge.md # OpenCode slash command
└── install.sh            # Systematic installer
```

## Installation

```bash
# Global installation (default)
curl -fsSL https://raw.githubusercontent.com/AlcyoneLabs/skill-forge/main/install.sh | bash

# Local installation
curl -fsSL https://raw.githubusercontent.com/AlcyoneLabs/skill-forge/main/install.sh | bash -s -- --local

# Self-install (for development)
./install.sh --self --local
```

## Usage

Load the skill and use it to create, refine, or package custom Agent Skills.

If you use OpenCode, simply load the agent into context via the `/skill-forge` command.

The new skill created will contain a similar commands for your skill.

## Key Features

- **Standardized Structure**: Enforces consistent folder layout and naming conventions
- **Dynamic Multi-Skill Installer**:
    - Automatically scans `skill/` directory for available skills
    - Offers interactive toggle menu to select specific skills or "All"
    - Supports scanning and installing multiple skills from a single repo
    - Defaults to directory name if `PROJECT_NAME` is unset (fully generic)
- **Reference Documentation**: Built-in guides for skill creation patterns
- **Update Support**: Easy skill updates via `--update-skill` flag

## Inspiration

This project was greatly inspired by the structure and approach of [dmmulroy/cloudflare-skill](https://github.com/dmmulroy/cloudflare-skill), with the goal of creating a standardized framework for skill creation that provides nice ways to set up and update skills across different AI agent platforms.
