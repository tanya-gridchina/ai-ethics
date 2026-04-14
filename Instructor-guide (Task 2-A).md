# Instructor Guideline (Task 2, Track A)

## Teaching and Monitoring the Session

---

### Overview

In this task, students modify a working prototype of the AI Ethics Assistant using a generative AI coding assistant. The pedagogical goal is not to teach coding but to force students to engage with the **design decisions embedded in a governance tool** by making them change those decisions and observe the consequences.

When a student decides to change a score from 3 to 5, they must articulate *why* the current weight is wrong and *what governance outcome* the new weight produces. When they add a question, they must define what risk it captures and how it interacts with the existing scoring logic. The tool becomes a medium for governance reasoning, not an end in itself.

**Expected session duration:** 75–120 minutes (can be split across two sessions)
**Class size:** 15–60 students, individually or in teams of 2–3
**Prerequisites:** Students should have read the case and used the tool at least once before this session

---

### Session Structure

#### Phase 1: Orientation (15 minutes)

**Objective:** Ensure all students can access and run the tool, and understand the modification workflow.

- Distribute the files (or direct students to the GitHub repository)
- Live demo: open `ethics_assessment.html` in a browser, walk through one dimension, show the results page and spider chart
- Live demo: make one simple change using the prompt template — e.g., change a question's wording. Show the before/after. This demystifies the process and signals that the task is accessible.
- Emphasize: **the quality of the governance reasoning matters more than the technical sophistication of the change**

**Common early question:** "Do I need to know how to code?"
**Answer:** No. The prompt template is designed so you describe changes in plain English. The LLM generates the code. Your job is to decide *what* to change and *why*.

#### Phase 2: Exploration and Planning (15–20 minutes)

**Objective:** Students identify what they want to change and why.

- Ask students to complete a brief assessment using the tool (if they haven't already)
- Prompt them to re-read the six unresolved flags from the AMCA case (Appendix C) and identify which ones the current tool fails to address
- Students should write a 2–3 sentence "change proposal" before touching the tool — what they plan to modify and what governance gap it addresses
- Circulate and check proposals. Redirect students who are too vague ("make it better") or too ambitious ("rebuild everything")

**Instructor tip:** The strongest modifications typically focus on one of these areas:
1. The disconnect between a Low overall score and unresolved governance flags
2. The self-reporting vulnerability (AMCA's human oversight mischaracterization)
3. Missing coverage for specific risks (GenAI, data provenance, deployment context)
4. How results are communicated — what a score means vs. what users think it means

#### Phase 3: Implementation (30–50 minutes)

**Objective:** Students make their modifications using the LLM-assisted workflow.

- Students work individually or in teams of 2–3
- They use Claude, ChatGPT, or another tool to modify the HTML file
- Circulate actively — this is where most support is needed

**What to watch for:**
- Students who change scores arbitrarily without governance reasoning — ask them to justify every number
- Students who add questions that duplicate existing ones — ask what new risk their question captures
- Students who focus exclusively on UI/aesthetics — redirect to governance substance
- Students who are struggling with the tool — pair them with a more technically confident peer

#### Phase 4: Testing and Reflection (15–20 minutes)

**Objective:** Students verify their modifications work and write their reflection.

- Ask students to complete a full assessment with their modified tool
- They should test at least two scenarios: one that should score Low and one that should score High
- If a modification doesn't change the outcomes as intended, that's worth discussing — why not? What does that reveal about the scoring architecture?
- Students begin their 400-word reflection (can be completed after class)

#### Phase 5: Debrief (15–20 minutes, optional)

**Objective:** Reveal insights about governance tool design through student presentations.

- Ask 3–4 teams to present their modification in 2–3 minutes each: what they changed, why, and what they learned
- Facilitate discussion around recurring themes:
  - Did anyone find that adding rigor made the tool harder to use? (The rigor-usability trade-off)
  - Did anyone's change inadvertently create a new problem? (Unintended consequences in governance design)
  - Did the process of deciding scores and thresholds reveal anything about how "risk" is defined and measured?

**Key debrief questions:**
- "How did it feel to assign a number to an ethical risk? What did that process reveal about the nature of quantification in governance?"
- "If a business unit submitter fills out your modified tool honestly, would your changes catch the AMCA-type problems? Why or why not?"
- "What's the difference between a tool that catches problems and a tool that helps people think differently about their systems?"

---

### Assessment Rubric

| Criterion | Excellent (A) | Good (B) | Adequate (C) | Insufficient |
|-----------|---------------|----------|--------------|-------------|
| **Governance Reasoning** | Modification addresses a clearly identified governance gap with explicit connection to the case. Trade-offs are articulated. | Governance rationale is present and reasonable but connection to the case could be sharper. | Some governance reasoning, but vague or disconnected from the case. | No clear governance rationale; changes appear arbitrary. |
| **Implementation** | Tool works correctly. New questions are well-written with calibrated scores and meaningful guidance. | Tool works. New content is functional but could be more polished. | Tool mostly works but has minor issues. Content is present but rough. | Tool is broken or changes are not visible. |
| **Critical Reflection** | Reflection demonstrates genuine insight about governance tool design. Honest about limitations. | Reflection addresses the required points with reasonable depth. | Reflection is present but superficial. | Missing or fails to engage with the substance. |
| **Ambition** | Attempts something non-obvious that reveals governance insight. | Makes meaningful changes that go beyond the minimum. | Meets the basic requirements. | Minimal effort. |

---

### Pre-Session Checklist

- [ ] Students have read the full case including Appendices B and C
- [ ] Files are distributed (via GitHub repo, LMS, or direct download)
- [ ] Students have verified they can open `ethics_assessment.html` in a browser
- [ ] Students have access to at least one GenAI tool (Claude, ChatGPT, or comparable)
- [ ] You have completed the assessment yourself and made at least one test modification
- [ ] Projector/screen available for the live demo in Phase 1

---

### Materials Provided to Students

1. `ethics_assessment.html` — The working prototype (single self-contained file)
2. `assessment_data.js` — Standalone data file for LLM prompt workflows
3. `PROMPT_TEMPLATE.md` — Ready-to-use prompts for data changes, UI changes, or both
4. `STUDENT_GUIDE.md` — Technical reference for editing
5. `Student Instructions (Task 2-A).md` — This task's instructions, deliverables, and evaluation criteria
