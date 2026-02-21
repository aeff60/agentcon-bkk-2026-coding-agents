# Getting Started with Coding Agents using GitHub Copilot

A comprehensive hands-on resource for AgentCon BKK 2026, covering how to use GitHub Copilot as a coding agent across four practical workshops.

## 🎯 Overview

This repository contains four workshops that guide you through using GitHub Copilot in real-world scenarios — from building presentations and diagrams to designing web pages and developing full web applications.

Each workshop includes step-by-step exercises, practical examples, and Copilot prompting tips you can apply immediately.

## 🗂️ Workshops

| # | Workshop | Description |
|---|----------|-------------|
| 1 | [Building Presentations with GitHub Copilot](./workshop-01-presentations/) | Use Copilot and Slidev to create engaging developer presentations |
| 2 | [Creating Diagrams with GitHub Copilot](./workshop-02-diagrams/) | Generate Mermaid diagrams from natural language using Copilot |
| 3 | [Designing a Web Page with GitHub Copilot](./workshop-03-webpage/) | Build a responsive static web page with HTML, CSS, and JS |
| 4 | [Developing a Web Application with GitHub Copilot](./workshop-04-webapp/) | Scaffold and build a full Node.js + Express web app end-to-end |
| 5 | [Building a Browser Extension with GitHub Copilot](./workshop-05-extension/) | Create a Chrome/Edge browser extension with a popup and content script |

## 🚀 Quick Start

### Prerequisites

- [Node.js 18+](https://nodejs.org/)
- [VS Code](https://code.visualstudio.com/) with the [GitHub Copilot extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- npm package manager

### Run the Presentation (Workshop 1)

```bash
# Install dependencies
npm install

# Start the Slidev development server
npm run dev
```

The presentation will be available at http://localhost:3030/

### Available Presentation Commands

```bash
# Start development server with live reload
npm run dev

# Build for production (static HTML)
npm run build

# Export slides to PDF
npm run export
```

## 📝 Presentation (`slides.md`)

The root `slides.md` is a complete Slidev presentation covering coding agents and GitHub Copilot. It is used as the foundation for Workshop 1 and includes:

- **Dark Theme**: Optimized for technical conference presentations
- **Interactive Elements**: Click animations, code examples, and Mermaid diagrams
- **Presenter Mode**: Separate presenter view with notes
- **Code Highlighting**: Syntax highlighting with Shiki

## 📚 Resources

- [Slidev Documentation](https://sli.dev/)
- [Mermaid Diagram Editor](https://mermaid.live/)
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [AgentCon BKK 2026](https://globalai.community/chapters/bangkok/events/agentcon-bangkok/)
- [Session Presentation](https://docs.google.com/presentation/d/1z8Bgn7Zn2oPOVk1V7lzXnt2S1KACAjJrKkpo8K65Z60/edit?usp=sharing)

## 📄 License

MIT License — See the [LICENSE](./LICENSE) file for details.
