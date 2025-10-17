
# ****Basic structure of CSS file****

A CSS file is made up of **rules**, and each rule has two main parts:

1.  **Selector** → The HTML element(s) you want to style.
    
2.  **Declaration Block** → Inside `{ }`, contains one or more **declarations**.
    

Each **declaration** has:

-   **Property** (what you want to change, like `color`, `font-size`).
    
-   **Value** (the setting, like `red`, `16px`).

**Syntax:**
```
selector {
  property: value;
  property: value;
}
```
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
👉 Applies to **all `<p>`** or **all `<h1>`** elements.

 2. **Class Selector (`.classname`)**
Targets elements with a specific  class attribute.
```
.highlight {
  background-color: yellow;
}
```
in HTML
``` <p class="highlight">This paragraph is highlighted.</p>```
👉 Classes can be reused on multiple elements.

 3. **ID Selector (`#idname`)**
 
 Targets an element with a specific **id attribute** (unique per page).
```
 #main-title {
  color: red;
}
```
in HTML
``` <h1 id="main-title">This is styled with an ID</h1>```


## How to **set color, background, and border** in CSS.

## 🎨 1. **Text Color**
The `color` property sets the **text color** of an element.
``` 
p {
  color: red;         /* named color */
}
h1 {
  color: #3498db;     /* hex code */
}
h2 {
  color: rgb(0, 128, 0); /* RGB value */
}
h3{
 color:rgba(244,66,220,0.9); /*RGBA value */
}

```
👉 You can use **named colors**, **HEX (`#ff0000`)**, **RGB**, or **HSL**.
**Note:** The most commonly used approach is: HEX code

## 🖼️ 2. **Background**
The `background` properties control the **background color, image, and patterns**.

``` 
/* Background color */
body {
  background-color: lightgray;
}

/* Background image */
div {
  background-image: url("background.jpg");
  background-repeat: no-repeat;  /* avoid tiling */
  background-size: cover;        /* fill the whole area */
}

/* Shorthand (color + image + repeat + position) */
section {
  background: #f0f0f0 url("pattern.png") no-repeat center;
}

```
## ⬛ 3. **Border**
The `border` property controls the **line around an element**.
```
/* Basic border */
p {
  border: 2px solid black;
}

/* Different styles */
div {
  border: 3px dashed red;
}

h1 {
  border: 4px dotted blue;
}

/* Border radius (rounded corners) */
button {
  border: 2px solid green;
  border-radius: 10px;
}

```
👉 Border styles include: `solid`, `dashed`, `dotted`, `double`, `groove`, etc.
## **Advanced selector**

The following are main important advanced selectors 
1) **Universal Selector (`*`) :**
Selects **all elements** on the page.
```
* {
  color: blue;
}
```
👉 Often used for **CSS resets**.
2) **Descendant Selector (`A B`) :** 

Selects elements **inside** another element (nested).
```
div p {
  color: blue;
}
```
👉 This will style `<p>` tags only if they are inside a `<div>`.

 3) **Adjacent Sibling Selector (`A + B`) :**
 Selects an element that comes **immediately after** another element.
 ```
 h1 + p {
  color: green;
}
 ```
 👉 Styles the first `<p>` that comes right after an `<h1>`.
4) **Attribute Selector (`[attribute]`)**
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
👉 Great for styling lists, tables, and repeating elements.


## CSS inheritance
**Inheritance** in CSS means that  some property values are passed (inherited) from parent elements to their child elements.

👉 For example: If you set a text color on the `<body>`, all text inside will usually take that color unless overridden.


Not all CSS properties inherit by default.

✅ Common **inherited properties**:

-   `color`
    
-   `font` (family, size, weight, style)
    
-   `line-height`
    
-   `text-align`
    
-   `visibility`
- Others **do not inherit** (like box-model and layout properties).
- You can **force or prevent inheritance** using keywords:

1.  **`inherit`** → Forces an element to take the value from its parent.
    
    `p { color: inherit;
    }` 
    
2.  **`initial`** → Resets the property to its default (browser) value.
    
    `p { color: initial;
    }` 
    
3.  **`unset`** → Acts like `inherit` if the property is naturally inherited, otherwise acts like `initial`.
    
    `p { color: unset;
    }` 
    
4.  **`revert`** → Rolls back to the stylesheet’s default or user-agent (browser) styles.
5. `a.special {
  color: revert;  /* back to the browser’s default (usually blue with underline) */
}`
## Fonts and Text in CSS

## 🔹 1. **Font Properties**
**-  font-family** →  Sets the typeface.
```
p {
  font-family: Arial, "Open-Sans", sans-serif;
}
```
Question .. ? 
-   👉 Always use a **fallback list** (serif, sans-serif, monospace) in case the main font is not available.
**-  font-size** → Sets the size of text.
```
h1 { font-size: 36px; }
p { font-size: 16px; }

```
**- font-weight**→  Controls thickness (light, normal, bold)
```
p { font-weight: bold; }
```
- **`font-variant`** → Small caps formatting.

`h2 { font-variant: small-caps; }`

**`font` (shorthand)** → Combine multiple font properties.

```
p { font: italic bold 16px/1.5 Arial, sans-serif;
/* font: style weight size/line-height family; */
}
```

## 🔹 2. **Text Properties**
- **`text-align`** → Alignment.
 ```
 h1 { text-align: center; }
p { text-align: justify; }
 ```
 -  **`text-decoration`** → Underline, line-through, overline.
  ```
a { text-decoration: none; }
p { text-decoration: underline; }
  ```
-   **`text-transform`** → Change case.
```
h1 { text-transform: uppercase; }
p { text-transform: capitalize; }
```
- **`line-height`** → Space between lines of text.
```
p { line-height: 1.8; }
```
-  **`letter-spacing`** → Space between letters.
- **`word-spacing`** → Space between words.
- **`text-shadow`** → Add shadow effect.







