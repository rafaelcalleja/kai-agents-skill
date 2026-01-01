# Kai Agents Skill

Dynamic agent composition and orchestration system - create custom agents with unique personalities, voices, and trait combinations on-the-fly.

## Features

- **800 Agent Combinations**: Compose agents from 10 expertise, 10 personality, and 8 approach traits
- **Hybrid Agent Model**: Named agents (persistent) + Dynamic agents (task-specific)
- **Voice Mapping**: Each trait combination maps to a distinct voice
- **AgentFactory CLI**: Compose agents programmatically with trait inference

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

## Verify Installation

Once installed, test with:

- Ask: "create custom agents to research this topic" → activates the agents skill
- Ask: "what agent traits are available?" → lists all 28 composable traits
- Ask: "spin up custom security agents" → creates specialized security agents

## Prerequisites

- **Bun runtime**: `curl -fsSL https://bun.sh/install | bash`
- **Claude Code** (or compatible agent system)

### Install Dependencies

```bash
cd skills/Agents/Tools
bun add yaml handlebars
```

## Usage

### Natural Language

Just ask naturally:
- "Create a custom security agent"
- "Spin up 5 custom science agents"
- "List available agent traits"
- "I need a skeptical legal expert"

### AgentFactory CLI

```bash
# List all available traits
bun run skills/Agents/Tools/AgentFactory.ts --list

# Compose agent by traits
bun run skills/Agents/Tools/AgentFactory.ts --traits "security,skeptical,thorough"

# Infer traits from task
bun run skills/Agents/Tools/AgentFactory.ts --task "Review this API for vulnerabilities"
```

## Trait System

Agents are composed from three categories:

| Category | Options |
|----------|---------|
| **Expertise** | security, legal, finance, medical, technical, research, creative, business, data, communications |
| **Personality** | skeptical, enthusiastic, cautious, bold, analytical, creative, empathetic, contrarian, pragmatic, meticulous |
| **Approach** | thorough, rapid, systematic, exploratory, comparative, synthesizing, adversarial, consultative |

## Components

| Component | File | Purpose |
|-----------|------|---------|
| Agents skill | `skills/Agents/SKILL.md` | Routing and triggers |
| Agent factory | `skills/Agents/Tools/AgentFactory.ts` | Dynamic composition |
| Trait definitions | `skills/Agents/Data/Traits.yaml` | Expertise, personality, approach |
| Agent template | `skills/Agents/Templates/DynamicAgent.hbs` | Prompt generation |
| Create agent | `skills/Agents/Workflows/CreateCustomAgent.md` | Custom agent workflow |
| List traits | `skills/Agents/Workflows/ListTraits.md` | Show available traits |
| Personalities | `skills/Agents/AgentPersonalities.md` | Named agent examples |

## Version

- **Current**: 1.1.0
- **Author**: danielmiessler

## Changelog

### 1.1.0
- Custom agents now use `subagent_type: "general-purpose"` instead of "Intern"
- Added constitutional rule for custom agent creation

### 1.0.0
- Initial release
- 28 composable traits
- AgentFactory CLI tool
