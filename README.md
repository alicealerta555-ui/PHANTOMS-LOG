# PHANTOMS-LOG

**Playable Public Alpha — RC2.6.8**

PHANTOMS-LOG is an experimental open-source **Cyberpunk text RPG for ChatGPT and future local language models**. It is deliberately being developed as a text RPG first, because text is the simplest environment in which to build and test the difficult parts of AI gaming: persistent world state, human-like NPC behaviour, memory, relationships, consequences, procedural regions, quests, loot, trade, survival and natural-language player input.

> The goal is not an AI that merely writes a Cyberpunk story. The goal is an AI game master operating inside a real, persistent game simulation.

## Play directly in ChatGPT

PHANTOMS-LOG is designed so that the public game package can be used directly inside a ChatGPT conversation.

1. Download the **PHANTOMS-LOG RC2.6.8 Public Alpha** package.
2. Start a new ChatGPT conversation and upload the project ZIP/package to the chat.
3. Tell ChatGPT to read and follow `CHAT_SPIELSTART.md` and start PHANTOMS-LOG from the uploaded project files.
4. For a new run, complete character creation when prompted.
5. Play using normal free-form language. You do not need to select from A/B/C/D dialogue buttons.

A suitable start message is:

```text
Use the uploaded PHANTOMS-LOG project files. Read CHAT_SPIELSTART.md and follow its game-start instructions. Start a new PHANTOMS-LOG run and guide me through character creation. Treat the runtime and persistent game state as authoritative; do not invent successful actions, items or world state that the game does not support.
```

For an existing run, upload the relevant public project/save package and tell ChatGPT to **continue the existing run rather than silently creating a replacement save**.

The language model is the interface and game-master layer; the project's runtime, rules and persistent state are intended to remain authoritative wherever the current build provides them.

> **Current Public Alpha note:** the complete Public Alpha package/source tree must be available to the chat for this workflow. The GitHub repository is still being populated with the full public source package; the README alone is not the game.

## Why text first?

The project starts as a text adventure by design. The simulation should work before a graphics engine is placed on top of it. Later, a visual client, generated backgrounds, NPC portraits, creature images and other presentation layers can be added without changing the canonical world state.

The intended architecture is:

**simulation/runtime → persistent world state → language model → presentation**

For images:

**runtime world state → structured visual description → image model/API → illustration**

The image must represent the world. It must not invent new canonical facts.

## What already works

PHANTOMS-LOG is more than a design document. The current codebase already contains working or partially integrated systems for:

- free-form text input instead of A/B/C/D dialogue menus
- character creation
- attributes, skills and talents
- multiple character classes
- save/load and persistent run state
- locations and movement
- automatic arrival/perception context
- search and exploration
- rule-bound loot resolution
- canonical item definitions and item instances
- item provenance
- inventory
- crafting
- repair
- trade and scarcity-aware pricing
- negotiation hooks
- quests and quest state
- hidden information and epistemic boundaries
- authorization/access concepts
- NPC state
- NPC memory and continuity
- trust, fear, grievance and reputation systems
- households, factions and social propagation
- autonomous NPC routines
- dynamic events
- regional/cultural world surfaces
- weather/environment systems
- survival pressure and needs
- persistent consequences
- rule-bound narration
- test, stress-test and audit infrastructure

The project is already **playable**. The important point is not that every subsystem is finished; it is that there is already a real game loop underneath the remaining development work.

## NPC philosophy: people, not assistants

A core goal is for NPCs to behave like people rather than helpful chatbots.

NPCs should be friendly when friendliness makes sense — for example during normal service interactions, trade or routine conversation — but friendliness must never mean automatic obedience.

Before agreeing to a request, an NPC should consider:

- physical self-protection
- legal risk
- professional/job risk
- economic risk
- security policies
- role and responsibility
- authorization
- trust and familiarity
- fear and grievance
- reputation
- faction interests
- personality and current needs

A clerk may happily hand over a package that belongs to the player and then immediately refuse: **“Can I use your internal computer?”**

Persuasion, deception, bribery, intimidation, credentials and trust may influence a decision, but they should not magically erase hard security boundaries.

**Friendliness is not obedience.**

RC2.6.8 Public Alpha includes an additional self-protection/security gate in the lived-experience NPC layer so that high-risk, unauthorized and clearly out-of-role requests are rejected before ordinary social friendliness is evaluated.

## Persistent NPC life

The longer-term aim is that NPCs do not freeze when the player leaves.

