
# ****Basic structure of CSS file****

A CSS file is made up of **rules**, Each **rule** tells the browser _which element_ to style and _how_ to style it. 


 **Parts of CSS rule:**
**Syntax:**
```
selector {
  property: value;
  property: value;
}
```
1.  **Selector** → The HTML element(s) you want to style.
    
2.  **Declaration Block** → Inside `{ }`, contains one or more **declarations**.
    
Each **declaration** has:

3.   **Property** (what you want to change, like `color`, `font-size`).
    
4.   **Value** (the setting, like `red`, `16px`).

Each declaration ends with a **semicolon (;)** and the whole block with **curly braces `{}`**.
**Example**
```
h1 {
  color: blue;       /* text color */
  font-size: 30px;   /* size of the text */
  }
```
**How to define Comments in CSS File:**
```
/* This is CSS comment */
```

## Basic CSS selectors 

 1. **Element selectors**
Targets HTML tags directly.
```
p {
  color: blue;
}
h1 {
  font-size: 32px;
}
```
 Applies to **all `<p>`** or **all `<h1>`** elements.

 2. **Class Selector (`.classname`)**
Targets elements with a specific  class attribute.
```
.highlight {
  background-color: yellow;
}
```
in HTML
``` <p class="highlight">This paragraph is highlighted.</p>```
Can be reused on **many elements**.

 3. **ID Selector (`#idname`)**
 
 Targets an element with a specific **id attribute**.
```
 #main-title {
  color: red;
}
```
in HTML
``` <h1 id="main-title">This is styled with an ID</h1>```
⚠️ Each **ID must be unique** on the page.

4. **Group Selector**
Apply the same styles to multiple elements by separating with commas.
```
h1, h2, h3 {
  font-family: "Poppins", sans-serif;
}
```
Saves time and keeps code shorter.

5.  **Universal Selector (`*`) :**
Selects **all elements** on the page.
```
* {
  color: blue;
}
```
Commonly used to reset browser default styles.

6.  **Descendant Selector (`A B`) :** 

Selects elements **inside** another element (nested).
```
div p {
  color: blue;
}
```
→ Styles all `<p>` inside a `<div>` (but not `<p>` elsewhere).


7. **Child Selector**
     Selects **direct children** only (`>`).
     
   ```
 div > p {
  color: blue;
}
```

→ Styles `<p>` that are **immediate children** of `<div>` (not nested deeper).


   8.  **Adjacent Sibling Selector (`A + B`) :**
 Selects an element that comes **immediately after** another element.
 ```
 h1 + p {
  color: green;
}
 ```
Styles the first `<p>` that comes right after an `<h1>`.



9.  **Attribute Selector (`[attribute]`)**
Selects elements based on their **attributes** or **attribute values**.
```
/* Any element with a title attribute */
[title] {
  color: red;
}

/* Specific value */
input[type="text"] {
  border: 2px solid blue;
}
```
👉 Super useful for styling **forms** or **links**.
 5) **`:nth-of-type(n)` Selector**
Selects the **n-th child of a specific type** within its parent.
```
/* Every second paragraph inside a div */
div p:nth-of-type(2) {
  color: purple;
}

/* All odd rows in a table */
tr:nth-of-type(odd) {
  background-color: #f0f0f0;
}
```
 Great for styling lists, tables, and repeating elements.

----
## **Pseudo-classes** and **pseudo-elements**

 **Pseudo-Classes (`:`)**

 🔸 What are they?
**Pseudo-classes** are used to **select elements based on their state or position** — not by their actual class or ID.  
They start with a **single colon** `:`.
👉 Example: `:hover`, `:focus`, `:nth-child(2)`
```
button:hover {
  background: blue;
  color: white;
}
```

 **Pseudo-Elements (`::`)**

🔸 What are they?

**Pseudo-elements** are used to **style specific parts of an element’s content** — like the first letter, line, or to insert extra generated content.  
They start with **double colons** `::` (modern syntax), though old CSS still supports single `:` for compatibility.

👉 Example: `::before`, `::after`, `::first-line`
```
p::first-letter {
  font-size: 2rem;
  font-weight: bold;
}
```
## **Selector Specificity (Priority)**

When multiple selectors target the same element, **CSS decides which one wins** based on specificity:

1.  Inline style (`style=""`) → highest
    
2.  ID selector → next
    
3.  Class / attribute / pseudo-class → then
    
4.  Type / element selector → lowest

6.   **Order** (later rules override earlier ones)

**Example** 
```
<p id="text" class="highlight">Hello!</p>

```
```
p { color: green; }         /* type */
.highlight { color: blue; } /* class */
#text { color: red; }       /* id */

```
✅ Final color: **red**, because **ID** has the highest specificity.

But when you use `!important`, it **jumps to the top of the list**, even above inline styles.

### What Is `!important` in CSS?
The `!important` declaration is used in CSS to **force a style rule to override all other conflicting rules**, regardless of **specificity** or **source order**.

It’s like telling the browser:

> “No matter what, this rule wins!”

 **Syntax Example**
 ```
 p {
  color: red !important;
}
 ```
 
 While it seems convenient, using `!important` often causes **more problems than it solves**.
 1. **Hard to debug** : You’ll struggle to figure out why a style won’t change — it could be overridden by a hidden `!important` elsewhere.
 2. **Breaks the cascade** : It bypasses CSS’s natural flow and order, which can make code inconsistent.
 3. **Inflexible for future edits** : When everything becomes `!important`, nothing can override anything.
 4. **Conflicts with frameworks** : CSS libraries like Bootstrap or Tailwind often include their own rules, and `!important` can break them.
 
 ## When It’s (Sometimes) Useful

Use `!important` **only** for:

-   **Debugging or testing** quickly.
    
-   **User-specific overrides**, such as accessibility styles (high contrast, large font).
    
-   **Third-party stylesheets** you can’t control (e.g., forcing your custom design to override a library rule).
  
