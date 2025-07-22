# AGENTS.md

## 🧠 Codex Agent: Optimization & QA Instructions

Welcome!  
This file contains clear instructions for any AI (or human) code agent tasked with optimizing, auditing, or preparing a Pull Request for this project.

---

### Project Overview

- **Purpose:** Interactive, static HTML/CSS/JS guide for AI-powered sales training (AMP Sales Team Leave-Behind).
- **Stack:** No frameworks; all code is in `index.html` with `/imgs/` folder for assets.
- **Hosted:** GitHub Pages (static site).
- **Reference Manifest:** See [`project.meta.json`](./project.meta.json) for structured intent, style, and “do not change” constraints.

---

## 🛠️ Agent Tasks

### 1. **Consult the JSON Manifest**
- Before making changes, review [`project.meta.json`](./project.meta.json) for detailed requirements, structure, and unchangeable project elements.
- Adhere to all style, branding, content, and functional constraints defined in the JSON.

### 2. **Audit and Code Quality**
- Scan all HTML, CSS, and JavaScript for:
  - Semantic HTML5 usage, ARIA roles, and accessibility.
  - Code duplication, unused code, inefficient patterns.
  - Inline vs. external styles: ensure best-practices.
- Flag and suggest removal of any unused classes, IDs, or scripts.

### 3. **Functionality Testing**
- Confirm all interactive features work on desktop and mobile:
  - Copy/reset buttons, editable prompts.
  - Floating “Back to Top” button.
  - Table of Contents navigation.
  - Card reveals and visual hierarchy.
- Report or fix any broken/missing features.

### 4. **Responsiveness & UX**
- Ensure full usability on modern phone, tablet, and desktop sizes.
- Optimize CSS for:
  - Breathing room between cards/sections.
  - Appropriate font sizes for each device.
  - Touch targets and interactive elements.
- Test and improve:
  - Contrast between text, backgrounds, and accents.
  - Section/card separation and visual clarity.

### 5. **Performance & Accessibility**
- Run audit tools (Lighthouse, Pa11y, htmlhint, stylelint).
- Fix or propose fixes for:
  - Accessibility issues (contrast, ARIA, alt text, keyboard nav).
  - Performance slowdowns (image sizes, unused code).
  - Lint warnings/errors.

### 6. **Code Formatting**
- Run Prettier on all files for consistency.
- Make sure indentation, quotes, and line lengths are consistent.

### 7. **Propose a Pull Request**
- Bundle all changes in a single, well-commented PR.
- Include a summary of all changes, audit results, and recommendations for further improvement (if any).
- **Do not change or rewrite branding/copy without explicit approval and in accordance with `project.meta.json`.**

---

## Example Audit Commands (for Node.js environment)

```sh
serve .
lighthouse http://localhost:5000 --output html --output-path ./lighthouse-report.html
pa11y http://localhost:5000
htmlhint index.html
stylelint "**/*.css"
prettier --check .
