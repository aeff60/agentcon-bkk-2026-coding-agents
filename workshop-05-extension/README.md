# Workshop 5: Building a Browser Extension with GitHub Copilot

Learn how to use GitHub Copilot to build a simple browser extension for **Google Chrome** or **Microsoft Edge** — from project setup through manifest configuration, popup UI, and content scripts.

## 🎯 Learning Objectives

By the end of this workshop, you will be able to:

- Understand the structure of a Manifest V3 browser extension
- Use GitHub Copilot to generate the manifest, popup, and content scripts
- Build a working Chrome/Edge extension with a popup UI
- Inject content scripts into web pages using Copilot's help
- Load and test an unpacked extension in Chrome or Edge

## 🛠️ Prerequisites

- [VS Code](https://code.visualstudio.com/) with the [GitHub Copilot extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- Google Chrome or Microsoft Edge (latest version)
- Basic familiarity with HTML, CSS, and JavaScript

## 🚀 Getting Started

All files for this workshop live inside the `workshop-05-extension/` folder.

Open VS Code in this folder:

```bash
code workshop-05-extension
```

No `npm install` is required — browser extensions are plain HTML, CSS, and JavaScript files.

To load your extension during development:

1. Open Chrome or Edge and navigate to `chrome://extensions` (or `edge://extensions`).
2. Enable **Developer mode** (toggle in the top-right corner).
3. Click **Load unpacked** and select the `workshop-05-extension/` folder.

## 📋 Workshop Exercises

### Exercise 1: Create the Manifest File

The `manifest.json` file is the entry point for every browser extension.

1. Create a new file called `manifest.json` in this folder.
2. Add a comment at the top and let Copilot generate the content:

```jsonc
// Manifest V3 for a Chrome/Edge extension called "Page Word Counter"
// that shows a popup with the word count of the current page
```

3. Ask Copilot Chat to refine it:
   > "Create a Manifest V3 `manifest.json` for a Chrome extension called 'Page Word Counter'. It needs a popup action with `popup.html`, a content script `content.js` that runs on all pages, and the `activeTab` and `scripting` permissions."

Expected structure:

```json
{
  "manifest_version": 3,
  "name": "Page Word Counter",
  "version": "1.0",
  "description": "Counts the number of words on the current page.",
  "action": {
    "default_popup": "popup.html",
    "default_icon": "icon.png"
  },
  "permissions": ["activeTab", "scripting"],
  "content_scripts": [
    {
      "matches": ["<all_urls>"],
      "js": ["content.js"]
    }
  ]
}
```

---

### Exercise 2: Build the Popup UI

The popup appears when the user clicks the extension icon in the browser toolbar.

1. Create `popup.html` and ask Copilot:
   > "Create a minimal HTML popup page for a Chrome extension. It should show a heading 'Page Word Counter', a paragraph element with id `wordCount` to display the count, and a button with id `countBtn` labeled 'Count Words'. Link it to `popup.js`."

2. Create `popup.js` and add a comment:

```javascript
// When countBtn is clicked, execute a script in the active tab
// to count words in document.body.innerText and display the result
```

3. Let Copilot complete the implementation. Ask Copilot Chat to help with the `chrome.scripting.executeScript` API:
   > "Using Manifest V3's `chrome.scripting.executeScript`, inject a function into the active tab that counts the words in `document.body.innerText` and returns the count. Display it in the `wordCount` element."

---

### Exercise 3: Style the Popup

1. Create `popup.css` and ask Copilot Chat:
   > "Create a CSS file for a Chrome extension popup. The popup should be 280px wide, have a dark theme with a purple accent, a bold count display, and a full-width button with hover effect."

2. Link the stylesheet in `popup.html` and verify the popup looks good.

---

### Exercise 4: Write a Content Script

Content scripts run in the context of web pages.

1. Create `content.js` and add a comment:

```javascript
// Content script: listen for a message from the popup
// and respond with the word count of the page
```

2. Ask Copilot Chat:
   > "Write a content script that listens for a `{action: 'getWordCount'}` message using `chrome.runtime.onMessage` and replies with `{wordCount: N}` where N is the number of words in `document.body.innerText`."

3. Update `popup.js` to use `chrome.tabs.sendMessage` instead of `executeScript`:
   > "Refactor popup.js to send a `{action: 'getWordCount'}` message to the active tab using `chrome.tabs.sendMessage` and display the `wordCount` from the response."

---

### Exercise 5: Add an Extension Icon

1. Ask Copilot Chat to generate an SVG icon or use any 48×48 PNG:
   > "Give me an inline SVG that I can save as icon.svg for a word counter extension — a simple speech bubble with 'W' inside, dark background, white icon."

2. Convert the SVG to PNG using an online tool or VS Code extension, and save it as `icon.png`.

3. Verify the icon appears in the browser toolbar after reloading the unpacked extension.

---

### Exercise 6: Reload and Test

1. After making changes, go to `chrome://extensions` (or `edge://extensions`).
2. Click the **Reload** icon next to your extension.
3. Navigate to any web page (e.g., https://example.com).
4. Click the extension icon and press **Count Words**.
5. Verify the word count appears in the popup.

Ask Copilot Chat to help debug any issues:
> "My Chrome extension popup shows `undefined` for the word count. Here is my popup.js and content.js — what could be wrong?"

---

### Exercise 7 (Optional): Add a Badge Counter

Ask Copilot Chat:
> "Update the extension so that after counting, the word count is also shown as a badge on the extension icon using `chrome.action.setBadgeText` and `chrome.action.setBadgeBackgroundColor`."

## 💡 Copilot Tips for Browser Extensions

| Goal | Copilot Prompt |
|------|---------------|
| Manifest setup | "Create a Manifest V3 `manifest.json` for a Chrome extension that [description]" |
| Popup UI | "Create an HTML popup for a Chrome extension with [layout description]" |
| Content script | "Write a content script that [action] and sends the result back to the popup" |
| Background service worker | "Create a Manifest V3 service worker that listens for [event] and [action]" |
| Storage | "Use `chrome.storage.local` to save and retrieve [data] in a Chrome extension" |
| Permissions | "What permissions does a Chrome extension need to [action]?" |
| Debugging | "My content script isn't running on [site] — what could be wrong with this manifest?" |

## 📁 Project Structure (After Exercises)

```
workshop-05-extension/
├── manifest.json     # Extension manifest (entry point)
├── popup.html        # Popup UI markup
├── popup.css         # Popup styles
├── popup.js          # Popup logic (calls content script)
├── content.js        # Content script (runs in page context)
└── icon.png          # Extension icon (48×48)
```

## 📚 Resources

- [Chrome Extensions — Getting Started](https://developer.chrome.com/docs/extensions/get-started)
- [Manifest V3 Migration Guide](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3)
- [chrome.scripting API](https://developer.chrome.com/docs/extensions/reference/api/scripting)
- [chrome.runtime.onMessage API](https://developer.chrome.com/docs/extensions/reference/api/runtime#event-onMessage)
- [Microsoft Edge Extensions Documentation](https://learn.microsoft.com/en-us/microsoft-edge/extensions-chromium/)
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
