# Task 2 · Track B: Reimagine the Ethics Assistant

## What This Task Asks

You will produce a redesign specification for a substantially improved version of Scotiabank's AI Ethics Assistant. Your task is not to write code. It is to commit in writing to a vision for the next generation of this governance tool and to defend the trade-offs that vision entails.

This task builds directly on the critique you produced in Task 1. Having identified what the current tool gets wrong, you must now decide what would be better, and why.

---

## Required Components

Your proposal must address each of the following. The case states the minimums; the items below restate them with implementation prompts.

### 1. What the revised tool would assess that the current one does not

Identify at least two substantive gaps in what the current tool surfaces, for example, generative AI risks, data provenance, the local social and regulatory context of markets like Mexico and Latin America, or the experience of customers most likely to be harmed when AI systems fail (Indigenous, unbanked, underbanked individuals). For each gap, describe what new questions, dimensions, or assessment paths the revised tool would introduce and what risks they capture.

### 2. How would it handle the self-reporting problem

The AMCA case shows that submitters can characterize their own systems inaccurately, sometimes inadvertently, sometimes self-servingly, and the current tool depends on the AI & Ethics Governance team's review to catch this. Propose a concrete mechanism (or combination of mechanisms) that reduces the tool's structural reliance on self-reporting. Examples to consider, not be limited by: required documentation links, automated inconsistency detection, evidence-based questions ("attach the model card"), and independent verification triggers.

### 3. How would it communicate risk honestly without losing usability

The current tool produces a single score, displayed on a radar chart, with auto-generated action guidance. The score is technically accurate yet, and as the AMCA result demonstrates can mask material gaps. Propose how the revised tool should communicate risk to a non-specialist submitter. What does a score do well? What does it obscure? What would a more honest output look like, and what does it cost in usability?

### 4. The role of human reviewers under realistic bandwidth constraints

The AI & Ethics Governance team's review process catches things the tool does not, but their bandwidth is finite, and the volume of AI deployment is rising. Specify what the revised tool delegates to automation, what it escalates to a reviewer, and what the reviewer's role looks like: pre-submission consultation, structured triage, post-deployment audit, or some combination. Be specific about how the revised division of labour scales.

### 5. The normative anchor - make a choice and defend it

This is the centre of Julian's dilemma, and the case requires you to commit to a position. Which framework should anchor the next version of the Ethics Assistant?

- Scotiabank's own Data Ethics Commitment (the current anchor).
- The EU AI Act.
- Canada's AIDA.
- A new framework that explicitly centres the communities most likely to be affected - Indigenous customers, unbanked individuals, people in markets like Mexico and Latin America where local context is currently absent from the assessment.

**Pick one. Defend it.** The case is explicit: do not list options without committing. Name what your choice rules out, what it protects against, and why the trade-off is worth it.

---

## Deliverable

A redesign proposal of approximately **1,000 words**.

The proposal should be:

- **Structured.** Use headings that map to the components above. Treat them as sections, not bullet points.
- **Specific.** "Improve fairness monitoring" is not a redesign. "Require quantitative fairness assessment for the four attributes covered by Mexican non-discrimination law before submission can be marked complete" is.
- **Grounded in the case.** Cite AMCA, the six unresolved flags, the human-oversight mischaracterisation, the EU AI Act / AIDA references, the communities Julian names. Show that you read it.
- **Honest about trade-offs.** Improvements that increase rigour usually reduce usability. Improvements that reduce reviewer burden usually increase reliance on automated logic that may itself be imperfect. Name the cost of your choices.
- **Decisive.** A 1,000-word proposal that catalogues options without committing scores poorly.

---

## Evaluation Criteria

| Criterion | What's Being Assessed |
|-----------|----------------------|
| **Diagnostic fidelity** | Does the proposal correctly identify the most material gaps in the current tool, drawing on the case rather than abstract principles? |
| **Specificity** | Are the redesign moves concrete enough that someone could build them, or are they aspirational gestures? |
| **Normative commitment** | Does the proposal commit to a framework and defend the choice, including what it rules out, rather than listing options? |
| **Trade-off honesty** | Does the proposal name the costs of its own choices, especially the rigour-usability and automation-reviewer-bandwidth tensions? |
| **Case grounding** | Does the proposal demonstrate familiarity with the case's specifics  (AMCA, the six flags, Julian's framing) rather than treating it as a generic AI ethics scenario? |

---

## Tips

- **Open the tool before you start writing.** A short hands-on session with the prototype will sharpen your sense of what feels strong, what feels ad hoc, and where the seams show. You only need to inspect; Track A students will modify it.
- **Do not try to fix everything.** Two well-defended redesign moves beat seven shallow ones. The 1,000-word limit enforces selectivity.
- **The hardest section is the framework choice.** It is also the most differentiating. Most students hedge. The strongest proposals commit and live with the implications.
- **Centre the affected communities, or argue against doing so.** Julian names them explicitly. A proposal that ignores this question in either direction is incomplete.
