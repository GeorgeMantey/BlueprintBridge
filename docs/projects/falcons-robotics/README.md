# Falcons Robotics — Google AI Studio Prototype

**Status:** Prototype specification; implementation and test results are not yet verified.  
**Specification version:** 1.0  
**Date:** 2026-10-25

Falcons Robotics is a future-technology learning ecosystem built around real-world problems, interdisciplinary STEM, project-based learning, capability evidence, and human-governed curriculum evolution.

## Documents
- [Master specification](MASTER_SPEC.md)
- [Google AI Studio build prompts](AI_STUDIO_PROMPTS.md)
- [Test plan and acceptance criteria](TEST_PLAN.md)

## First vertical slice
Student learns → designs a water-saving mini garden → records measurements and evidence → submits work → teacher reviews and verifies → verified capability appears in the Technology Passport.

## Build approach
1. Open [Google AI Studio](https://aistudio.google.com/) and use Build mode.
2. Apply the master prompt, then use the follow-up prompts one at a time.
3. Test each critical workflow before expanding scope.
4. Export/sync the code to GitHub and keep this repository as the canonical project record.
5. Record actual test outcomes; never claim a test passed unless it was run.

## Non-negotiable safeguards
- AI may coach and recommend; it cannot independently verify student work, award official credentials, publish curriculum, or modify the canonical Falcons Method.
- Clearly label demo data and simulated integrations.
- Do not use real child data in the prototype without approved privacy/security controls.
- Keep Gemini API keys server-side and out of source control.
- No phantom features: visible controls must work, be disabled with an explanation, or be labelled planned.
- This specification is not proof that an application has been built, deployed, or tested.
