# Prompt Template for Modifying the AI Ethics Assistant

Use this prompt when you want Claude (or another LLM) to help you make changes to the tool. Copy the section below, fill in the `[DESCRIBE YOUR CHANGES]` part, and attach the relevant file(s).

---

## For data changes (questions, wording, scores, dimensions)

**Attach:** `assessment_data.js`

**Prompt:**

> I have an AI Ethics Assessment tool that loads its content from the attached `assessment_data.js` file. The file contains all dimensions, questions, answer options, scores, action guidance, and scoring thresholds.
>
> Please make the following changes to the data file and return the updated file. Keep the `const ASSESSMENT_DATA = ` wrapper and trailing semicolon:
>
> [DESCRIBE YOUR CHANGES HERE]
>
> Important rules:
> - Keep the same JSON structure — don't rename keys or change the schema.
> - Every question needs an `id` (e.g., "q1", "q2"), a `type` ("single_choice", "multi_choice", "multi_sub", or "text"), and `text`.
> - Every answer option needs a `label` and a `score` (number). Optionally include `actionGuidance` (string) and `examples` (array of strings).
> - If adding a new dimension, include an `id` (lowercase_snake_case), `name`, `icon` (emoji), `description`, and `questions` array. Also add its threshold in `scoring.thresholds` and its color in `config.dimension_colors`, and add its id to the appropriate group in `scoring.overall_action_indicator.dimension_groups`.
> - Return only the complete, valid file with the `const ASSESSMENT_DATA = { ... };` wrapper.

### Example change requests:

- "Change the score for 'Yes' in Acceptable Use Q1 from 3 to 5"
- "Add a new answer option 'Partially' with score 1 to Safe/Secure Q1"
- "Rename the 'Vendor' dimension to 'Third Party Risk'"
- "Add a new dimension called 'Data Quality' with 3 questions about data completeness, accuracy, and freshness"
- "Change the action guidance for Fair/Impartial Q1 Sex/Gender 'Yes' option to include a note about GDPR"
- "Remove Q3 from Robust/Reliable"

---

## For page/UI changes (layout, styling, new features)

**Attach:** `ethics_assessment.html`

**Prompt:**

> I have an AI Ethics Assessment tool built as a single HTML file (attached). It loads its data from an external `assessment_data.js` file. The page uses Chart.js for a radar chart, jsPDF for PDF export, and vanilla JavaScript.
>
> Please make the following changes to the HTML file and return the complete updated file:
>
> [DESCRIBE YOUR CHANGES HERE]
>
> Important: keep the external data loading approach (the page fetches `assessment_data.js` at runtime). Don't embed the data back into the HTML.

### Example change requests:

- "Add a progress percentage next to each step in the progress bar"
- "Change the color scheme to use blue tones instead of red"
- "Add a 'Print' button that opens the browser print dialog"
- "Show a summary of all answers before the results page"
- "Add the ability to enter the project name at the beginning and show it in the PDF report"
- "Make the action guidance pop-ups show automatically when an option is selected, not just on click"

---

## For both data + UI changes

**Attach:** both `assessment_data.js` and `ethics_assessment.html`

**Prompt:**

> I have an AI Ethics Assessment tool consisting of two files:
> 1. `ethics_assessment.html` — the page (attached)
> 2. `assessment_data.js` — the data file (attached)
>
> Please make the following changes and return both updated files:
>
> [DESCRIBE YOUR CHANGES HERE]
