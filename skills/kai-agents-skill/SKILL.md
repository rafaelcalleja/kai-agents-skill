---
name: kai-agents-skill
description: This skill should be used when the user asks to "create custom agents", "spin up custom agents", "specialized agents", "agent personalities", "available traits", "agent voices", or mentions dynamic agent composition, trait-based agents, or unique agent personalities. Provides a complete agent composition and orchestration system.
---

# Kai Agents Skill

Dynamic agent composition system - create specialized agents with unique personalities and voices, composed from traits on-the-fly.

## Quick Reference

| Trigger | Action |
|---------|--------|
| "create custom agents" | Use AgentFactory to compose unique agents |
| "what traits are available" | List all 28 composable traits |
| "spin up agents" | Launch generic parallel agents |
| "use [agent name]" | Use a named persistent agent |

## Hybrid Agent Model

Two types of agents work together:

| Type | Definition | Best For |
|------|------------|----------|
| **Named Agents** | Persistent identities with backstories | Recurring work, voice output, relationships |
| **Dynamic Agents** | Task-specific specialists composed from traits | One-off tasks, novel combinations, parallel work |

## Trait Composition System

Agents are composed by combining three trait categories:

```
AGENT = Expertise + Personality + Approach
```

**Total combinations:** 10 × 10 × 8 = **800 unique agent compositions**

### Available Traits

See [references/traits.md](references/traits.md) for complete trait definitions.

**Expertise (10):** security, legal, finance, medical, technical, research, creative, business, data, communications

**Personality (10):** skeptical, enthusiastic, cautious, bold, analytical, creative, empathetic, contrarian, pragmatic, meticulous

**Approach (8):** thorough, rapid, systematic, exploratory, comparative, synthesizing, adversarial, consultative

## Route Triggers

**CRITICAL: The word "custom" is the KEY trigger:**

| User Says | What to Use | Why |
|-----------|-------------|-----|
| "**custom agents**", "create **custom** agents" | AgentFactory workflow | Unique prompts + unique voices |
| "agents", "launch agents", "bunch of agents" | Generic Task tool | Same voice, parallel grunt work |
| "use [agent name]", "get [agent name] to" | Named agent | Pre-defined personality |

## Creating Custom Agents

When user requests custom agents:

1. **Determine requirements** from request:
   - How many agents? (Default: 1)
   - What's the task?
   - Specific traits mentioned?

2. **Vary traits for each agent** - CRITICAL for unique voices:
   ```
   Agent 1: research + enthusiastic + exploratory → Energetic voice
   Agent 2: research + skeptical + systematic → Academic voice  
   Agent 3: research + analytical + comparative → Professional voice
   ```

3. **Launch agents in parallel** using Task tool with unique prompts

See [references/create-custom-agent-workflow.md](references/create-custom-agent-workflow.md) for detailed workflow.

## Voice Mapping

Each trait combination maps to a distinct voice for TTS output:

| Traits | Voice | Character |
|--------|-------|-----------|
| skeptical + analytical | Academic | Intellectual warmth |
| enthusiastic + creative | Energetic | High-energy dynamic |
| cautious + meticulous | Professional | Measured formal |
| security + adversarial | Intense | Deep gravelly |
| empathetic + consultative | Warm | Friendly engaging |

See [references/voice-mappings.md](references/voice-mappings.md) for complete voice mapping system.

## Model Selection

| Task Type | Model | Reason |
|-----------|-------|--------|
| Grunt work | `haiku` | 10-20x faster, cost efficient |
| Standard analysis | `sonnet` | Balanced quality/speed |
| Deep reasoning | `opus` | Maximum intelligence |

## Example Compositions

### Security Red Team
```
Agent 1: security + adversarial + bold → Intense voice
Agent 2: security + skeptical + meticulous → Gritty voice
Agent 3: security + contrarian + systematic → Academic voice
```

### Research Team
```
Agent 1: research + enthusiastic + exploratory → Energetic voice
Agent 2: research + skeptical + thorough → Academic voice
Agent 3: research + analytical + synthesizing → Professional voice
```

### Contract Review
```
Agent 1: legal + cautious + meticulous → Professional voice
Agent 2: legal + skeptical + systematic → Authoritative voice
Agent 3: legal + contrarian + thorough → Academic voice
```

## Named Agent Examples

For recurring work with relationship continuity, use named agents:

- **The Intern**: Eager, curious, fast-talking overachiever
- **The Architect**: Academic visionary with strategic wisdom
- **The Engineer**: Battle-scarred leader with practical experience

See [references/named-agents.md](references/named-agents.md) for full personality definitions.

## Common Mistakes

| Wrong | Right |
|-------|-------|
| Same traits for all agents | Vary traits for unique voices |
| Using "custom" for generic parallel work | "Custom" = unique personalities |
| Specifying traits without personality | Always include personality dimension |

## Integration

Works well with:
- **kai-voice-system**: Agents automatically use voice IDs for TTS
- **kai-observability-server**: Track agent spawning in real-time
