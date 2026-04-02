# Intake SOP Detail

## Accepted Inputs

- spoken notes
- chat logs
- screenshots
- business cards
- meeting notes
- review or project references

## Routing Summary

1. Detect whether the input is person-related.
2. Split person information from task or action content.
3. Check whether the minimum node threshold is met.
4. Search existing nodes by name, aliases, organization, role, and context.
5. Choose one operation: `create`, `append`, `candidate`, or `needs confirmation`.
6. Route action content to the task protocol when needed.

## Extraction Targets

Extract only:

1. identity
2. confirmed facts
3. explicit user-stated observations
4. hypotheses needing verification
5. linked projects, matters, or people
6. follow-up actions

## Dedup Order

1. name
2. aliases
3. organization
4. role
5. project or matter context
6. linked people

## Append-Only Rule

When an existing node is found:

- append new facts to the end of the fact log
- update `last_interaction` only when justified
- add aliases or linked matters only when the new evidence supports it
- do not rewrite the whole node
- do not silently overwrite old facts or old judgments

## Auto-Merge Threshold

Only auto-merge when at least three of the following align and there is no material conflict:

- name or alias
- organization
- role
- project or matter context
- linked people

Otherwise:

- mark as possible duplicate
- escalate for confirmation

## Escalate Instead of Storing When

- identity is incomplete
- accusation is unsupported
- input is highly emotional
- contradictions are strong
- the user intent is unclear

## Clarification Limit

- ask at most two rounds of clarification
- downgrade to `candidate` or keep only raw material if still unclear

## Output Discipline

Always separate:

1. confirmed facts
2. explicit user observations
3. hypotheses needing verification
4. linked matters
5. task handoff
