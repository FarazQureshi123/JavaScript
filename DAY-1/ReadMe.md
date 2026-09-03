# JavaScript Learning Journey: Day 1

Welcome to my JavaScript repository! This repository documents my daily progress, code snippets, notes, and projects as I learn and revise JavaScript from scratch.

---

## 📌 Day 1: JavaScript History, Architecture & File Structure

### 💡 Core Key Takeaways & Concepts

1. **Brief History**:
   - JavaScript was created in **1995** by Brendan Eich while working at Netscape.
   - Remarkably, the core language was designed and built in just **10 days**!
   - Despite its name, JavaScript is distinct from Java.

2. **Client-Side vs. Server-Side**:
   - **Client-Side Scripting**: JavaScript natively executes inside the browser (client), handling interactive features, DOM manipulation, and dynamic user interfaces without sending requests back to the server for every interaction.
   - **Server-Side Scripting**: Languages like **Java** and **PHP** execute on web servers to manage databases, build backends, and send raw rendered data to the client. *(Note: Node.js allows JS on the server as well, but JS originated as a browser client-side language).*

3. **Script Execution & HTML Loading (`defer`)**:
   - By default, placing `<script>` tags in the `<head>` blocks HTML rendering until the script finishes downloading and running.
   - Adding the `defer` attribute allows the script file to download in **parallel** with the HTML parsing, executing only after the document is fully parsed. This optimizes performance and prevents blocking issues.

---

## 📁 Repository Structure & Code Examples

Here is how today's practical exercise is structured:

```text
js-learning-day1/
├── README.md
├── index.html
└── script.js