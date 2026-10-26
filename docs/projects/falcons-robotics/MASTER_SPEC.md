# Falcons Robotics — Master Specification for Google AI Studio

**Version:** 1.0  
**Status:** Approved direction for prototype planning; implementation not yet verified.  
**Date:** 2026-10-25

## 1. Product vision

Falcons Robotics is a global future-technology learning ecosystem. It helps students learn to understand systems, connect science and engineering, solve authentic problems, design and build prototypes, test with evidence, learn from failure, improve solutions, and demonstrate verified capabilities.

**Method loop:** Observe → Understand → Model → Design → Build → Test → Learn → Adapt → Invent.  
**Supporting learning loop:** Learn → Simulate → Design → Build → Test → Fail safely → Improve → Explain → Invent.

Core principles:
- Problem-first engineering.
- No technology is taught in isolation.
- A robot operates inside an ecosystem.
- Read the system before trying to change it.
- Never confuse age with potential.
- Failure can generate data and discovery.
- Capability must be demonstrated with evidence, not assumed from grade completion.

## 2. Prototype goals

Build a responsive working application—not a static mockup—that demonstrates:
1. Public website and platform overview.
2. Student workspace and Grade 4 sample curriculum.
3. Global Problem Atlas with seeded examples.
4. Project mission and engineering notebook.
5. Bounded, age-appropriate Gemini learning assistant.
6. Evidence submission and teacher review.
7. Multidimensional capability profile and Technology Passport.
8. Teacher dashboard.
9. Falcons Method Intelligence demo workspace.
10. Setup, testing, known limitations and handover documentation.

## 3. Scope boundaries

### Build now
- Responsive homepage and app shell.
- Student, Teacher, Curriculum Reviewer and Administrator demo roles.
- Grade 4 curriculum nodes and a complete sample mission.
- Notebook entries, measurements, evidence submission, feedback and verification workflow.
- Competency rubric and Technology Passport preview.
- Seeded Method Intelligence records and change proposal workflow.
- Error/loading/empty states and basic accessibility.
- Persistent storage where supported and configured; otherwise a clearly labelled demo repository.

### Explicitly defer
- Unattended web crawling or autonomous research at scale.
- AI-authored curriculum changes deployed without human review.
- Automated high-stakes credentialing.
- Real student records before privacy/security approval.
- Live robotics hardware telemetry, payments, public social features, and government-scale analytics.
- Claims of real QR verification unless a working verification endpoint exists.

## 4. Roles and permissions

### Student
Can access assigned learning content, use the learning assistant, save notebook entries, submit evidence, view feedback, and view their own capability profile. Cannot self-verify work or edit official competency status.

### Teacher
Can access assigned classes, assign missions, review submissions, provide feedback, return work for revision, verify evidence against a rubric, and view class progress.

### Curriculum Reviewer
Can inspect source evidence and change proposals, request revisions, approve/reject proposals, and create a versioned release.

### Administrator
Can manage demo data and configuration. Administrative actions must be logged.

### AI assistant/agents
May coach, summarize, identify patterns, and recommend. They may not independently verify student work, update official competency status, award credentials, publish curriculum, or change the canonical Method.

Role hiding in the UI is not authorization. Enforce permissions at the data/server layer wherever authentication is implemented.

## 5. Required screens

### Public
Home, Platform, Falcons Method, Curriculum, For Schools, Global Problem Atlas, About, Contact/Request a Pilot.

### Student
Dashboard, My Learning Path, Curriculum Map, Project Missions, Mission Workspace, Engineering Notebook, AI Learning Assistant, Evidence & Feedback, Technology Passport.

### Teacher
Class Overview, Student Progress, Mission Assignment, Submission Review, Competency Matrix, Curriculum Resources.

### Method Intelligence
World Signals, Evidence Verification, Technology Radar, Engineering Patterns, Failure Intelligence, Curriculum Audit, Standards Mapping, Industry/Future Skills, Pedagogy, Method Evolution Proposals, Version History.

### Shared UI
Responsive navigation, demo-role selector, visible demo labels, search/filter where useful, breadcrumbs, accessible labels, loading/empty/success/error states, and no dead-end buttons.

