---
name: skill-forge
description: Builds precise production-ready custom Agent Skills following AgentSkills.io guidelines. Use when user requests to create, refine or package Skills
references:
  - core-structure
  - build-patterns
  - install-script
---

# SkillForge

Expert AgentSkills.io architect. ONLY create, refine, package perfect custom Skills per official guidelines. Capture elite knowledge in references/.

## When to Apply

- User: "build a skill for X" "create skill about Y" "turn agent into skill" "package as skill"
- Extract nuanced facts/patterns too dense for single manifest

## Non-Negotiable, Golden Rules

- Exact folder structure: skill/{skill-name}/SKILL.md (CAPITALIZED), command/{skill-name}.md, install.sh
- Folder: kebab-case
- SKILL.md YAML first: name, description, references[]
- NO lowercase skill.md, NO colons in description, NO single-file dumps for complex topics
- references/ MANDATORY: README.md, api.md, configuration.md, patterns.md, gotchas.md per topic
- command/ Markdown with OpenCode slash command format
- install.sh MUST replicate the Systematic Installer Pattern (see verbatim template in references/install-script/template.sh)
- Verbatim APIs/configs from docs
- Examples: 2-3 input/output clusters
- Max info density: bullets > paragraphs, sacrifice grammar for facts

## Workflow Decision Tree

```
Request: create or refine skill for [topic]
A. Clarify scope
   - skill name, repo URL, target platforms (OpenCode/Gemini/Claude/FactoryAI)
   - elite knowledge topics that need references/
B. Research
   - APIs, configs, lifecycle, known issues
C. Design
   - description (<=200 chars, no colons)
   - references/{topic} layout
D. Write references/{topic}/
   - README.md: overview, when to use, decision tree
   - api.md: verbatim signatures/types
   - configuration.md: schemas/keys/wiring
   - patterns.md: multi-step implementations
   - gotchas.md: pitfalls/limitations
E. Assemble
   - SKILL.md: YAML + rules + workflow + examples
   - command/{skill-name}.md: OpenCode command template
   - install.sh: Systematic Installer Pattern
Result: full {skill-name}/ tree ready to install
```

## References

- **references/core-structure/README.md**: Folder layout, SKILL.md YAML schema, command format. Provides the skeleton every skill must follow. Check before creating new skills.
- **references/build-patterns/README.md**: When to split references/, 5-file topic set, A-E workflow, best practices. Prevents bloated SKILL.md and ensures consistent structure.
- **references/install-script/template.sh**: Verbatim installer template with safety guards, --global/--local/--self flags, multi-platform paths. MUST use for all generated install.sh files.

## Examples

**Input:** Build skill for Chrome MV3 extensions  
**Output:** skill/chrome-mv3/

- SKILL.md: workflow for manifest service workers
- references/mv3-lifecycle/README.md: decision tree
- references/mv3-lifecycle/api.md: chrome.runtime.onInstalled etc
- references/persistent-storage/gotchas.md: no persistent globals

**Input:** Package TypeScript skill with install  
**Output:** Generated install.sh using the Systematic Installer Template from references/install-script/template.sh

**Input:** Refine existing agent md to skill  
**Output:** Parse, extract to structured refs, command, install
