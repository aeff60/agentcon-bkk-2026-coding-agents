# Workshop 3: Designing a Web Page with GitHub Copilot

Learn how to use GitHub Copilot to design and build a static web page from scratch using HTML, CSS, and a touch of JavaScript — no frameworks required.

## 🎯 Learning Objectives

By the end of this workshop, you will be able to:

- Use GitHub Copilot to scaffold a complete HTML/CSS/JS web page
- Apply responsive design principles with Copilot's assistance
- Iterate on layout, styling, and interactivity using Copilot Chat
- Deploy a static site to GitHub Pages

## 🛠️ Prerequisites

- [VS Code](https://code.visualstudio.com/) with the [GitHub Copilot extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- Basic knowledge of HTML and CSS (helpful but not required)
- A web browser

## 🚀 Getting Started

All files for this workshop live inside the `workshop-03-webpage/` folder.

Open VS Code in this folder:

```bash
code workshop-03-webpage
```

Start with the provided starter file `index.html` and build on it during the exercises.

## 📋 Workshop Exercises

### Exercise 1: Scaffold a Landing Page

1. Open `index.html` in VS Code. It already contains a minimal HTML5 skeleton — build on top of it.
2. Inside the `<body>` tag, add a comment and let Copilot fill in the section:

```html
<!-- Hero section with a headline, subtitle, and call-to-action button -->
```

3. Accept Copilot's suggestion, then preview by opening `index.html` in your browser (`File → Open File`).

---

### Exercise 2: Add a Responsive Navigation Bar

Ask Copilot Chat:

> "Add a sticky top navigation bar with a logo on the left and navigation links on the right. Make it responsive with a hamburger menu for mobile screens. Use only HTML and CSS — no JavaScript frameworks."

Paste the output into `index.html` and resize your browser window to test responsiveness.

---

### Exercise 3: Style with a Color Palette

1. Add a `<style>` block or a linked `styles.css` file.
2. Ask Copilot Chat:
   > "Create a CSS color palette using CSS custom properties (variables) for a modern dark theme with a purple accent color. Apply it to the navigation, hero section, and buttons."

---

### Exercise 4: Add an Interactive Feature

Ask Copilot Chat:

> "Add a 'Back to Top' button that appears when the user scrolls down more than 300px and smoothly scrolls back to the top when clicked. Implement it using vanilla JavaScript."

---

### Exercise 5: Make the Page Accessible

Select your entire `index.html` content and ask Copilot Chat:

> "Review this HTML and suggest improvements for web accessibility (a11y): add ARIA labels, ensure proper heading hierarchy, add alt text placeholders, and improve color contrast."

Apply the suggested changes.

---

### Exercise 6: Deploy to GitHub Pages (Optional)

1. Push the `workshop-03-webpage/index.html` file to your GitHub repository.
2. Go to **Settings → Pages** in your GitHub repository.
3. Set the source to `main` branch and `/workshop-03-webpage` folder.
4. Your page will be live at `https://<your-username>.github.io/<repo-name>/`.

## 💡 Copilot Tips for Web Design

| Goal | Copilot Prompt |
|------|---------------|
| Page scaffold | "Create a complete HTML5 landing page for [product/topic]" |
| CSS layout | "Create a CSS Grid layout with a sidebar and main content area" |
| Responsive design | "Make this section responsive using CSS Flexbox" |
| Animations | "Add a fade-in animation when this element enters the viewport" |
| Dark mode | "Add a dark mode toggle using CSS variables and localStorage" |
| Forms | "Create an accessible contact form with client-side validation" |
| Performance | "Optimize this HTML/CSS for faster page load" |

## 📁 Starter File

The `index.html` starter file in this folder provides a minimal HTML5 skeleton to build on during the workshop.

## 📚 Resources

- [MDN Web Docs — HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [MDN Web Docs — CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [CSS Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [WebAIM — Web Accessibility](https://webaim.org/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
