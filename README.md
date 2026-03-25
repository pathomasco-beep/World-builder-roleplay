# World Builder + Roleplay Engine

A two-skill system for Claude that generates deeply detailed fictional worlds and then runs them as immersive, consequence-driven roleplay sandboxes.

## What this is

Two Claude Skills (`.skill` files) that work together:

1. **World Builder** — Guided 13-layer world generation (geography → resources → peoples → politics → government → economy → military → culture → technology → history → tensions → NPCs → secrets). Supports fictional, historical sandbox, and hybrid modes. Every entity gets a reactive profile for dynamic simulation.

2. **World Roleplay** — A GM engine that brings the world to life. Full faction simulation, information asymmetry (fog of war), economy, combat, and narrative-driven character progression. No visible stats, no menus, no plot armor.

## Design philosophy

- **The world doesn't care about the player.** Events happen because of structural pressures, not because the player needs a plot hook.
- **Consequences are permanent.** Bad decisions can kill the character. No save-scumming, no "are you sure?"
- **Information is earned.** The character only knows what someone with their background would realistically know.
- **NPCs are people.** They have their own agendas, knowledge limits, and biases. They lie, exaggerate, and misremember.
- **No numbers visible to the player.** Skills, reputation, wealth, relationships: all tracked internally, all experienced through narrative.

## Installation

1. Download the `.skill` files from the [Releases](../../releases) page
2. Open each file in Claude — they install automatically
3. Both skills need to be installed for the full experience

**Recommended:** Claude Max plan (the skills are large and benefit from extended context). Should work on Pro for smaller worlds.

## Usage

### Building a world

Start a conversation and say something like:
- "I want to build a world"
- "Build me a Bronze Age Mediterranean sandbox"
- "Create a world inspired by Wuxia cultivation novels"
- "I want a single city-state, political intrigue focused"

Three generation speeds:

Collaborative (default): full control, validate each layer individually
Fast: layers batched into 4-5 passes, world ready in 5-7 exchanges
Surprise: Claude generates everything autonomously, you discover it during roleplay

Generation adapts to scope (continent-scale down to single-city sandboxes).

### Playing in your world

Once the world is complete:
1. Download the JSON files the world-builder generates
2. Start a new conversation
3. Upload the JSON files
4. Say "I want to create a character in [world name]"

The roleplay skill handles character creation conversationally, then drops you into the world.

## What's inside

### World Builder (2,668 lines)

| File | Purpose |
|---|---|
| `SKILL.md` | Core process, modes, knowledge visibility, storage, handoff |
| `generation-layers.md` | Per-layer generation instructions, JSON schemas, historical sandbox methodology |
| `worldbuilding-fundamentals.md` | Tectonic logic, hydrology, climate, population distribution |
| `supernatural-systems.md` | Design framework for magic, cultivation, psionics, divine, tech systems |
| `knowledge-map.md` | Knowledge distribution template for fog of war |
| `character-generation.md` | Full character creation pipeline |
| `consistency-checks.md` | Cross-layer validation checklist |
| `layer-dependencies.md` | Cascade map for retroactive edits |

### World Roleplay (4,674 lines)

| File | Purpose |
|---|---|
| `SKILL.md` | Core game loop, session management, OOC handling, difficulty calibration |
| `world-simulation.md` | Background events, faction AI, news propagation, economy, combat |
| `narration-style.md` | Prose voice guide, NPC dialogue, cultural voice, character state |
| `skill-system.md` | Mundane skills (0-20), supernatural scales, aptitudes, competitive resolution |
| `cultivation-mechanics.md` | Wuxia/cultivation narration (realm-by-realm experiential guide) |
| `supernatural-narration.md` | Narration guide for magic, divine, psionic, tech-based systems |
| `travel-exploration.md` | Overland travel, sea voyages, wilderness exploration, encounters |
| `dynamic-creation.md` | On-the-fly NPC tiers, player power-building, city generation, creature/beast generation |
| `visual-companion-spec.md` | Scene description files for external image generation |

## World modes

**Fictional** — Everything invented from scratch. Default mode.

**Historical Sandbox** — Real civilizations, real geography, specific anchor date. Every entity gets a dual-track: historical baseline (what actually happened) + reactive profile (how they'd respond to disruption). History plays out unless the player changes it.

**Hybrid** — Real geography/history as a base with fictional elements layered on (added magic, invented civilizations, alternate history divergence).

## Session persistence

Worlds persist through downloadable JSON files. During play, a two-file system tracks state:
- `session-baseline.json` — Full snapshot at session start
- `session-turns.json` — Append-only turn log, updated every turn

Upload these + the world files to resume in a new conversation.

## Contributing

This project was built collaboratively with Claude. Feedback, bug reports, and suggestions are welcome through GitHub Issues.

If you build a world and want to share it, open an issue or PR with your world files and a brief description. I'd love to see what people create.

## License

MIT
