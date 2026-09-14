# Changelog

## RC2.6.8 — Playable Public Alpha

- prepared first public open-source release
- GPL-3.0 licensing
- public README and contribution guidance
- NPC lived-experience self-protection/security gate
- unauthorized, high-risk and out-of-role requests can be refused before friendliness logic
- negotiation context differentiated from fixed-service behavior
- public test runner path fix
- 21/21 NPC lived-experience tests passing
- 1241 primary unit tests passing in release preparation
- private provenance/security artifacts excluded from the public build

### Progression hotfix — XP / level wiring

- added persistent numeric XP to player progression state
- committed, anti-farm-filtered gameplay evidence now awards XP automatically
- XP now resolves the authoritative player level
- Level 2 is reached at 12 XP; Level 3 is reached at approximately 36 XP
- later level thresholds rise progressively toward Level 50
- existing RC2.6.8 saves without an XP field backfill XP once from already-earned `pattern_evidence`
- legacy migration does not double-count previously earned evidence
- added regression tests for XP gain, level thresholds, persistence and legacy-save migration
- primary unit suite remains **1241 tests, OK** after the hotfix; additional targeted progression tests also pass

This remains an alpha release. Save migration, deeper NPC autonomy, combat/economy balance, local-model integration, APIs, procedural biomes and image-generation layers remain active development areas.
