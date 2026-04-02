# People Node Intake

People Node Intake turns messy person-related input into safe person-node intake decisions and task handoff.

## Best For

- Obsidian-based relationship memory
- founder or operator personal knowledge systems
- human-in-the-loop business tracking
- project and review systems that need person-to-matter mapping

## Use It When

- a user mentions a specific person
- a user pastes a chat log, note, screenshot, or meeting summary about someone
- a user asks to remember, track, or profile a person
- a user asks who someone is before a meeting
- a user mixes a person with a follow-up action

## Do Not Use It For

- fully automatic CRM enrichment
- legal, fraud, or blacklisting judgment automation
- high-volume bulk ingestion without human review

## Prerequisites

- an Obsidian Vault is available
- the Vault contains `Library/People/`
- a task protocol is available for follow-up action handoff
- Synaptic Link or equivalent retrieval is available for recall

## Install

Copy this folder into your skill directory.

Example paths:

- `~/.claude/skills/people-node-intake`
- `~/.openclaw/workspace/skills/people-node-intake`

## Quick Start

1. Put the skill into your skill directory.
2. Make sure your Vault contains `Library/People/`.
3. Trigger it with input such as `记一下这个人，某合作方的商务负责人`.
4. Review whether the result should create, append, stay candidate, or require confirmation.

## Output Contract

Each run returns:

- target person
- operation type
- new facts
- new observations
- hypotheses needing verification
- linked matters
- task handoff decision
- target path

## Current Limits

- weak-signal social fragments must not become confirmed facts
- duplicate handling still relies on alias and context checks
- sensitive judgments require explicit confirmation
- v1 does not include graph visualization, reminders, or autonomous CRM workflows

## Compatibility

- core skill entry: `SKILL.md`
- detailed operating references: `references/`
- fictional sample nodes: `examples/`
- license: `LICENSE.txt`

## License

See `LICENSE.txt`.
