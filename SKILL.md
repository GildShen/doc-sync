---
name: doc-sync
description: "Synchronize project documentation with verified implementation, interfaces, configuration, and operational behavior across languages and frameworks. Use when asked to update, audit, or correct documentation against implementation, or when project instructions require documentation synchronization. Confirm the documentation destination before writing when it has not already been specified."
---

# Documentation Synchronization

Keep documentation aligned with verified behavior. Organize it around maintained features, workflows, contracts, and operations rather than creating one document per source file.

## Confirm the Destination Before Writing

On first use in a project, inspect applicable project instructions and the existing documentation structure, then confirm where the user wants documentation written before creating or modifying documentation files.

- If the user has already explicitly named the destination in the current task or established a continuing preference for this project, use it without asking again.
- Otherwise, propose the most relevant existing document or directory and ask one concise question, for example: "Where should I write the documentation? I suggest updating `docs/api.md`; you can choose another file or directory."
- A repository convention is evidence for a recommendation, not confirmation of the user's destination preference, unless an applicable instruction explicitly selects it for this task.
- While waiting, continue read-only investigation and prepare the proposed content. Do not treat silence as confirmation or write to the guessed destination.
- Reconfirm only if the destination becomes unavailable or the task requires a materially different documentation area. Do not ask on every file or turn within an agreed scope.
- For an audit-only request, report findings without requiring a write destination. Ask only if the user also requests edits and has not specified one.

Installation alone does not run this skill or open a conversation. Apply this confirmation rule when the skill is invoked for documentation work. Do not modify the installed skill to store preferences; use an available project preference mechanism only when the user requests persistence.

## Establish Scope and Evidence

Identify the requested behavior, intended audience, relevant implementation, and documentation owners. Follow applicable project instructions and respect exclusions in the user's request. Ordinary code changes do not automatically authorize unrelated documentation work.

Use the smallest relevant set of implementation files, tests, interface definitions, schemas, configuration, and observed runtime or operational evidence. Existing documentation establishes structure and prior claims; it does not prove current implementation behavior. Treat tests as evidence of intended coverage and distinguish them from behavior actually executed or verified.

For mismatches, distinguish implemented behavior, a separately authoritative specification, and an unimplemented requirement. Describe divergence explicitly; do not silently rewrite a normative specification to match a bug. State unresolved uncertainty and link to the relevant source when helpful.

## Select the Documentation Boundary

Prefer updating the existing document that owns the subject:

- **Feature or workflow:** purpose, entry points, main flow, outcome, and relevant limitations.
- **Interface or contract:** ownership, inputs, outputs, invariants, compatibility, and verification.
- **Data or migration:** schema changes, upgrade and rollback behavior, data risks, and verification.
- **Operations:** prerequisites, configuration, steps, verification, and recovery.
- **Module:** responsibility and important entry points; use existing doc comments or local documentation for implementation details.

Create a document only when a stable subject has no suitable existing owner and the new file is within the confirmed destination and task scope. Update an existing index when necessary to make that document discoverable, provided the index is within the agreed scope. Otherwise report the suggested index update.

Follow project conventions for paths, language, audience, metadata, and navigation. Do not impose a `docs/` directory, a particular index filename, update-date fields, or a fixed template. Use only useful sections; omit empty placeholders. Link to authoritative contracts instead of duplicating them. Respect any separate ownership of user help, API references, or operational runbooks without depending on a particular companion skill.

## Make Proportional Updates

Update documentation when requested or when an authorized change affects a documented workflow, public interface, contract, configuration, migration, integration, or operational procedure. Correct material mismatches supported by evidence.

An internal refactor, formatting change, or test-only change normally needs no documentation update when documented behavior remains accurate. Report that conclusion when relevant. An explicit documentation request can still justify improving explanations or structure without a code change.

Keep edits focused on the requested subject and preserve unrelated content. Do not alter implementation to make documentation true unless implementation changes are separately authorized. Do not add change-log entries, TODO records, manual test cases, commits, deployment, or publication as incidental outputs; follow existing authorization and project requirements for each.

## Verify and Report

Review the final edits against the requested scope and evidence before running checks. Verify names, signatures, defaults, examples, links, and operational steps affected by the edit. Use existing documentation build, link, or example checks when relevant and available; do not run a full application test suite solely for prose changes.

Report the documentation destination, substantive updates, verification performed, and any unresolved mismatch or unverified example. Distinguish checked content from commands that were not executed.
