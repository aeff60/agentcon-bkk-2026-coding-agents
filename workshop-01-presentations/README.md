# Workshop 1: Building Presentations with GitHub Copilot

Learn how to use GitHub Copilot to rapidly create engaging and professional presentations using [Slidev](https://sli.dev/) — a developer-friendly, Markdown-based presentation framework.

## 🎯 Learning Objectives

By the end of this workshop, you will be able to:

- Use GitHub Copilot to generate and refine Slidev presentation content
- Structure slides with layouts, animations, and code examples
- Leverage Copilot Chat to brainstorm slide ideas and speaker notes
- Export and share your presentation

## 🛠️ Prerequisites

- [Node.js 18+](https://nodejs.org/)
- [VS Code](https://code.visualstudio.com/) with the [GitHub Copilot extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- Basic familiarity with Markdown

## 🚀 Getting Started

The root of this repository already contains a complete Slidev presentation. Use it as a reference while building your own.

```bash
# From the repository root, install dependencies
npm install

# Start the development server
npm run dev
# Open http://localhost:3030 in your browser
```

## 📋 Workshop Exercises

### Exercise 1: Generate a Slide Outline with Copilot

1. Open `slides.md` (at the repository root) in VS Code.
2. At the end of the file, add a comment and let Copilot complete it:

```markdown
<!-- New section: Introduction to Machine Learning -->
```

3. Accept Copilot's suggestion and refine it using Copilot Chat:
   > "Make this slide more engaging with bullet points and an icon for each concept."

---

### Exercise 2: Add a Code Demo Slide

1. Ask Copilot Chat:
   > "Create a Slidev slide showing a Python function that sorts a list, with syntax highlighting and a step-by-step animation using magic-move."

2. Paste the generated slide content into `slides.md` and preview it in the browser.

---

### Exercise 3: Generate Speaker Notes

1. Select any existing slide in `slides.md`.
2. Ask Copilot Chat:
   > "Write speaker notes for this slide that explain the key points in plain language for a beginner audience."

3. Add the notes below the slide using Slidev's note syntax:

```markdown
<!--
Your speaker notes go here.
-->
```

---

### Exercise 4: Create a Custom Theme Slide

1. Ask Copilot to add a visually distinct title slide:
   > "Create a Slidev title slide with a dark gradient background, centered text, a subtitle, and a GitHub link in the bottom-right corner."

2. Add the slide to `slides.md` and verify the layout in the browser.

---

### Exercise 5: Export Your Presentation

```bash
# Export to a static HTML site
npm run build

# Export to PDF (requires Playwright)
npm run export
```

## 💡 Copilot Tips for Presentations

| Goal | Copilot Prompt |
|------|---------------|
| Generate slide content | "Create a 5-slide deck on [topic] using Slidev Markdown" |
| Add animations | "Add `v-clicks` to reveal each bullet point one at a time" |
| Improve clarity | "Simplify this slide so the key message is obvious in 5 seconds" |
| Add diagrams | "Add a Mermaid flowchart showing the steps of [process]" |
| Write speaker notes | "Write 3 talking points for a developer audience for this slide" |

## 📚 Resources

- [Slidev Documentation](https://sli.dev/)
- [Slidev Themes Gallery](https://sli.dev/themes/gallery)
- [Mermaid Diagram Syntax](https://mermaid.js.org/intro/)
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
