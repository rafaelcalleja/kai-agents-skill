# kai-agents-skill

Dynamic agent composition and orchestration system - create custom agents with unique personalities, voices, and trait combinations on-the-fly.

## Features

- **Hybrid Agent Model** - Named agents for recurring work, dynamic agents for one-off tasks
- **Trait Composition** - 800 unique agent combinations (10 expertise × 10 personality × 8 approach)
- **Voice Mapping** - Automatic voice assignment based on personality traits
- **Parallel Orchestration** - Launch multiple custom agents simultaneously

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

- Ask: *"create custom agents to research this topic"* → activates the agents skill
- Ask: *"what agent traits are available?"* → lists all 28 composable traits
- Ask: *"spin up custom security agents"* → creates specialized security agents

## Trigger Phrases

- "create custom agents"
- "spin up custom agents"
- "specialized agents"
- "agent personalities"
- "available traits"
- "agent voices"

## Usage

### Create Custom Agents

```
User: Create 3 custom research agents to analyze this market

Result: 3 agents with unique personalities:
- Agent 1: research + enthusiastic + exploratory → Energetic voice
- Agent 2: research + skeptical + thorough → Academic voice
- Agent 3: research + analytical + comparative → Professional voice
```

### List Available Traits

```
User: What agent traits are available?

Result: Lists all 28 composable traits:
- 10 Expertise areas (security, legal, finance, etc.)
- 10 Personality dimensions (skeptical, enthusiastic, etc.)
- 8 Approach styles (thorough, rapid, systematic, etc.)
```

### Security Red Team

```
User: Spin up custom security agents to red team this architecture

Result: 3 security-focused agents with different attack perspectives:
- Agent 1: security + adversarial + bold → Intense voice
- Agent 2: security + skeptical + meticulous → Gritty voice
- Agent 3: security + contrarian + systematic → Academic voice
```

## Trait Categories

### Expertise (10)
Domain knowledge: security, legal, finance, medical, technical, research, creative, business, data, communications

### Personality (10)
Behavioral style: skeptical, enthusiastic, cautious, bold, analytical, creative, empathetic, contrarian, pragmatic, meticulous

### Approach (8)
Work style: thorough, rapid, systematic, exploratory, comparative, synthesizing, adversarial, consultative

## Voice Integration

When integrated with a TTS system, each agent gets a distinct voice based on their traits:

| Personality | Voice Character |
|-------------|-----------------|
| Skeptical + Analytical | Academic warmth |
| Enthusiastic + Creative | High-energy dynamic |
| Cautious + Meticulous | Measured professional |
| Security + Adversarial | Intense gravelly |

## Directory Structure

```
kai-agents-skill/
├── .claude-plugin/
│   └── marketplace.json
├── plugin.json
├── skills/
│   └── kai-agents-skill/
│       ├── SKILL.md
│       └── references/
│           ├── traits.md
│           ├── voice-mappings.md
│           ├── create-custom-agent-workflow.md
│           └── named-agents.md
└── README.md
```

## Works Well With

- **kai-voice-system** - Agents automatically use voice IDs for TTS notifications
- **kai-observability-server** - Track agent spawning and outputs in real-time

## Credits

Based on the kai-agents-skill pack from [Personal AI Infrastructure](https://github.com/danielmiessler/fabric) by Daniel Miessler.
