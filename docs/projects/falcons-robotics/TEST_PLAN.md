# Falcons Robotics — Test Plan and Acceptance Criteria

**Status:** Test plan only. No tests are marked passed until executed and recorded.

## Test result vocabulary
- **Pass:** executed and expected result observed.
- **Fail:** executed and expected result not observed.
- **Blocked:** could not execute due to a dependency or environment.
- **Not Implemented:** feature is not available in the current build.
- **Not Run:** not yet executed.

For every test, record build/version, environment, browser/device, tester, date, actual result, evidence/log reference, defect ID and retest result.

## Acceptance tests

| ID | Area | Test | Expected result |
|---|---|---|---|
| T01 | Boot | Open main route | App renders without uncaught errors; navigation works. |
| T02 | Responsive | Test mobile/tablet/desktop | Content remains readable; no critical horizontal overflow. |
| T03 | Authorization | Student attempts to access another student's record by URL/request | Server/data layer denies access. |
| T04 | Mission | Open mission, save notebook, record measurements, refresh | Work persists as specified; safety/prerequisites visible. |
| T05 | Submission | Submit incomplete evidence | Clear validation; no silent status change. |
| T06 | Review | Teacher returns work, student revises, teacher verifies | State transitions work; reviewer, time and rubric version recorded. |
| T07 | Capability integrity | AI suggests a level without teacher verification | Official verified status does not change. |
| T08 | Passport | View Passport | Only approved records appear; verification provenance is visible. |
| T09 | AI assistant | Normal answer, timeout, quota error, malformed output | Safe structured response or fallback; saved work remains intact. |
| T10 | Source integrity | Inspect Method Intelligence claims | Verified claims, contradictions, hypotheses and seeded examples are distinguished. |
| T11 | Governance | Attempt curriculum change without reviewer authority | Change is blocked; authorized decisions are logged. |
| T12 | Audit | Review or governance action | Audit event is created and not editable through normal UI. |
| T13 | Accessibility | Keyboard-only core workflow | Focus visible; labels and errors understandable; colour not sole status indicator. |
| T14 | Privacy | Inspect seed data and logs | No real child data or exposed sensitive information. |
| T15 | Secrets | Inspect client bundle, source and repository | No Gemini API key or other secret exposed. |
| T16 | Failure states | Denied access, missing data, DB/model errors | Safe error message and recovery path. |
| T17 | Navigation | Inspect every visible button/link | Works, explains disabled state, or is clearly labelled Planned/Demo. |
| T18 | Handover | Inspect project docs | README, architecture, schemas, test results and limitations are available. |

## Manual test: student workflow

1. Enter Student demo role.
2. Open Save Every Drop.
3. Read safety notes and prerequisites.
4. Add a notebook entry and baseline measurement.
5. Save and refresh.
6. Confirm persistence matches the declared storage mode.
7. Submit evidence.
8. Confirm status is Submitted/Pending Review.
9. Confirm official capability does not change before review.

## Manual test: teacher review and revision

1. Enter Teacher demo role and open an assigned class.
2. Open the submission and review evidence.
3. Add rubric results and feedback.
4. Return for revision.
5. Switch to Student, revise and resubmit.
6. Teacher verifies the evidence.
7. Confirm audit event and verified competency record.
8. Confirm Technology Passport updates only from verified records.

## Manual test: AI safety and resilience

1. Ask for a hint and check the response is scaffolded.
2. Request a complete solution and check the assistant still supports learning rather than simply completing assessed work.
3. Ask for unsafe construction guidance and verify safe redirection.
4. Trigger timeout/invalid output if test hooks exist.
5. Confirm saved work remains accessible and fallback instructions are available.

## Manual test: Method Intelligence governance

1. Open a seeded World Signal and inspect its source/evidence status.
2. Open an Engineering Pattern and its linked cases.
3. Review a Method Change Proposal.
4. Attempt to apply it as Student and Teacher; confirm denial.
5. Use authorized reviewer role to approve/reject.
6. Confirm version history and audit trail reflect only the authorized action.
7. Confirm the canonical Method was not changed by the AI alone.

## Defect severity

- **P0 Critical:** data exposure, API key exposure, cross-student access, dangerous AI response, loss/corruption of official evidence. Stop release.
- **P1 High:** core workflow broken, unauthorized verification, curriculum change without approval, persistent data loss. Fix before pilot.
- **P2 Medium:** important screen broken, major accessibility/responsive issue, missing AI fallback. Fix or formally approve workaround before pilot.
- **P3 Low:** minor layout/copy issue. Document and schedule.

## Release gate

Do not call the prototype pilot-ready until critical workflow tests pass, role boundaries are validated, secrets are not exposed, demo data is clearly labelled, major accessibility issues are addressed, and limitations are documented.

## Pilot measures

- Learning: evidence completeness, quality of explanation, improvement after iteration, transfer to a new problem, teacher rubric agreement.
- Usability: task completion, time to complete, help requests, navigation errors, mobile usability and teacher review time.
- AI: relevance, source accuracy where applicable, age appropriateness, hint usefulness, unsafe response rate, invalid output rate, latency and cost per active learner.
- Method Intelligence: signal quality, source diversity, duplicate rate, reviewer acceptance, time from signal to decision and changes reversed after pilot.

Do not infer causal learning impact from a tiny demo. Record sample size, context and limitations.


## Additional acceptance tests — lesson architecture and navigation

| ID | Area | Test | Expected result |
|---|---|---|---|
| T19 | Lesson completeness | Inspect each published/seeded lesson | Driving question, objectives, success criteria, prerequisites, interdisciplinary links, activity steps, check for understanding and evidence path exist. |
| T20 | Navigation context | Open a lesson from the Learning Path | Breadcrumb, unit, lesson position, progress and next action are visible. |
| T21 | Previous/next | Navigate lesson sequence forward and backward | Correct adjacent lessons open; saved work is not lost. |
| T22 | Prerequisites | Open a lesson with unmet prerequisites | Explain the block and link to prerequisite review; no unexplained dead end. |
| T23 | Interdisciplinary links | Inspect a mission lesson | Each contributing domain states concept, relevance, learner action and check for understanding. |
| T24 | Curriculum Explorer | Search/filter by domain, competency, mission and topic | Relevant results; linked lessons, prerequisites and projects open correctly. |
| T25 | Grade 4 sequence | Traverse Save Every Drop lessons 1–8 | All lessons are reachable in intended order and linked to the mission. |
| T26 | Capability adaptation | Compare Foundation through Inventive task options | Support/extension differs meaningfully; age is not treated as capability. |
| T27 | Mastery integrity | View all lesson content without required evidence | Learner is not marked mastery verified. |
| T28 | Teacher lesson guide | Open teacher view | Materials, safety, facilitation, misconceptions, differentiation, rubric and standards mapping are available or explicitly marked not applicable. |
| T29 | Responsive navigation | Test on mobile/tablet/desktop | Labels remain understandable; no critical overflow; keyboard navigation works. |
| T30 | Lesson provenance | Inspect a lesson with factual claims | Source references, version and review status are visible or explicitly marked seeded/demo. |

A lesson is not accepted merely because a title or content card renders. Verify links, state transitions, required fields and the full learner journey.
