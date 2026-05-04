# Instructor Guide · Task 2 · Track A

## Pedagogical Aim

Track A puts the Ethics Assistant prototype in students' hands and asks them to modify it using a generative AI coding assistant. The aim is not to teach coding. It is to force students to engage with the design decisions embedded in a governance tool by making them change those decisions and observe the consequences.

When a student decides to change a score from 3 to 5, they must articulate why the current weight is wrong and what governance outcome the new weight produces. When they add a question, they must define what risk it captures and how it interacts with existing scoring logic. The tool becomes a medium for governance reasoning, not an end in itself. The LLM handles the syntax; the student owns the design decision.

**Recommended for:** courses where students have, or are developing, experience with AI-assisted software development.
**Session length:** 75–120 minutes (can be split across two sessions).
**Class size:** 15–60 students; individually or in teams of 2–3.
**Prerequisites:** Students must have read the case (especially Appendices B and C) and completed Task 1.

---

## Session Structure

### Phase 1 · Orientation (15 min)
- Live demo: open `ethics_assessment.html`, walk through one dimension, show the radar chart and PDF export.
- Live demo: make one trivial change with the prompt template — e.g., reword a question — and reload to show the before/after. This demystifies the workflow and signals that the task is accessible.
- Reinforce: the quality of the governance reasoning matters more than the technical sophistication of the change.
- Common early question — *"Do I need to know how to code?"* Answer: no. The LLM generates the code. The student decides what to change and why.

### Phase 2 · Planning (15–20 min)
- Ask students to re-read the six unresolved AMCA flags (Appendix C) and identify which ones the current tool fails to surface.
- Each student or team writes a 2–3 sentence change proposal: what they will modify and what governance gap it addresses.
- The strongest proposals tend to focus on:
  1. The disconnect between a Low overall score and unresolved flags.
  2. The self-reporting vulnerability illustrated by the human-oversight mischaracterisation.
  3. Missing coverage for generative AI, data provenance, or deployment context.
  4. How results are communicated — what a score means versus what users assume it means.

### Phase 3 · Implementation (30–50 min)
- Students work individually or in teams of 2–3 with their LLM of choice.
- Circulate actively. Watch for and correct:
  - Students who change scores arbitrarily without governance justification — ask them to defend every number.
  - Students who add questions that duplicate existing ones — ask what new risk theirs captures.
  - Students who focus on UI or aesthetics — redirect to governance substance.
  - Students who get stuck with the LLM — pair them with a more confident peer.

### Phase 4 · Test and Reflect (15–20 min)
- Each student completes a full assessment with their modified tool. They should test at least two scenarios — one expected to score Low and one expected to score High — and verify the modification produces the intended effect.
- If a modification doesn't change outcomes as intended, that is worth surfacing in the reflection. Why didn't it? What does that reveal about the scoring architecture?
- Students begin the 400-word reflection (completed after class).

### Phase 5 · Debrief (15–20 min, optional)
- Ask 3–4 teams to present their modification (2–3 min each): what they changed, why, what they learned.
- Facilitate around recurring themes:
  - Did increased rigour reduce usability? (The rigour-usability trade-off)
  - Did anyone's change inadvertently create a new gap? (Unintended consequences in governance design.)
  - Did the process of assigning scores and thresholds reveal anything about how "risk" is quantified?

### Suggested Debrief Questions
- *"How did it feel to assign a number to an ethical risk? What did the process reveal about quantification in governance?"*
- *"If a business-unit submitter fills out your modified tool honestly, would your changes catch AMCA-type problems?"*
- *"What is the difference between a tool that catches problems and a tool that helps people think differently about their systems?"*

---

## Assessment Rubric

| Criterion | Excellent (A) | Good (B) | Adequate (C) | Insufficient |
|-----------|---------------|----------|--------------|--------------|
| **Governance reasoning** | Modification addresses a clearly identified gap with explicit connection to the case. Trade-offs articulated. | Rationale present but connection to case could be sharper. | Some reasoning, but vague or disconnected from the case. | No clear rationale; changes appear arbitrary. |
| **Implementation** | Tool works correctly. New content well-written, scores calibrated, guidance meaningful. | Tool works. Content functional but could be more polished. | Tool mostly works; minor issues. Content rough. | Tool broken or changes invisible. |
| **Critical reflection** | Genuine insight about governance tool design. Honest about limitations. | Addresses required points with reasonable depth. | Present but superficial. | Missing or fails to engage with the substance. |
| **AI-collaboration insight** | Clear account of where the LLM helped, where it failed, and what that revealed. | Some account; less developed. | Mentioned in passing. | Not addressed. |

---

## Pre-Session Checklist

- [ ] Students have read the case (especially Appendices B and C) and completed Task 1.
- [ ] Students have access to `ethics_assessment.html` (via repository, LMS, or download).
- [ ] Students have access to at least one LLM (Claude, ChatGPT, or comparable).
- [ ] You have completed the assessment yourself and made one test modification using the prompt template.
- [ ] Projector or screen available for the live demo.

---

## Materials Provided to Students

| File | Purpose |
|------|---------|
| `ethics_assessment.html` | The working prototype (single self-contained file). |
| `Student Instructions (Task 2 Track A).md` | Workflow, prompt template, deliverable, evaluation criteria. |