## 6. First mission: Save Every Drop

**Title:** Save Every Drop: Build a Water-Smart Mini Garden.

**Problem:** A small garden must use less water while keeping plants healthy. Learners investigate how water moves, how materials absorb or drain water, and how measurements help compare solutions.

**Learning outcomes**
- State the problem and constraints.
- Separate observations from assumptions.
- Measure and compare water use.
- Explain basic water/material behaviour.
- Sketch and select a solution.
- Build a safe classroom prototype.
- Record tests, compare outcomes and propose an improvement.
- Explain a decision using evidence.

**Interdisciplinary connections:** science, mathematics, computing, engineering design, communication.

**Stages:** Observe → measure baseline → sketch two solutions → choose materials → build a safe model → test → record data → improve → explain.

**Safety:** Classroom-safe materials only. No mains electricity, chemical treatments, unsupervised sharp tools, or water/electronics combinations. Powered builds require an approved low-voltage kit and teacher supervision.

**Capability adaptations**
- Foundation: follow a guided plan and record observations.
- Developing: choose between two designs and compare measurements.
- Proficient: justify a design with evidence and propose a controlled improvement.
- Advanced: add a simple sensor or logic simulation.
- Inventive: propose and test an original variation with teacher approval.

**Required evidence:** problem statement, labelled sketch, material choice and reason, baseline/post-change measurements, test record, reflection on a failure/surprise, explanation/presentation, teacher rubric review.

## 7. Curriculum and capability model

Curriculum hierarchy: Domain → Strand → Competency → Learning Objective → Lesson/Resource → Prerequisite → Mission/Project → Rubric → Evidence.

Use multidimensional competencies, not a single global student score. Suggested dimensions: mathematics, physics, chemistry/materials, programming, electronics, robotics, design, systems thinking, communication and collaboration.

Capability statuses: **Foundation → Developing → Proficient → Advanced → Inventive**. These are not grade or age labels. A learner may be Advanced in programming and Foundation in chemistry.

Minimum competency record:
- student_id
- competency_id
- current_status / suggested_status
- evidence_count
- assessment_result
- teacher_verified
- last_assessed_at
- rubric_version
- evidence_ids

Only approved human review updates the official verified status.

## 8. Falcons Method Intelligence Engine

Purpose: monitor research, technologies, engineering cases, failures, industry skills, standards and learning science; detect cross-domain patterns; recommend curriculum/Method improvements while preserving governance.

Prototype agent roster:
1. World Signal Agent
2. Evidence & Verification Agent
3. Technology Radar Agent
4. Engineering Pattern Agent
5. Failure Intelligence Agent
6. Curriculum Auditor Agent
7. Standards & Policy Agent
8. Industry & Future Skills Agent
9. Pedagogy & Learning Science Agent
10. Method Evolution Agent
11. Project Intelligence Agent
12. World-to-Classroom Compiler Agent

For the first prototype, use structured records and seeded examples. Do not claim that seeded examples are live global monitoring.

Every agent contract must define purpose, allowed inputs/tools, output schema, source references, confidence, validation, failure behaviour, permission scope, escalation and audit event.

Governance lifecycle:
**Discovered → Evidence checked → Pattern identified → Educational relevance assessed → Change proposal → Human review → Pilot → Measure → Approve/revise/reject → Versioned release.**

No agent can silently change the canonical curriculum or Method.

## 9. Shared data entities

Implement typed models with stable IDs, timestamps, version/status fields, and created_by where relevant:
- User
- School
- Competency
- CurriculumNode
- Mission
- NotebookEntry
- EvidenceSubmission
- CompetencyRecord
- TechnologyPassport
- WorldSignal
- VerifiedClaim
- EngineeringPattern
- FailureCase
- MethodChangeProposal
- AuditEvent

