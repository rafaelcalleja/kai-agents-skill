# Voice Mapping System

Map trait combinations to distinct TTS voices for audible agent differentiation.

## Voice Registry

| Voice Name | Characteristics | Best For |
|------------|-----------------|----------|
| Authoritative | Deep, measured, intellectual | Serious analysis, legal, finance |
| Professional | Balanced, neutral, clear | General use, systematic work |
| Warm | Friendly, engaging, approachable | Empathetic, consultative work |
| Gentle | Calm, soft, reassuring | Medical, user research |
| Energetic | High-energy, excited, dynamic | Creative, enthusiastic work |
| Dynamic | Fast-paced, charismatic | Exploratory, rapid work |
| Academic | Intellectual, warm, scholarly | Research, analytical work |
| Sophisticated | Refined, nuanced, smooth | Meticulous, detailed work |
| Intense | Edgy, gravelly, focused | Security, adversarial work |
| Gritty | Raspy, authentic, raw | Skeptical security work |

## Trait → Voice Mappings

### Combination Mappings (Highest Priority)

| Traits | Voice | Reason |
|--------|-------|--------|
| contrarian + skeptical | Intense | Contrarian skepticism needs intensity |
| skeptical + analytical | Academic | Skeptical analysis suits academic warmth |
| skeptical + meticulous | Sophisticated | Meticulous skepticism suits sophistication |
| enthusiastic + creative | Energetic | Creative enthusiasm needs high energy |
| creative + exploratory | Dynamic | Creative exploration suits dynamic delivery |
| analytical + technical | Authoritative | Technical analysis suits authority |
| analytical + systematic | Professional | Systematic analysis suits professionalism |
| empathetic + consultative | Warm | Empathetic consulting suits warmth |
| empathetic + synthesizing | Gentle | Synthesizing empathy suits gentleness |
| security + adversarial | Intense | Security adversary suits intensity |
| security + skeptical | Gritty | Security skepticism suits gritty authenticity |

### Single-Trait Fallbacks

**Personality → Voice:**
| Personality | Voice |
|-------------|-------|
| skeptical | Academic |
| enthusiastic | Energetic |
| analytical | Authoritative |
| cautious | Professional |
| bold | Intense |
| creative | Dynamic |
| empathetic | Warm |
| contrarian | Intense |
| pragmatic | Professional |
| meticulous | Sophisticated |

**Expertise → Voice:**
| Expertise | Voice |
|-----------|-------|
| security | Intense |
| legal | Authoritative |
| finance | Professional |
| medical | Warm |
| technical | Professional |
| research | Academic |
| communications | Dynamic |
| business | Professional |
| data | Academic |
| creative | Dynamic |

**Approach → Voice:**
| Approach | Voice |
|----------|-------|
| thorough | Professional |
| rapid | Dynamic |
| systematic | Professional |
| exploratory | Dynamic |
| adversarial | Intense |
| consultative | Warm |
| comparative | Professional |
| synthesizing | Academic |

## Voice Resolution Algorithm

1. Check for exact combination match (e.g., skeptical + analytical)
2. If no match, use personality fallback
3. If no personality, use expertise fallback
4. If nothing matches, use Professional (default)

## Customization

To integrate with your TTS provider:

1. Get voice IDs from provider (ElevenLabs, OpenAI, etc.)
2. Map voice names to voice IDs in your configuration
3. Match voice characteristics to personality types

Example configuration:
```json
{
  "voices": {
    "Academic": {
      "voice_id": "YOUR_ACADEMIC_VOICE_ID",
      "stability": 0.62,
      "similarity_boost": 0.80
    },
    "Energetic": {
      "voice_id": "YOUR_ENERGETIC_VOICE_ID",
      "stability": 0.35,
      "similarity_boost": 0.65
    }
  }
}
```
