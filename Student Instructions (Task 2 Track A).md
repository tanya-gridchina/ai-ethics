# Task 2 · Track A: Modify the Ethics Assistant

## What This Task Asks

You have access to a working prototype of Scotiabank's AI Ethics Assistant — the same governance tool described in the case. Your task is to **modify the tool** to address one or more of the limitations or governance gaps you identified in your Task 1 critique.

You will use a generative AI coding assistant (Claude, ChatGPT, GitHub Copilot, or comparable) to make the changes. **You are not expected to write code from scratch.** The goal is to translate a governance design insight into a working change in the tool — not to demonstrate technical sophistication.

---

## What You Receive

| File | What It Is |
|------|-----------|
| `ethics_assessment.html` | The complete working prototype. Open it in any modern browser. |
| This file | Your instructions, the modification workflow, and a prompt template. |

The HTML file is fully self-contained — code and assessment data live in the same file. No installation, no server, no separate data file.

---

## Suggested Workflow

**1. Try the tool first.** Open `ethics_assessment.html` in a browser and complete an assessment for a hypothetical AI use case. Notice which questions feel inadequate, which scoring outcomes seem misaligned with the actual ethical risk, and which design decisions appear in the code.

**2. Decide what to change, and why.** Before opening the LLM, write 2–3 sentences naming the governance gap you intend to address and the modification you'll make. The strongest submissions connect a specific case finding (e.g., the AMCA Low score sitting alongside six unresolved flags, the human-in-the-loop mischaracterisation, the absence of generative-AI vocabulary) to a specific change in the tool.

**3. Make the change with an LLM.** Open Claude (or ChatGPT, etc.). Upload `ethics_assessment.html` to the chat. Use the prompt template below. Save the file the LLM returns.

**4. Test it.** Open the modified HTML in your browser. Complete an assessment. Confirm the change behaves as intended. If it doesn't, iterate with the LLM until it does.

**5. Write your reflection.** ~400 words covering the questions in the Deliverable section.

---

## Directions to Consider

The case identifies several governance gaps you might address. You may combine several or pursue a direction not listed here. The strongest submissions make a clear connection between a problem identified in the case and a particular modification to the tool.

- **Scoring & weighting.** Adjust how dimension scores are computed, how thresholds map to Low/Medium/High, or how the Overall Action Indicator combines dimensions. Address the case's central tension: a "Low" overall score coexisting with material unresolved flags.
- **Questions & dimensions.** Add questions that capture risks the current tool misses — generative AI, data provenance, deployment context, affected communities. Add a seventh dimension if the existing six cannot host the new content. Revise existing questions to reduce the self-reporting vulnerability.
- **User experience & guidance.** Change how action guidance is shown, make it harder to bypass, add contextual warnings when answer combinations suggest elevated risk, or redesign how results are communicated beyond a single score.
- **Structural changes.** Add a review step before submission. Create different paths for traditional ML vs. generative AI. Add fields for organisational context (deployment scale, affected population, regulatory environment).

---

## Prompt Template

Copy the prompt below into your LLM chat and attach `ethics_assessment.html`.

> I'm modifying a self-contained HTML prototype of an AI ethics assessment tool (attached). The file uses Chart.js for a radar chart and jsPDF for PDF export, with the assessment data inlined as a `const DATA = { ... }` object inside the same `<script>` block.
>
> Please make the following change and return the complete updated HTML file:
>
> **[Describe the change in plain English.]**
>
> Constraints:
> - Keep the file self-contained — no external data file, no new dependencies.
> - Preserve the existing structure: `dimensions` array, question types (`single_choice`, `multi_choice`, `multi_sub`, `text`), scoring thresholds, conditional questions.
> - Maintain the existing visual style.
> - If you add or remove a dimension, update `scoring.thresholds`, `config.dimension_colors`, and `scoring.overall_action_indicator.dimension_groups` consistently.
>
> Return the full HTML file in a single code block.

### Examples of change descriptions

- *"Add a new question to Acceptable Use: 'Does this use case generate synthetic content (text, image, audio, or video) that could be mistaken for human-produced output?' Yes scores 4, No scores 0. Add action guidance explaining the risks of synthetic content in financial communications."*
- *"Add a warning banner on the results page when the Overall Action Indicator is Low but any individual dimension is Medium or High. The banner should explain that the score may not reflect all governance risks identified."*
- *"Add a seventh dimension called 'Generative AI' with three questions covering hallucination risk, prompt injection exposure, and data provenance. Calibrate scoring so that High in this dimension forces the Overall Action Indicator to Medium or above."*
- *"Replace the human-oversight question (Acceptable Use Q3) with one that requires the submitter to attach a description of the human reviewer's role before they can advance, so that 'human-in-the-loop' cannot be selected without commitment to what that means."*

---

## Deliverable

Submit two items:

1. **Your modified `ethics_assessment.html`.** It must open in a browser and produce a complete assessment.

2. **A reflection of approximately 400 words** addressing:
   - What you changed and why — connect the modification to a specific governance gap or finding from the case.
   - What the change accomplishes in governance terms — how does it make the tool more effective at identifying, measuring, or communicating ethical risk?
   - What your experience using the AI coding assistant revealed — what the tool handled well, what required correction or iteration.
   - What the process suggested about the relationship between tool design and governance intent.

---

## Evaluation Criteria

| Criterion | What's Being Assessed |
|-----------|----------------------|
| **Governance reasoning** | Does the modification address a real governance gap identified in the case? Is the connection articulated, not assumed? |
| **Implementation quality** | Does the modified tool work? Are new questions well-written? Are scores calibrated thoughtfully? |
| **Critical reflection** | Does the reflection demonstrate honest engagement with trade-offs, including unintended consequences of the change? |
| **AI-collaboration insight** | Does the reflection show what working with an LLM revealed about the gap between design intent and execution? |

Technical sophistication is welcome but not required. A thoughtfully designed new question with calibrated scoring and clear guidance demonstrates as much governance understanding as a complex code change.

---

## Tips

- **Try to break the tool first.** Find a scenario where the current scoring produces a misleading result — that is where your modification should focus.
- **Re-read the AMCA appendix.** The six unresolved flags are a roadmap of concrete governance gaps the current tool fails to surface.
- **Think about who fills out the form.** The submitter is a model developer in a business unit, not an ethics specialist. Your modification should help that person reach a more accurate characterisation, not require them to already be one.
- **Keep your modification narrow.** A single well-executed change beats a sprawling rewrite. The reflection is where you demonstrate breadth.
- **Iterate with the LLM.** First-pass output is rarely correct. Read what came back, test it, ask the LLM to fix what didn't work.
