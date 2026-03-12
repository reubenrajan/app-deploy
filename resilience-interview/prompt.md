# Resilience Test Engineer — Interview Questionnaire Prompt

> Use this prompt with the accompanying CSV file to regenerate the complete interactive HTML interview questionnaire from scratch.

---

## Setup

Using the attached CSV file as a reference for resilience areas and their associated data points, create an **interactive HTML interview questionnaire** for hiring a **Resilience Test Engineer** with experience in chaos testing tools (LitmusChaos, Gremlin, Harness) and observability tools (Datadog, Dynatrace).

---

## Content Requirements

- Generate **10 interview questions per resilience area**, covering all 8 areas defined in the CSV
- Questions must have a good mix of **open-ended, closed, and mixed** question types, clearly labelled
- Each question must be tagged with its **topic** (derived from the CSV data points)
- Each question must include **4–6 answer hint points** — key concepts, terms, or examples a strong candidate should mention — with important terms **bolded**

---

## Interactive Features

For each question, include:

- A **checkbox** to mark the question as asked during the interview
- An expandable **Answer Hints panel** (collapsed by default), with an individual **checkbox per hint point** to tick when the candidate mentions it
- A mini **progress bar** inside the hints toggle showing how many hints have been covered (e.g. `3/5`)
- A **freetext notes/feedback textarea** for the interviewer to record observations

### Global UI Elements

- A **sticky progress bar** at the top showing how many of the 80 questions have been asked
- **Section tabs** for navigating between the 8 resilience areas, with per-section counters that show a `✓` when all 10 questions are asked
- A **live interview score widget** in the top-right corner of the header, showing a circular progress ring and percentage score based on hint points covered out of the total possible, with the following verdict thresholds:

  | Score     | Verdict         | Colour |
  |-----------|-----------------|--------|
  | < 40%     | No Hire         | Red    |
  | 40–69%    | Can Consider    | Amber  |
  | 70%+      | Sure Hire ✓     | Green  |

- The score verdict label should animate with a subtle pop when the band changes
- A **dark/light mode toggle** (pill switch) positioned in the **top-right corner of the header**, defaulting to the OS `prefers-color-scheme` preference if no saved preference exists, persisted to `localStorage`
- The **score widget** should sit **directly below the dark/light mode toggle**, both grouped together in the top-right corner of the header inside a shared flex column container

---

## Save & Persistence

- **Auto-save** all checkboxes, hint ticks, and notes to `localStorage` after 1.5 seconds of inactivity, with a pulsing dot indicator in the progress bar and a status pill confirmation
- **Named session save** via a 💾 Save modal — the user can name the session (e.g. `"Jane Smith – 11 Mar 2026"`), with the ability to overwrite or delete existing sessions
- **Load session** via a 📂 Load modal — lists all saved named sessions and the auto-save, each with a timestamp; also supports **importing a JSON session file** from disk
- On page load, automatically **restore the last auto-saved session**
- All session data and theme preference persisted independently to `localStorage`

---

## Export

- An **⬇ Export** button that downloads a `.txt` summary file containing:
  - Session name and export timestamp
  - All 80 questions with asked / skipped status
  - Hint coverage per question (`✓` / `○` per point)
  - All interviewer notes
  - Total score percentage and verdict
- The **Save**, **Load**, and **Export** buttons should be grouped in a **fixed bottom-right toolbar**

---

## Design & Aesthetics

- Production-grade, visually distinctive **dark-first design** using CSS custom properties for full theme switching
- **Fonts** (loaded from Google Fonts):
  - `Syne` — display headings and large numerics
  - `DM Sans` — body text and UI copy
  - `DM Mono` — labels, tags, badge text, and monospaced elements
- Each of the 8 sections has a **distinct accent colour** applied to its icon, heading, and section progress counter
- Hint checkboxes and hint UI use a **violet** accent colour, distinct from the green question-asked accent
- Smooth **0.3s transitions** on all theme switches (background, borders, text, gradients)
- **Light theme** must use appropriately deepened accent tones to maintain readability on white backgrounds
- All elements — hint ticks, question checkboxes, badge labels, type tags, and the score ring — must fully adapt to both themes
- Responsive layout with appropriate padding adjustments at `≤ 640px` viewport width

---

## Technical Constraints

- Delivered as a **single self-contained `.html` file** — no external dependencies except Google Fonts
- No build tools, frameworks, or bundlers — plain HTML, CSS, and vanilla JavaScript only
- All interactivity, state, persistence, and theming handled entirely client-side
