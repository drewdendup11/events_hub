Question 1
You change the footer colour in styles.css. How many pages update? What if the same colour was only set with an inline style on index.html?
Ans:All five pages update because they share the same external styles.css.If the colour was only set using inline CSS on index.html, only the footer on index.html would be affected.

Question 2
Which is more specific: h1 or #welcome?
Ans: #welcome is more specific than h1 Therefore, if both set the colour, #welcome wins.

Question 3
Convert #0369a1 into an approximate RGB value. Why do designers often prefer hex in stylesheets?
Ans: rgb(3, 105, 161) Designers often prefer hexadecimal because it is short, compact and easy to use in CSS.

Question 4
Set a nav link to display: none, then to visibility: hidden. What is the difference in the layout?
Ans:display: none removes the element completely.
visibility: hidden hides the element but keeps its space.

Question 6 
In your wireframe, how many event cards appear side-by-side at phone width? At desktop width?
Ans:At phone width: 1 card per row
At desktop width: 3 cards per row

Question6 
Why must styles.css be linked AFTER the Bootstrap CSS file?
Ans:styles.css should be loaded after Bootstrap so your own CSS can override Bootstrap styles when the selectors have appropriate specificity.


practical IV

# Practical IV — JavaScript Events Hub
## Quick Check Answers (Q1–Q8)

### Q1. What happens if `validate.js` runs before `main.js` and calls a function defined only in `main.js`?

The browser may show a `ReferenceError`, such as `ReferenceError: findEventById is not defined`, because the function has not been defined when it is called. Load `main.js` before `validate.js` when the second script depends on the first.

### Q2. What happens when `document.write()` runs after the page has fully loaded? Why is `innerHTML` safer for updates?

Calling `document.write()` after the page has loaded can replace the entire document with the new content. `innerHTML` updates the contents of a particular element instead. For plain text, `textContent` is safer because it does not interpret the text as HTML.

### Q3. What is the difference between `alert()`, `confirm()`, and `prompt()`?

- `alert()` displays a message with an OK button.
- `confirm()` displays OK and Cancel and returns `true` or `false`.
- `prompt()` asks the user to enter text and returns the entered string or `null` if cancelled.

### Q4. What is a regular expression, and what does `.test()` do?

A regular expression (regex) is a pattern used to check whether text has a required format. The `.test()` method returns `true` if the text matches the pattern and `false` otherwise.

Example:

```javascript
const phonePattern = /^(17|77)\d{6}$/;
console.log(phonePattern.test("17123456")); // true
console.log(phonePattern.test("123"));      // false
```

### Q5. What happens if Inter-College Football seats change from 0 to 5 in the events array?

After saving the updated array and reloading the page, the event should no longer appear sold out. Its card should show that seats are available, and its Register option should become enabled, provided the rendering and dropdown functions use the seat count to control availability.

### Q6. What do `seatsMessage(0)` and `seatsMessage(12)` return?

The answer depends on the implementation of `seatsMessage()` in `js/main.js`. In the sample, zero seats produces a sold-out message, while 12 seats produces an availability message. The exact wording is determined by the function's return statements.

### Q7. Which line stops the browser from leaving the page when the form has an empty email? What happens without it?

The line is:

```javascript
e.preventDefault();
```

It prevents the form's default submission behavior. Without it, the browser may submit the form and reload or navigate away, interrupting the display of validation errors.

### Q8. Is `document.querySelectorAll("nav a")` a NodeList or an HTMLCollection? Does `forEach()` work on it?

It returns a **NodeList**, not an HTMLCollection. In modern browsers, `NodeList.forEach()` works, allowing us to process each matching navigation link.

Example:

```javascript
document.querySelectorAll("nav a").forEach(function (link) {
    link.classList.add("nav-item");
});
```