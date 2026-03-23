🚀 React Learning Milestone - 01

Welcome! This document captures my learning progress while exploring the fundamentals of React.

📌 1. What is React?
React is a JavaScript library used to build user interfaces, especially for web applications.
It enables developers to create complex UIs using small, reusable components, making applications easier to maintain and scale.

🌐 2. What is a CDN?
A CDN (Content Delivery Network) is a distributed network of servers.
It improves performance by delivering content from the nearest server to the user, reducing load time and latency.

📦 3. Why Two Script Files (React & ReactDOM)?
<script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

React is designed to be platform-independent, so it is split into:

🔹 react → Core logic (components, state, hooks)
🔹 react-dom → Handles rendering in the browser

👉 This separation allows React to work across platforms like:
Web (ReactDOM)
Mobile (React Native)

⚙️ 4. Without React vs With React
🧱 Without React (Vanilla JavaScript)
<body>
  <div id="root"></div>
  <script>
    const heading = document.createElement("h1");
    heading.innerText = "Hello World";

    const root = document.getElementById("root");
    root.appendChild(heading);
  </script>
</body>
⚛️ With React
<body>
  <div id="root"></div>

  <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
  <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

  <script>
    const text = React.createElement(
      "h1",
      { id: "text" },
      "Naresh is a good boy"
    );

    const root = ReactDOM.createRoot(document.getElementById("root"));
    root.render(text);
  </script>
</body>

👉 React makes UI development more structured, reusable, and scalable.

🧠 5. Understanding React.createElement()
React.createElement(
  "h1",
  { id: "text" },
  "Naresh is a good boy"
);
🔍 Breakdown:

Type → "h1" (HTML tag)
Props → { id: "text" } (attributes)
Children → "Naresh is a good boy" (content)

⚡ Important Concept

React does NOT directly create HTML.
Instead, it creates a JavaScript object (React Element):
{
  type: "h1",
  props: {
    id: "text",
    children: "Naresh is a good boy"
  }
}
👉 Then ReactDOM converts it into real DOM:

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(text);
🏗️ 6. Nested Elements in React
React.createElement(
  "div",
  { id: "parent" },
  React.createElement(
    "div",
    { id: "child" },
    React.createElement(
      "h1",
      { id: "text" },
      "Welcome to Naresh World"
    )
  )
);
Output:
<div id="parent">
  <div id="child">
    <h1>Welcome to Naresh World</h1>
  </div>
</div>
🔗 7. Sibling Elements in React
React.createElement(
  "div",
  { id: "parent" },
  React.createElement(
    "div",
    { id: "child" },
    [
      React.createElement("h1", {}, "Welcome to Naresh World"),
      React.createElement("h1", {}, "Welcome to Suresh World"),
      React.createElement("h1", {}, "Welcome to Harish World")
    ]
  )
);

👉 Passing an array creates multiple sibling elements.

⚛️ 8. What is JSX?

JSX (JavaScript XML) allows writing HTML-like syntax inside JavaScript.

Example:
const element = <h1>Hello Naresh</h1>;
Behind the scenes:
const element = React.createElement("h1", null, "Hello Naresh");

👉 JSX improves readability and developer experience.

🔐 9. What is crossorigin (CORS)?

CORS (Cross-Origin Resource Sharing) is a browser security mechanism.
An origin includes:
Protocol (http/https)
Domain
Port
👉 If any of these differ → it's a cross-origin request

🧱 Analogy:

Think of CORS like a security guard:
You request data from another server
Browser checks permission

Server responds:

✅ Allowed → Access granted
❌ Blocked → Access denied

crossorigin helps handle such requests correctly.

⚖️ 10. Library vs Framework
Library	Framework
You control the flow	Framework controls the flow
You call it	It calls you
Flexible	Structured

👉 React is a library, not a framework.

🎯 Summary

React simplifies UI development using components
JSX makes code readable
React uses a virtual representation before updating the DOM
Separation of React & ReactDOM enables cross-platform support