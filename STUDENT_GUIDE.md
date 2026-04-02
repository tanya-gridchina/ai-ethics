# AI Ethics Assistant — Student Guide

## What Is This Tool?

The AI Ethics Assistant is a web-based assessment tool that evaluates AI/ML projects across six ethical dimensions: Acceptable Use, Fair/Impartial, Robust/Reliable, Safe/Secure, Transparent/Explainable, and Vendor. It walks you through a series of questions, calculates risk scores, and produces a spider chart with a downloadable PDF report.

## Files in This Repository

| File | Purpose |
|------|---------|
| `ethics_assessment.html` | The complete tool — UI, logic, styling, AND all assessment data |
| `assessment_data.js` | Standalone copy of the data for use with the prompt template (see Level 2) |
| `PROMPT_TEMPLATE.md` | Ready-to-use prompts for asking an LLM to modify the tool |
| `STUDENT_GUIDE.md` | This document |

The HTML file is fully self-contained — it includes both the code and all assessment data. The data section is clearly marked at the top of the `<script>` block so you can edit it directly. A standalone `assessment_data.js` file is also provided for use with the LLM prompt template workflow.

---

## Using the Tool

### Option A: On GitHub Pages (recommended)
If the repository has GitHub Pages enabled, just visit the published URL. The tool runs entirely in your browser — no data is sent to any server.

### Option B: Locally
1. Download `ethics_assessment.html`.
2. Double-click to open in your browser — it works directly, no server needed. It's a single self-contained file.

---

## Making Changes

There are three levels of changes you can make, from easiest to most advanced:

### Level 1: Content Changes (Edit the JSON)

**No coding required.** Open `assessment_data.js` in any text editor and make changes directly.

#### Where to find the data
Open `ethics_assessment.html` in a text editor. Near the top, you'll find a clearly marked section:
```
// ╔══════════════════════════════════════════════════════════╗
// ║  ASSESSMENT DATA — EDIT THIS SECTION TO CUSTOMIZE      ║
// ╚══════════════════════════════════════════════════════════╝
const DATA = {
  "meta": { ... },
  "dimensions": [ ... ],
  ...
};
```
Edit the content inside the curly braces. Keep the `const DATA = ` prefix and the closing `};`.

#### Change question wording
Find the question by its `id` and edit the `text` field:
```json
{
  "id": "q1",
  "text": "Your new question text here",
  ...
}
```

#### Change a score
Find the answer option and change its `score`:
```json
{
  "label": "Yes",
  "score": 5,    ← change this number
  "actionGuidance": "..."
}
```

#### Add a new answer option
Add a new object to the `options` array:
```json
{
  "label": "Partially",
  "score": 2,
  "actionGuidance": "Guidance text for this option."
}
```

#### Add a new question to an existing dimension
Add a new object to the dimension's `questions` array:
```json
{
  "id": "q4",
  "text": "Your new question?",
  "type": "single_choice",
  "options": [
    { "label": "Yes", "score": 3, "actionGuidance": "..." },
    { "label": "No", "score": 0 }
  ]
}
```

#### Add a new dimension
Add a new object to the `dimensions` array, then also:
- Add its threshold to `scoring.thresholds`
- Add its color to `config.dimension_colors`
- Add its `id` to the appropriate group in `scoring.overall_action_indicator.dimension_groups`

#### Change scoring thresholds
Edit the values in `scoring.thresholds`:
```json
"acceptable_use": {"low_below": 4, "high_at_or_above": 6}
```
This means: score < 4 = Low, score >= 6 = High, anything in between = Medium. The HTML reads these values at runtime, so changes take effect immediately — no need to edit the HTML.

#### Validation tip
After editing, paste your JSON into [jsonlint.com](https://jsonlint.com) to make sure it's still valid. A single missing comma or bracket will break the tool.

---

### Level 2: LLM-Assisted Changes (Use the Prompt Template)

**No coding required.** Use `PROMPT_TEMPLATE.md` to ask Claude (or ChatGPT, etc.) to make changes for you.

#### Workflow:
1. Open `PROMPT_TEMPLATE.md` and pick the right prompt section for your change type.
2. Copy the prompt, fill in what you want to change.
3. Attach the relevant file(s) to your chat with the LLM.
4. The LLM will return updated file(s).
5. Download the updated file(s) and replace the old ones in your repository.
6. Commit and push to GitHub.

#### Examples of what you can ask:
- *"Add a new dimension called 'Data Quality' with questions about completeness, accuracy, and timeliness"*
- *"Change the color scheme to dark mode"*
- *"Add a field at the beginning where users enter their project name, and include it in the PDF"*
- *"Make the spider chart show raw scores instead of Low/Medium/High levels"*

---

### Level 3: Direct Code Editing (Advanced)

**Requires HTML/CSS/JavaScript knowledge.** Open `ethics_assessment.html` in a code editor and modify directly.

Key areas of the code:
- **Styles** — everything between `<style>` and `</style>` near the top
- **Scoring logic** — search for `calculateDimensionScore` and `getDimensionLevel`
- **Chart rendering** — search for `renderChart`
- **PDF generation** — search for `downloadPDF`
- **Question rendering** — search for `renderAssessment`

Note: Thresholds, dimension colors, and scoring groups are all read from `assessment_data.js` at runtime — they are NOT hardcoded in the HTML.

---

## GitHub Workflow

### First time setup
1. Fork this repository (or clone it if you have write access).
2. Enable GitHub Pages: go to Settings → Pages → Source: Deploy from a branch → select `main`, folder `/ (root)`.

### Making and publishing changes
1. Edit your files (either locally or on github.com directly).
2. Commit your changes with a descriptive message:
   ```
   git add .
   git commit -m "Changed Acceptable Use Q1 score from 3 to 5"
   git push
   ```
3. GitHub Pages will automatically deploy. Changes appear within 1–2 minutes.

### If something breaks
- Check the browser console (F12 → Console tab) for errors.
- The most common issue is invalid JSON — paste `assessment_data.js` into [jsonlint.com](https://jsonlint.com).
- If the page won't load at all, make sure both files are in the same folder/directory.
- You can always revert to a previous version using `git log` and `git checkout`.

---

## Question Types Reference

| Type | Behavior | Scoring |
|------|----------|---------|
| `single_choice` | User picks one option | Selected option's score is added |
| `multi_choice` | User picks one or more options | Highest score among selected is added |
| `multi_sub` | Multiple labeled sub-questions, each single-choice | All sub-question scores are summed |
| `text` | Free text input | No score (qualitative context only) |

## Conditional Questions

Questions can be shown/hidden based on prior answers using `conditionalOn`:
- `"conditionalOn": "q1_yes"` → show only if Q1 was answered "Yes"
- `"conditionalOn": "q1"` → on a `multi_sub`, only show sub-questions whose matching Q1 sub-question was "Yes"

---

## Need Help?

- **JSON syntax errors:** Use [jsonlint.com](https://jsonlint.com) to validate your data file.
- **Complex changes:** Use the prompt template with Claude at [claude.ai](https://claude.ai).
- **Git issues:** GitHub's [quickstart guide](https://docs.github.com/en/get-started/quickstart) covers the basics.
