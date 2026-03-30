# AI Ethics Assistant — Regeneration Prompt

Use this prompt along with the `assessment_data.json` file to regenerate the AI Ethics Assistant tool from scratch. Send both this prompt and the data file to Claude.

---

## PROMPT (copy everything below this line)

---

I have a JSON data file (`assessment_data.json`) that defines an ethical assessment tool for AI/ML use cases. Please build a **single-file HTML page** that implements this tool exactly as described in the data file. Here are the requirements:

### Format & Flow
- **Multi-step wizard**: one dimension per step, shown in the order they appear in the data file.
- **Welcome screen** with the title, subtitle, and welcome_text from `meta`, showing all dimension icons/names, a "Begin Assessment" button, and a "Resume" option if saved data exists.
- **Progress bar** at the top showing all dimensions with color-coded step indicators.
- **Dimension intro** at the top of each step showing the dimension's icon, name, and description.
- **Results screen** at the end with a spider/radar chart, dimension scores, Low/Medium/High badges, and an Overall Action Indicator banner.

### Question Types (defined in `question_types_reference`)
- `single_choice`: Radio-style buttons; user picks one. Show a `?` help icon on options that have `actionGuidance` or `examples` — clicking it opens a modal popup with that guidance.
- `multi_choice`: Toggle-style buttons; user can select multiple. Show "Select all that apply" label. Scoring uses the **highest score** among selected options.
- `multi_sub`: Renders each item in `subQuestions` as a labeled sub-section with its own single_choice options. All sub-scores are summed.
- `text`: A textarea for free-form input. No score. Show any `examples` below as a hint.
- **Conditional questions**: If a question has `conditionalOn`, only show it when the condition is met (e.g., `"q5_yes"` means show only if q5 was answered "Yes"; `"q1"` on a multi_sub means only show sub-questions whose matching q1 sub-answer was "Yes").

### Scoring (defined in `scoring`)
- Each dimension's raw score = sum of all scored answers within it.
- Weights/scores are **hidden** from the user during the assessment.
- On the results page, raw scores are converted to **Low / Medium / High** using the thresholds in `scoring.thresholds`.
- The **Overall Action Indicator** (High / Medium / Low) is calculated using the rules in `scoring.overall_action_indicator`, with dimensions grouped into `group_A_higher_weight` and `group_B_lower_weight`.

### Action Guidance Popups
- Each answer option may have `actionGuidance` (text) and `examples` (array of strings).
- Show a small `?` icon next to any option that has guidance.
- Clicking it opens a **modal popup** with the guidance text and examples as a bulleted list.

### Features
- **Local storage**: Auto-save all answers to `localStorage` so users can resume later.
- **Spider/radar chart**: Use Chart.js to render a radar chart. The chart should plot **Low/Medium/High levels** (0, 1, 2) rather than raw scores — this makes dimensions comparable since they have different score ranges. The radial axis should be fixed at 0–2 with tick labels "Low", "Medium", "High". Tooltips should also show level names, not numbers.
- **PDF export**: Use jsPDF to generate a downloadable PDF report with the overall indicator, per-dimension scores + levels, and all answers.
- **Color coding**: Use the colors from `config.dimension_colors` for each dimension throughout the UI (progress bar, borders, chart points, score cards).
- **Reset button**: Allow users to clear all saved data and start over.

### Technical Constraints
- **Single HTML file** with all CSS, JS, and data embedded inline.
- Load Chart.js and jsPDF from CDN (`cdnjs.cloudflare.com`).
- Use Google Fonts for typography (suggest a serif + sans-serif pairing).
- Mobile-responsive design.
- Clean, professional aesthetic — not generic. Use warm tones, good spacing, and thoughtful typography.

### Data File
The attached `assessment_data.json` contains everything: `meta` (title, subtitle, welcome text), `config` (colors, features), `dimensions` (all questions, options, scores, guidance), `scoring` (thresholds, overall indicator rules), and `question_types_reference` (documentation).

**Please generate the complete working HTML file.**
