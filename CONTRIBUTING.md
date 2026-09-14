# Contributing to PHANTOMS-LOG

Thanks for helping improve PHANTOMS-LOG.

## Good contribution areas

- NPC behavior and persistence
- natural-language intent parsing
- world generation and biome systems
- quests, trade, combat and crafting
- tests and regression cases
- local LLM integration
- model training experiments
- APIs and image-generation adapters
- performance and save migration
- documentation and onboarding

## Before opening a pull request

1. Keep simulation truth separate from narration.
2. Do not make image output authoritative world state.
3. Preserve persistent consequences unless a migration explicitly changes them.
4. Add or update tests for behavioral changes when practical.
5. Run the relevant tests before submitting substantial changes.

## NPC behavior rule

NPCs are not assistants. Friendliness does not imply obedience. Self-protection, authorization, professional rules, social context and personal goals should be evaluated before compliance.

## Pull requests

Explain what changed, why it changed, what was tested, and whether save compatibility is affected.

By contributing, you agree that your contribution is licensed under the repository's GPL-3.0 license unless explicitly stated otherwise.
