# Task 2, Track A: Modify the Ethics Assistant

## Participant Handout

---

### Your Mission

You have access to a working prototype of Scotiabank's AI Ethics Assistant — the same governance tool described in the case. Your task is to **modify the tool** to address one or more of the governance gaps identified in the case, or to improve the tool in a direction you believe makes it more effective.

You will use a generative AI coding assistant (Claude, ChatGPT, GitHub Copilot, or comparable) to make your changes. You are not expected to write code from scratch.

---

### What You Receive

| File | Description |
|------|-------------|
| `ethics_assessment.html` | The complete working prototype — open it in a browser to try it |
| `assessment_data.js` | A standalone copy of the assessment data for use with LLM prompts |
| `PROMPT_TEMPLATE.md` | Ready-to-use prompt templates for asking an LLM to make changes |
| `STUDENT_GUIDE.md` | Technical reference: file structure, question types, how to edit |

Start by **using the tool yourself** — complete an assessment for a hypothetical AI use case to understand how it works before modifying it.

---

### Types of Changes You Can Make

Here are some directions to consider. You may combine several, or pursue a direction not listed here. The strongest submissions make a clear connection between a governance problem identified in the case and a concrete modification to the tool.

**Scoring & Weighting**
- Adjust how dimension scores are calculated or how thresholds map to Low/Medium/High
- Change how the Overall Action Indicator combines dimension-level results
- Address the case's core tension: a "Low" score coexisting with unresolved governance flags

**Questions & Dimensions**
- Add new questions to capture risks the current tool misses (e.g., GenAI-specific risks, data provenance, deployment context)
- Add an entirely new seventh dimension
- Revise existing questions to reduce the self-reporting vulnerability highlighted in the AMCA case

**User Experience & Guidance**
- Change how action guidance is presented — make it harder to bypass or ignore
- Add contextual warnings when answer combinations suggest elevated risk
- Redesign how results are communicated (beyond a single score)

**GenAI Integration**
- Incorporate generative AI features into the tool itself (e.g., an AI assistant that helps users answer questions, flags potential inconsistencies, or generates a narrative risk summary)
- Note: this is more technically ambitious and would involve API calls

**Structural Changes**
- Add a review/summary step before final submission
- Create different assessment paths for different system types (traditional ML vs. GenAI)
- Add fields that capture organizational context (deployment scale, affected population, regulatory environment)

---

### How to Make Changes

#### Level 1: Data-Only Changes (Recommended Starting Point)
Edit the data section directly in the HTML file, or use the prompt template to ask an LLM:

> *Example: "Add a new question to the Acceptable Use dimension: 'Does this use case generate content that could be mistaken for human-produced output?' with Yes scoring 4 and No scoring 0, and add action guidance explaining the risks of synthetic content in financial communications."*

#### Level 2: LLM-Assisted Code Changes
For structural or UI changes, upload the HTML file to your LLM with a description:

> *Example: "Add a warning banner that appears on the results page when the overall score is Low but any individual dimension is Medium or High, explaining that the score may not fully reflect the governance risks identified."*

#### Level 3: Direct Code Editing
If you're comfortable with HTML/CSS/JavaScript, edit the code directly. Key areas are documented in `STUDENT_GUIDE.md`.

---

### Deliverable

Submit **two items**:

1. **Your modified `ethics_assessment.html` file** — it should be a working tool that can be opened in a browser.

2. **A written reflection of approximately 400 words** addressing:
   - What you changed and why — connect your modifications to specific governance gaps or limitations identified in the case
   - What the change accomplishes in governance terms — how does it make the Ethics Assistant more effective at identifying, measuring, or communicating AI risk?
   - What trade-offs your modifications introduce — does increased rigor come at the cost of usability? Does a new dimension create assessment fatigue? Be honest about limitations
   - What you learned about AI governance tooling from the process of modifying this tool

---

### Evaluation Criteria

Your work will be assessed on:

| Criterion | What We're Looking For |
|-----------|----------------------|
| **Governance reasoning** | Does the modification address a real governance gap? Is the connection to the case clearly articulated? |
| **Implementation quality** | Does the modified tool work? Are new questions well-written? Are scores calibrated thoughtfully? |
| **Critical thinking** | Does the reflection demonstrate understanding of the trade-offs inherent in governance tool design? |
| **Ambition & creativity** | Did you attempt something meaningful, even if the execution is imperfect? |

Note: Technical sophistication is valued but not required. A thoughtfully designed new question with well-calibrated scoring and clear action guidance demonstrates as much governance understanding as a complex code change.

---

### Tips

- **Start by breaking the tool.** Find a scenario where the current scoring produces a misleading result — this is where your modification should focus.
- **Read the AMCA case carefully.** The six unresolved flags listed in the case are a roadmap of governance gaps the current tool doesn't fully address.
- **Think about the user.** The person filling out this assessment is a model developer in a business unit, not an ethics specialist. How does that shape what your modification should look like?
- **Test your changes.** After modifying the tool, complete an assessment and verify that your changes produce the intended effect on the scores and user experience.
- **Use the prompt template.** It's designed to produce working results. Describe what you want in plain English — the LLM will handle the code.