Suggested key fields:
- User: id, display_name, role, school_id, grade_context, locale, status.
- Competency: id, title, description, domain, prerequisites, rubric_id, version, status.
- Mission: id, title, problem_statement, constraints, safety_notes, prerequisites, competencies, stages, evidence_requirements, rubric_id, version, status.
- EvidenceSubmission: id, student_id, mission_id, evidence_refs, reflection, status, submitted_at, reviewed_by, review_at, rubric_results, feedback.
- CompetencyRecord: id, student_id, competency_id, suggested_status, verified_status, evidence_ids, assessor_id, rubric_version, last_assessed_at.
- MethodChangeProposal: id, target_version, rationale, evidence_ids, proposed_change, impact_assessment, risks, status, reviewer_id, decision_notes.
- AuditEvent: id, actor_id, action, target_type, target_id, timestamp, reason, before_after_summary.

## 10. AI assistant contract

The assistant is an engineering coach, not an answer vending machine.

It should ask what the learner observed, offer a hint before a complete solution, explain unfamiliar terms, connect science to the mission, encourage safe experimentation, and ask for evidence-based reflection.

Structured response:
- short_explanation
- next_question
- hint
- suggested_action
- safety_note
- related_competency_ids
- uncertainty_note

Validate model output before rendering. Handle timeout, rate limits, malformed output and permission errors without losing saved work. Never fabricate facts, citations, measurements, test results, or completion status. Keep API keys server-side.

## 11. Technical approach

- Frontend: responsive React-based web app generated in AI Studio Build mode, with reusable components and design tokens.
- Server: server-side runtime for Gemini calls and secret-bearing integrations.
- AI: replaceable service wrapper; structured output where appropriate; schema validation, timeout and error handling.
- Auth/storage: Firebase Authentication and Firestore if enabled and configured. A labelled demo data layer is acceptable for initial interaction testing.
- Repository: keep master specification, prompts, decisions, tests, limitations and release notes under version control.
- Deployment: use AI Studio preview first; deployment to Cloud Run is a separate step requiring current documentation, account/billing checks and configuration.

Do not treat AI Studio as a substitute for production security, observability, backups, cost controls or operational ownership.

## 12. Privacy, safety, accessibility and reliability

- Use demo identities; do not use real child records without approved privacy/security controls.
- Enforce role authorization on the server/data layer, not only in the UI.
- Keep secrets out of browser code, repository, prompts and logs.
- Use age-appropriate AI guidance and safe project constraints.
- Log official review, governance and administrative decisions.
- Handle loading, empty, offline, denied, rate-limit, timeout, malformed response and database-error states.
- Target WCAG 2.2 AA where feasible: keyboard navigation, visible focus, contrast, labels, scalable text and meaningful alt text.
- Before school deployment, conduct jurisdiction-specific privacy, child-safety, accessibility, IP and education-compliance review.

## 13. Definition of done

A reviewer can reproduce the build, run the core manual test, see actual results, understand which features are implemented versus demo/planned, and identify the next step without relying on undocumented chat history.

Do not claim a feature is complete because it appears on screen or the project compiles. Verify runtime behaviour and record evidence.


## 14. Required lesson structure, interdisciplinary links and navigation

The canonical lesson and navigation requirements are defined in [LESSON_ARCHITECTURE.md](LESSON_ARCHITECTURE.md). This is a required part of the platform specification, not an optional future enhancement.

Required hierarchy: Learning Path → Unit/Mission Theme → Real-World Challenge → Interdisciplinary Module → Lesson → Activity/Experiment/Simulation → Project Stage → Assessment → Evidence → Competency → Technology Passport.

Every lesson must include a driving question, real-world relevance, observable objectives, success criteria, prerequisites, interdisciplinary connections, key concepts, exploration, explanation/modeling, guided activity, application/build/simulation, testing and data, analysis/improvement, explanation, check for understanding, assessment/evidence, reflection/transfer, next step, teacher guide and source/provenance information.

The interdisciplinary domains are Natural Sciences (including Chemistry), Mathematics & Data, Computing & Digital Systems, Engineering & Design, Frontier Technologies, Human/Creative/Society, and Innovation & Enterprise. For each contributing domain, explain the concept, why the mission needs it, what the learner does with it, and how it is checked.

Student and teacher navigation, lesson states, capability-based differentiation, curriculum explorer filters, the Grade 4 Save Every Drop sequence, lesson data contract and acceptance criteria are mandatory. Build and test this structure before expanding the content library.
