# Google AI Studio Build Prompts — Falcons Robotics

Use these prompts one at a time in Google AI Studio Build mode. First apply the main prompt, inspect the generated project, then proceed in small steps. Do not ask the builder to rewrite the whole app at each stage.

## Master prompt

Build a responsive full-stack web application named **Falcons Robotics — Future Technology Learning Platform**. This is a working prototype, not a static landing-page mockup.

Purpose: help Grade 4–12 learners develop real engineering capability through interdisciplinary, project-based learning. Start with a complete Grade 4 mission, while using data structures that can scale to other grades and jurisdictions.

Design: premium mobile-first interface using deep navy, white, gold accents, restrained blue/teal/green/purple accents, accessible contrast, clear typography, generous whitespace and an eagle-inspired brand identity. Do not copy another company's proprietary design.

Create these pages:
1. Public Home: hero, platform overview, Falcons Method, features, sample mission, school CTA.
2. Student Dashboard: learning path, assigned missions, notebook entries, feedback and capability profile.
3. Curriculum Map: domains, competencies, prerequisites and learning objectives.
4. Global Problem Atlas: filterable seeded problems linked to science, constraints and projects.
5. Mission Workspace: problem, constraints, prerequisites, safety, stages, notebook, measurements, evidence and reflection.
6. AI Learning Assistant: scaffolded, age-appropriate coaching; server-side Gemini calls; validated output; graceful failures.
7. Teacher Dashboard: class overview, pending submissions, progress and competency matrix.
8. Submission Review: evidence, rubric, feedback, verify/return-for-revision actions and audit history.
9. Technology Passport: verified projects and competencies; label demo data; don't claim external/cryptographic verification unless implemented.
10. Method Intelligence: seeded World Signals, Evidence Bundles, Engineering Patterns, Failure Cases, Curriculum Gap Reports and Method Change Proposals.
11. Admin/Settings: demo role selection, app status and demo-data reset.

Implement **Save Every Drop: Build a Water-Smart Mini Garden** with problem statement, constraints, interdisciplinary learning, baseline measurement, design sketch, safe prototype, testing, comparison, iteration and reflection. Include Foundation, Developing, Proficient, Advanced and Inventive capability adaptations. Include child-appropriate safety guidance and teacher supervision requirements.

Roles: Student, Teacher, Curriculum Reviewer and Administrator. Use a labelled demo role selector if real authentication is not configured. Never represent demo mode as secure production authentication.

Use typed models for User, School, Competency, CurriculumNode, Mission, NotebookEntry, EvidenceSubmission, CompetencyRecord, TechnologyPassport, WorldSignal, VerifiedClaim, EngineeringPattern, MethodChangeProposal and AuditEvent. Seed a small dataset.

AI may coach, summarize and propose. AI must not independently verify student work, change official capability status, award credentials, publish curriculum or change the canonical Method. Human approval is required for official decisions.

Implement real navigation, forms, filters, notebook saving, submission workflow, teacher review actions, status changes and audit events. If a feature is not implemented, label it Demo, Planned or Not connected. Persist data with Firebase/Firestore if supported and configured; otherwise use a clearly labelled demo data layer with a replaceable storage adapter. Keep Gemini secrets server-side.

Use reusable components, responsive/accessibility patterns, loading/empty/error states, input validation and modular services. Add automated tests for critical workflows if supported. Create a README with setup, architecture, environment variables, data model, known limitations, manual test steps and deployment notes. Do not claim tests passed unless executed. Before finishing, inspect the app, fix build/runtime errors, and report implemented/unimplemented features and actual test results.

Build in stages: app shell and navigation first; then mission → notebook → submission → teacher review → verified competency record → Technology Passport. Next add AI coaching and Method Intelligence. Preserve working functionality.

## Follow-up prompt 1 — inspect and stabilize

Inspect the existing project before changing it. List current routes, components, data models, persistence, AI calls and tests. Run available checks. Fix build/runtime errors first. Do not redesign or remove working features without explaining why. Report only verified results.

## Follow-up prompt 2 — complete mission workflow

Implement Save Every Drop as an end-to-end vertical slice. Students save notebook entries, record measurements, submit evidence and see submission status. Teachers review, add rubric results, return for revision or verify. Each decision creates an audit event. Use persistent storage if configured; otherwise use a clearly labelled demo repository.

## Follow-up prompt 3 — AI coach

Implement a server-side Gemini-powered Falcons Learning Assistant. Use age-appropriate scaffolded coaching, ask questions before complete solutions, include safety reminders, validate structured output, handle timeout and invalid output, and never update official competency records. Keep secrets server-side. Add tests for success, timeout and malformed output.

## Follow-up prompt 4 — Technology Passport

Implement the Technology Passport from verified project and competency records only. Distinguish AI suggestions from teacher-verified achievement. Include evidence links, rubric version, reviewer and verification date. Never fabricate a QR verification service; label any mock QR as demo.

## Follow-up prompt 5 — Method Intelligence

Implement a demo workspace for the 12 Falcons Method Intelligence agents using seeded records and typed schemas. Each record shows evidence/source status, confidence, creation time and permission scope. Provide a Method Change Proposal workflow. No live crawling and no automatic curriculum edits in this phase.

## Follow-up prompt 6 — responsive/accessibility audit

Audit every route at mobile, tablet and desktop widths. Check keyboard navigation, focus visibility, contrast, form labels, error messages, text scaling and navigation overflow. Fix issues and report tested viewports and remaining limitations.

## Follow-up prompt 7 — QA and handover

Run available build, lint, type and automated tests. Inspect all navigation links and buttons. Test student submission, teacher verification, revision cycle, Passport update, AI failure fallback and role permissions. Do not mark tests passed unless executed. Produce release checklist, defect list, setup instructions and known-limitations register.
