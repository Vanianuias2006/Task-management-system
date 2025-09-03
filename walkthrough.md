
# 📘 JavaScript Tutorial – Task Tracker (Very Easy Level)

This guide explains how the **JavaScript code** in the Task Tracker project works, line by line, and how it connects with the **HTML**. The goal is to help beginners understand **DOM (Document Object Model)** manipulation and basic JS functions.

---

## 🔗 How HTML and JS Work Together

In your HTML file:

```html
<button onclick="showTask()">Show Task</button>
```

This line tells the browser:  
📌 “When this button is clicked, **run the JavaScript function** called `showTask()`.”

That function lives in `app.js`, which is included at the bottom of the HTML file:

```html
<script src="app.js"></script>
```

So the connection works like:
- HTML button → calls `showTask()` → runs JS code that updates something on the page.

---

## 🧠 JavaScript Code Explained Line by Line

### 1. `function showTask() { ... }`
Defines a **named function** called `showTask`. This is the main function we want to run when the user clicks the `Show Task` button.

---

### 2. `const input = document.getElementById("taskInput");`

This line finds the `<input>` element by its ID:

```html
<input id="taskInput" ... />
```

The browser stores it in a variable named `input` so we can use it in JS.

---

### 3. `const output = document.getElementById("output");`

This line gets the `<div id="output">` and stores it in a variable.  
We will use this div to show the user’s task.

---

### 4. `output.innerText = input.value;`

📌 This line takes the **text typed by the user** (`input.value`) and **displays it** inside the `#output` box using `innerText`.

> Try changing `innerText` to `innerHTML` and test with:
> ```
> <b>Buy milk</b>
> ```

---

### 5. `output.style.fontSize = "24";`

🚫 This is a **bug** – `"24"` is missing `"px"`. It should be:

```js
output.style.fontSize = "24px";
```

---

### 6. `output.style.color = "black";`

Changes the text color of the output to black.

---

### 7. `function makeBold() { ... }`

Another function triggered by a different button. It changes the output text to bold red:

```js
output.style.fontWeight = "bold";
output.style.color = "red";
```

---

### 8. `function tryHTML() { ... }`

This replaces the text inside the output with a bold version using HTML:

```js
output.innerHTML = "<b>" + output.innerText + "</b>";
```

Try entering:
```
Clean your room
```
and press “Try innerHTML” to see what happens!

---

### 9. `function clearTask() { ... }`

Clears the output box:

```js
output.textContent = "";
```

You can also try `innerText = ""` – it works similarly here.

---

## 🧪 Mini Exercises

1. ✅ Change the `placeholder` text of the input using JavaScript.
2. ✅ Add `onclick="clearTask()"` to the Clear button.
3. ✅ Try typing HTML in the input and display it with `innerText` and `innerHTML`.
4. ✅ Add a new function that changes the font to italic.
5. ✅ Try `textContent` and see how it behaves with tags.

---

## 🧩 Bonus DOM Tips

| Property | What it does |
|----------|---------------|
| `innerText` | Shows text as seen by the user (ignores hidden elements) |
| `textContent` | Shows all text, including hidden ones |
| `innerHTML` | Lets you **insert** HTML tags like `<b>`, `<br>`, etc. |
| `element.style.property` | Changes CSS from JS |

---

👋 **Now try tweaking the file, save, and refresh the browser.**  
That’s how most frontend devs learn — by testing, breaking, and fixing small things!

---

## 1) VERY EASY Micro Project – “Motivation Board”

**Goal:** Show and style short motivational notes typed by the user.

### Allowed JS Features (Very Easy Only)
- `function myFn() { … }` declared in JS
- Direct calls from HTML via `onclick="myFn()"`
- `document.getElementById(...)`
- `innerText`, `textContent`, `innerHTML`
- `element.style.<property>` (e.g., `color`, `fontSize`, `fontWeight`)

### Requirements
- Input box for a message; button **Show Note** triggers a function.
- A display `<div id="board"></div>` where the note appears.
- A **Make Bold** button that sets `style.fontWeight = "bold"`.
- A **Try HTML** button that sets `board.innerHTML = "<b>" + board.innerText + "</b>"`.
- A **Clear** button that empties the board using `textContent`.
- Keep all behavior in **simple functions without addEventListener**.

### Visual
- Center content; keep text readable.
- Minimal CSS (font family, spacing).

### Acceptance Criteria
- Shows note content in the board.
- Bold and HTML buttons visibly change the output.
- Clear button empties the board.
- Works with or without HTML in the input (see what `innerText` vs `innerHTML` does).

### Stretch (Optional)
- Change input placeholder with JS.
- Change text color to a user-chosen color (hard-coded options).

---

> Tip: Keep each project in a separate folder with `index.html`, `style.css`, `app.js`. Reuse your previous scaffolds and evolve them level-by-level.