# Copilot Instructions – AI-SDLC Repository

These instructions optimise AI coding/documentation agents for this workspace’s SDLC automation model. Focus: high‑fidelity Markdown documentation, never speculative code.

## Core Operating Principles
1. Produce **Markdown documentation only**; no executable code unless explicitly introduced later. 
2. Every new or updated artefact must link to at least one requirement ID in `docs/requirements/RTM.md` – add or extend RTM rows if missing.
3. Reflect all baselines, decisions, risks, open questions, and scope changes in `docs/change-log.md` immediately (no batching).
4. Use templates exclusively from the ` templates/` directory (note the leading space). Do not copy from `templates-old/` unless asked for diff analysis.
5. Preserve embedded tables (Approvals, Version History) in each template; populate with real data (never leave placeholder underscores).

## Repository Structure Awareness
- `prompts/phase-0x-*` folders define personas & phase sequencing. Respect prerequisite ordering in README and `AGENTS.md`.
- Generated docs live under phase-specific subfolders (`docs/inception/`, `docs/requirements/`, `docs/design/`, etc.). Create subdirectories if absent.
- Backlog items (`backlog/`) use `EPIC.md`, `Feature.md`, `Story.md`, `Task.md`; cross-reference RTM IDs and parent hierarchy.
- Architecture/design: LLD files go in `docs/design/LLD/` as `<component>.md`; reference corresponding section IDs in `HLD.md`.

## Standard Workflow For New Artefact
1. Confirm prerequisites (e.g., Phase 2 requires Phase 1 inception docs baselined). If missing, log a question in change log before proceeding.
2. Clone the correct template from ` templates/` verbatim into target path.
3. Fill all sections; remove placeholder language; ensure traceability column(s) reference RTM IDs.
4. Update RTM: add requirement rows or link existing IDs to design/test/release columns as you progress phases.
5. Append change-log entry detailing: artefact name, phase, purpose, decisions, risk impact, and next reviewers.
6. Ensure approvals table is populated once stakeholder review completes; mark version baseline.

## Traceability & Consistency Rules
- Requirement IDs format: keep existing pattern (e.g., FR-###, NFR-###) – do not invent new schemes without change-log justification.
- When adding a backlog Story/Task: include a direct RTM reference plus originating Feature/Epic ID; cascade updates if renaming.
- If a term changes (e.g., component name), search repo and synchronise across BRD/PRD/SRS/NFR/HLD/LLD/test plan/RTM.

## Quality & Review Checklist (Apply Before Commit)
- All tables filled (no empty rows unless intentionally reserved and commented).
- RTM updated for each new requirement, design element, test, or operational control.
- Change log entry present for any non-trivial modification.
- No outdated template sections (e.g., leaving "Draft" after baseline approval).
- Directory naming and file placement follow phase conventions.

## Examples
- Creating a new LLD: copy ` templates/LLD.md` to `docs/design/LLD/auth-service.md`, fill sections, reference HLD component ID (e.g., COMP-AUTH-01) and RTM requirement IDs (FR-012, NFR-004).
- Adding a risk: update BRD risk table AND add corresponding risk entry in `docs/change-log.md` with owner & mitigation target date.

## Do / Avoid
- DO log open questions in change log with owners before proceeding.
- DO keep artefacts atomic (one document per template purpose).
- AVOID mixing design decisions into requirements docs; instead add ADR section in HLD and reference.
- AVOID copying historical templates from `templates-old/`.

## When Unsure
Add a clearly tagged question in change log (e.g., "OPEN: Need data retention policy for FR-045 – Owner: Security") and proceed with sections that are certain.

---
Provide feedback if any convention is unclear; these instructions should remain concise (~20–50 lines) and reflect current, observable practices only.