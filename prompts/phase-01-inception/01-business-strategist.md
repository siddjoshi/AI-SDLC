# Phase 1.1 – Business Strategist Prompt (Business Case, Vision & Goals)

## Context
- **Phase Sequence:** First activity in the SDLC pipeline. No prior artefacts beyond raw opportunity intake.
- **Upstream Inputs:** Idea brief, market opportunity notes, executive mandate (if available).
- **Downstream Dependencies:** Outputs feed ` templates/BRD.md`, ` templates/PRD.md`, and stakeholder alignment activities.
- **Workspace Templates & References:**
  - ` templates/BRD.md` (KPI table, scope framing)
  - Repository `README.md` (mandatory inception artefacts)

## Objective
Produce a Business Case and Vision & Goals package that quantifies value, defines success metrics, and shapes all subsequent requirements work without needing any further prompts.

## Step-by-Step Instructions
1. **Review Repository Guidance**
   - Open `README.md` to confirm inception deliverables, compliance needs, and cross-phase dependencies.
   - Note mandatory artefacts (Business Case, Vision & Goals, Stakeholder Register) and the KPIs referenced downstream.
2. **Analyse Opportunity & Market**
   - Summarise the problem/opportunity, target segments, personas, and market landscape.
   - Record regulatory or compliance triggers that must appear in later phases.
3. **Draft the Business Case**
   - Create `docs/inception/business-case.md` if it does not exist.
   - Populate executive summary, strategic alignment, qualitative benefits, quantitative ROI, cost estimates, risks, and assumptions.
   - Include a KPI table with baseline, target, measurement cadence, and data sources; ensure KPI IDs can map into the BRD.
4. **Author the Vision & Goals Document**
   - Create `docs/inception/vision-and-goals.md`.
   - State product vision, guiding principles, business objectives, and explicit success criteria tied to the Business Case KPIs.
   - Highlight key personas and journeys that will be elaborated in the PRD.
5. **Document Dependencies & Open Questions**
   - Append a section listing dependencies for stakeholder alignment, compliance reviews, technology assessments, and funding gates.
   - Flag unanswered questions with owners and due dates so future agents can resolve them.
6. **Publish Change Log & Approvals**
   - Add version metadata (0.1 Draft → 1.0 Baseline) and capture approval stakeholders aligned with the forthcoming Stakeholder Register.

## Deliverables
- `docs/inception/business-case.md`
- `docs/inception/vision-and-goals.md`
- Embedded change log and approval tables within each document.

## Traceability & Handover Requirements
- Cross-reference KPI IDs and success metrics that must feed into ` templates/BRD.md` and ` templates/PRD.md`.
- Provide a dependency list for the Portfolio Manager prompt (Stakeholder Register, RACI, Comms Plan).
- Update or create `docs/change-log.md` with a summary of decisions and approvals.

## Completion Criteria
- Business Case and Vision & Goals documents are complete, versioned, and stored under `docs/inception/` with no placeholder text.
- KPIs, risks, and assumptions are explicitly tied to future artefacts (mention template names and sections).
- Dependencies and outstanding questions are enumerated with owners and due dates.

## Parallelisation Notes
- This prompt must complete before any other SDLC prompt begins. Subsequent prompts reference its artefacts; do not proceed to Phase 1.2 until Business Case and Vision & Goals are baselined.
