# ui-action-designer

**Figma to HTML pipeline: extract design systems, author PRDs, generate actions and tasks, output 4-direction design proposals.**

## Prerequisites

- **Claude Cowork or Claude Code** environment
- **Figma** access — recommended for design system extraction

## Goal

ui-action-designer bridges the design-to-development disconnect through an 8-phase pipeline: extract design systems, enable PRD authoring, extract actions and tasks, apply SHE filter, inject platform patterns, generate 4-direction proposals, and validate PRD consistency.

## When & How to Use

Deploy when you have a Figma design or concept that needs to become actionable specification and code. Pipeline: Design → DS extraction → PRD linking → Action-Task extraction → SHE filter → Knowledge injection → 4-direction proposals → HTML output.

## Use Cases

| Scenario | Prompt | What Happens |
|---|---|---|
| Design handoff | `"Turn Figma design into PRD and 4 implementation directions"` | DS extraction→PRD→Actions/Tasks→SHE→4 proposals as HTML + consistency check |
| PRD update | `"Update PRD based on new design direction"` | Design delta→PRD update→re-extract tasks→4-direction proposals→validate |
| PRD from scratch | `"Author simple PRD for this component"` | Factor selection→PRD→DS extraction→4 proposals→HTML prototype |

## Key Features

- 8-phase pipeline: Input → DS extraction → Analysis → Action-Task → SHE → Knowledge → 4 proposals → HTML
- PRD authoring with factor selection (required/optional/nice-to-have)
- Action-Task hierarchy: Actions (functions) > Tasks (steps)
- SHE filter: Simple→Hide→Embody
- iOS/Material Design 3 pattern injection
- 4-direction proposals: Pragmatic, Elegant, Minimal, Feature-rich
- PRD consistency verification

## Works With

- **[human-skill](https://github.com/jasonnamii/human-skill)** — informs user behavior patterns for PRD design
- **[hit-skill](https://github.com/jasonnamii/hit-skill)** — propagation and impact patterns for consumer features

## Installation

```bash
git clone https://github.com/jasonnamii/ui-action-designer.git ~/.claude/skills/ui-action-designer
```

## Update

```bash
cd ~/.claude/skills/ui-action-designer && git pull
```

Skills placed in `~/.claude/skills/` are automatically available in Claude Code and Cowork sessions.

## Part of Cowork Skills

This is one of 25+ custom skills. See the full catalog: [github.com/jasonnamii/cowork-skills](https://github.com/jasonnamii/cowork-skills)

## License

MIT License — feel free to use, modify, and share.
