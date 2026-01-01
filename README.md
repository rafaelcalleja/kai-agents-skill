# kai-agents-skill

> Dynamic agent composition system - create specialized agents with unique personalities and voices, composed from traits on-the-fly

Create custom agents by combining expertise, personality, and approach traits. 800 unique agent combinations possible.

## Features

- **28 Composable Traits** - 10 expertise, 10 personality, 8 approach
- **Hybrid Agent Model** - Named agents (persistent) + Dynamic agents (task-specific)
- **Voice Mapping** - Each trait combination maps to a distinct voice
- **AgentFactory CLI** - Compose agents programmatically with trait inference

**Core Philosophy:** Cognitive diversity through composable agent personalities. Every analysis benefits from multiple perspectives.

## Installation

### Option 1: Marketplace (Recommended)

```bash
# From Claude Code, run:
/plugin marketplace add rafaelcalleja/kai-agents-skill
/plugin install kai-agents-skill@rafaelcalleja-kai-agents-skill
```

### Option 2: Development/Testing

```bash
# Clone and use directly
git clone https://github.com/rafaelcalleja/kai-agents-skill.git
claude --plugin-dir ./kai-agents-skill
```

### Option 3: CLI Tools Only

```bash
cd kai-agents-skill/skills/Agents/Tools
bun install
```

## Verify Installation

Once installed, test with:

- Ask: *"create custom agents to research this topic"* → activates the agents skill
- Ask: *"what agent traits are available?"* → lists all 28 composable traits
- Ask: *"spin up custom security agents"* → creates specialized security agents

## Components

### Skill: Agents

Provides dynamic agent composition. Triggers on:
- "create custom agents", "spin up agents"
- "specialized agents", "agent personalities"
- "list available traits", "agent voices"

### Trait Categories

| Category | Count | Options |
|----------|-------|---------|
| **Expertise** | 10 | security, legal, finance, medical, technical, research, creative, business, data, communications |
| **Personality** | 10 | skeptical, enthusiastic, cautious, bold, analytical, creative, empathetic, contrarian, pragmatic, meticulous |
| **Approach** | 8 | thorough, rapid, systematic, exploratory, comparative, synthesizing, adversarial, consultative |

**Total combinations:** 10 x 10 x 8 = **800 unique agents**

## Usage

### Natural Language

Just ask naturally:
- "Create a custom security agent"
- "I need a skeptical legal expert"
- "Spin up 3 research agents with different approaches"

### AgentFactory CLI

```bash
cd skills/Agents/Tools

# List all available traits
bun run AgentFactory.ts --list

# Compose agent by traits
bun run AgentFactory.ts --traits "security,skeptical,thorough"

# Infer traits from task
bun run AgentFactory.ts --task "Review this API for vulnerabilities"
```

## Directory Structure

```
kai-agents-skill/
├── .claude-plugin/
│   ├── marketplace.json
│   └── plugin.json
├── skills/
│   └── Agents/
│       ├── SKILL.md
│       ├── AgentPersonalities.md
│       ├── Data/
│       │   └── Traits.yaml
│       ├── Templates/
│       │   └── DynamicAgent.hbs
│       ├── Tools/
│       │   └── AgentFactory.ts
│       └── Workflows/
│           ├── CreateCustomAgent.md
│           └── ListTraits.md
└── README.md
```

## Credits

- **Origin:** Based on [kai-agents-skill pack](https://github.com/danielmiessler/Personal_AI_Infrastructure) by Daniel Miessler
- **License:** MIT

### Acknowledgments

- **Daniel Miessler** - Original PAI architecture and agent concepts
- **IndyDevDan** - Trait composition patterns and voice mapping
- **Anthropic** - Claude 4.x agent capabilities

## Changelog

### v1.1.0 (2026-01-01)

Synced with standard plugin structure:

- **BREAKING**: Moved `plugin.json` to `.claude-plugin/` directory
- Updated paths to use `CLAUDE_PLUGIN_ROOT` for portability
- Custom agents now use `subagent_type: "general-purpose"` instead of "Intern"
- Removed `.claude/settings.local.json`

### v1.0.0

- Initial release
- 28 composable traits (10 expertise, 10 personality, 8 approach)
- AgentFactory CLI tool with trait inference
- Hybrid agent model (named + dynamic)