They should have schedules, needs, relationships, work, travel, conflicts, memories and goals. When the player meets someone again later, that NPC may have experienced events in the meantime. A shopkeeper does not need to remain behind the same counter forever simply because the player has not been watching.

The target is a world in which NPCs are **persistent simulated people** rather than dialogue nodes.

## World generation and biomes

The intended world model is closer to procedural games such as Minecraft than to an entirely improvised chat story.

The engine can use predefined **biomes / regional archetypes** containing rules for architecture, resources, hazards, factions, services, trade flows and typical population structures. Concrete locations can then be generated from those rules and persist after generation.

A generated district should remain that district. If it is looted, damaged, occupied or abandoned, those changes should persist.

## AI model / training

PHANTOMS-LOG was structured with the intention that its rules, prompts, behavioural systems and world information can later be used with a dedicated or locally running language model.

The next large experimental step is **training and model integration**.

### Why I am not simply training the full model myself

I am still developing this project on a **GeForce GTX 1060 with 6 GB of VRAM**. It is useful for development, testing and smaller local-model experiments, but it is simply not enough compute for the kind of larger training work I want to try with PHANTOMS-LOG.

I also do not have access to server farms or serious training infrastructure.

And there is another practical reason: at the moment I am living in **ASOG emergency accommodation — essentially homeless accommodation**. Materially, I currently have close to the minimum that life provides.

But I have my AI, I have this project, and I keep building.

That is one of the reasons I am opening PHANTOMS-LOG to other people. If you have stronger hardware, training experience, access to compute, or simply an idea that I cannot test on my own machine, you are welcome to try it and contribute the results back to the project.

Community experiments are explicitly welcome.

Useful areas include:

- LoRA / QLoRA
- fine-tuning suitable open-weight models
- preparing PHANTOMS-LOG data for training
- comparing base models
- local inference
- quantized models
- rule-compliance benchmarks
- NPC consistency benchmarks
- runtime/LLM hybrid architectures

If you have the hardware and want to try training a model for PHANTOMS-LOG, please do. Training configurations, adapters, benchmarks and reproducible results are welcome.

The target model should learn to **run PHANTOMS-LOG**, not merely imitate Cyberpunk prose.

## What still needs work

This is a **Playable Public Alpha**, not a finished 1.0 release. Useful contribution areas include:

- natural-language intent parsing
- free text → authoritative runtime action mapping
- deeper NPC self-protection and conflict behaviour
- defensive/aggressive NPC reactions
- long-term retaliation and consequences
- persistent emergent quests
- save migration between releases
- location migration/fallback resolution
- combat and balance
- economy and trading
- crafting depth
- procedural biome/world generation
- API integration
- local LLM integration
- training/fine-tuning
- automated regression testing
- performance
- GUI / graphics engine
- generated backgrounds, portraits and scene imagery

## API and image future

The runtime should eventually be able to work with different model providers or local inference servers through clean interfaces rather than being tied to one model.

Image generation is also a natural future layer. Locations, NPCs, creatures, items and major events could be visualized automatically, provided the image pipeline remains subordinate to the canonical game state.

## Local quick start

If you are running the project locally rather than through ChatGPT, use the shell launcher.

Linux/macOS-style shell:

```bash
chmod +x START_GAME.sh
./START_GAME.sh
```

For project validation:

```bash
./run_all_tests.sh
```

See `CHAT_SPIELSTART.md`, `START_HIER.md`, `READ_ME_FIRST_STANDALONE.md` and the documentation in the repository for more details.

## Current validation note

For this Public Alpha preparation, the NPC lived-experience test module passes **21/21 tests** after the self-protection patch. The primary unit-test suite passes **1241 tests** after fixing the public test runner's Python path to include `playable_full_version`.

The broader repository contains additional stress tests, smoke tests and audits. This is still an alpha release; bug reports and reproducible test cases are welcome.

## Open source

PHANTOMS-LOG is released under the **GNU General Public License v3.0 (GPL-3.0)** for original project material covered by the repository license. See `LICENSE`.

Third-party components, if any are introduced or separately identified, remain subject to their own licenses.

Forks, experiments and alternative implementations are welcome. If an approach works better, test it, document it and open a pull request.

## Project vision

PHANTOMS-LOG is being built around a simple idea:

**AI gaming should be more than a chatbot pretending to be a game.**

The simulation should exist independently enough that NPCs, objects, locations and consequences remain real parts of the game state — and the language model should make that world understandable, playable and human.
