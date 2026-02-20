# Workshop 4: Developing a Web Application with GitHub Copilot

Learn how to use GitHub Copilot to build a complete, interactive web application — from project setup through feature development, testing, and deployment.

## 🎯 Learning Objectives

By the end of this workshop, you will be able to:

- Use GitHub Copilot to scaffold and structure a full web application
- Generate backend API routes, data models, and business logic with Copilot
- Build interactive frontend components using Copilot's code completion and chat
- Write automated tests with Copilot's help
- Use Copilot to debug, refactor, and document code

## 🛠️ Prerequisites

- [Node.js 18+](https://nodejs.org/)
- [VS Code](https://code.visualstudio.com/) with the [GitHub Copilot extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- Basic familiarity with JavaScript or TypeScript
- Basic understanding of REST APIs (helpful but not required)

## 🚀 Getting Started

All files for this workshop live inside the `workshop-04-webapp/` folder.

```bash
# Navigate to the workshop folder
cd workshop-04-webapp

# Install dependencies (after completing Exercise 1)
npm install

# Start the development server (after completing Exercise 2)
npm run dev
```

## 📋 Workshop Exercises

### Exercise 1: Scaffold the Project

1. Open a terminal in the `workshop-04-webapp/` folder.
2. Ask Copilot Chat to help you choose a stack:
   > "I want to build a simple task manager web app. Suggest a lightweight Node.js + Express stack with a plain HTML/JS frontend and in-memory data storage — no database required."

3. Use Copilot to generate the initial `package.json`:
   > "Create a package.json for a Node.js Express app called 'task-manager' with scripts for `start` and `dev` (using nodemon)."

4. Run `npm install` after reviewing the generated file.

---

### Exercise 2: Build the Backend API

1. Create `server.js` and type a comment:

```javascript
// Express server for a Task Manager API
// Routes: GET /tasks, POST /tasks, PUT /tasks/:id, DELETE /tasks/:id
```

2. Let Copilot complete the implementation. Review the generated code carefully.

3. Ask Copilot Chat to add input validation:
   > "Add validation to the POST /tasks route: the `title` field is required and must be a non-empty string. Return a 400 error with a descriptive message if validation fails."

4. Start the server and test with `curl` or a browser:

```bash
node server.js
curl http://localhost:3000/tasks
```

---

### Exercise 3: Build the Frontend

1. Create `public/index.html` and ask Copilot:
   > "Create an HTML page with a form to add a task (title input + submit button), a list to display tasks, and delete buttons. Fetch data from the `/tasks` API using the Fetch API."

2. Ask Copilot Chat to add a loading state:
   > "Show a 'Loading...' spinner while the task list is being fetched from the API."

3. Ask Copilot Chat to improve error handling:
   > "Display a user-friendly error banner if the API request fails."

---

### Exercise 4: Write Automated Tests

1. Ask Copilot Chat:
   > "Using the built-in Node.js `node:test` module and `assert`, write tests for the Task Manager API: test that GET /tasks returns an empty array initially, POST /tasks creates a task and returns 201, and DELETE /tasks/:id removes a task."

2. Save the tests to `server.test.js` and run them:

```bash
node --test server.test.js
```

---

### Exercise 5: Refactor and Document

1. Select the entire `server.js` file and ask Copilot Chat:
   > "Refactor this Express server to separate routes into a `routes/tasks.js` file, use a `TaskStore` class in `store/tasks.js` to manage in-memory data, and add JSDoc comments to all functions."

2. Verify the app still works after the refactor.

---

### Exercise 6: Security Review

Select the full codebase and ask Copilot Chat:

> "Review this Node.js Express app for common security issues: missing input sanitization, lack of rate limiting, missing security headers, and any other concerns. Suggest fixes."

Apply the suggested improvements and discuss with your workshop group.

## 💡 Copilot Tips for Web Applications

| Goal | Copilot Prompt |
|------|---------------|
| Project setup | "Scaffold a Node.js Express app with TypeScript and ESLint" |
| API routes | "Create CRUD routes for a [resource] entity" |
| Data validation | "Add Zod schema validation to this Express route handler" |
| Error handling | "Add a global error handler middleware to this Express app" |
| Authentication | "Add JWT-based authentication middleware to this Express app" |
| Tests | "Write tests for this function using Node.js built-in test runner" |
| Refactoring | "Refactor this route handler to use async/await and handle errors" |
| Documentation | "Add JSDoc comments to all exported functions in this file" |
| Security | "Review this code for OWASP Top 10 vulnerabilities" |

## 📁 Project Structure (After Exercises)

```
workshop-04-webapp/
├── package.json          # Project metadata and scripts
├── server.js             # Express app entry point
├── server.test.js        # Automated tests
├── routes/
│   └── tasks.js          # Task API route handlers
├── store/
│   └── tasks.js          # In-memory task store
└── public/
    └── index.html        # Frontend UI
```

## 📚 Resources

- [Express.js Documentation](https://expressjs.com/)
- [Node.js Built-in Test Runner](https://nodejs.org/api/test.html)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [MDN — Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
