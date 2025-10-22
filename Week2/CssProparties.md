## Understanding CSS Properties
A **property** is a predefined word in CSS that controls a specific visual feature of an element.
Examples of properties:

-   `color` — text color
    
-   `background-color` — background color
    
-   `font-size` — size of the text
    
-   `margin` — space outside the element
    
-   `padding` — space inside the element
    
-   `border` — edge line around the element
    
-   `width` / `height` — size of the box
    
-   `display` — layout behavior (block, inline, flex, grid, etc.)
##  Understanding CSS Values
A **value** is assigned to a property after a colon (`:`) and ends with a semicolon (`;`).  
The value defines **how much** or **what kind** of effect the property applies.

Examples of values:

-   `red`, `#ff0000`, `rgb(255, 0, 0)` → color values
    
-   `20px`, `2em`, `50%` → size/length values
    
-   `solid`, `dashed`, `none` → border styles
    
-   `center`, `left`, `right` → alignment
    
-   `bold`, `italic`, `underline` → text appearance

**Note** : You can include multiple property–value pairs inside one rule.
Each line ends with a semicolon (`;`) and all are wrapped inside `{ }`.

## Common Property Categories

### Fonts and Text in CSS

### 🔹 1. **Font Properties**
**-  font-family** →  Sets the typeface.
```
p {
  font-family: Arial, "Open-Sans", sans-serif;
}
```
Question .. ? 
-    Always use a **fallback list** (serif, sans-serif, monospace) in case the main font is not available.
**-  font-size** → Sets the size of text.
```
h1 { font-size: 36px; }
p { font-size: 16px; }

```
**- font-weight**→  Controls thickness 
```
p { font-weight: bold; }
```
Options: `normal`, `bold`, or numbers (100–900).

- **`font-variant`** → Small caps formatting.

`h2 { font-variant: small-caps; }`

**`font` (shorthand)** → Combine multiple font properties.

```
p { font: italic bold 16px/1.5 Arial, sans-serif;
/* font: style weight size/line-height family; */
}
```

### 🔹 2. **Text Properties**
- **`text-align`** → Aligns text horizontally.
 ```
p { text-align: justify; }
 ```
 
 Options: `left`, `center`, `right`, `justify`.
 
 
 -  **`text-decoration`** → Underline, line-through, overline, none.
  ```
p { text-decoration: underline; }
  ```
  
-   **`text-transform`** → Change case.
```
p { text-transform: capitalize; }
```
Values: `uppercase`, `lowercase`, `capitalize`.

- **`line-height`** → Controls the vertical space between lines of text.
```
p { line-height: 1.8; }
```

-  **`letter-spacing`** → Space between letters.
- **`word-spacing`** → Space between words.


## **set color, background, and border** in CSS.

### 🎨 1. **Text Color**
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
You can use **named colors**, **HEX (`#ff0000`)**, **RGB**, or **HSL**.
**Note:** The most commonly used approach is: HEX code

## 🖼️ 2. **Background**
The `background` properties control the **background color, image, and patterns**.
1.  Background color
``` 
body {
  background-color: lightgray;
}
```
2. Background image 
```
section{
  section {background-image: url("background.jpg");}
  ```
  3.   Background Repeat :  Controls if and how the image repeats.
```
 section{ background-repeat: no-repeat;  }/* avoid tiling */
```
   Options: `repeat`, `no-repeat`, `repeat-x`, `repeat-y`. 

  4. Background Size 
```
 section { background-size: cover; }/* fill the whole area */
```
   Options: `cover` (fills area), `contain` (fits image), or specific values (`100px 200px`). 
  5. Shorthand
  


/* Shorthand (color + image + repeat + position) */
section {
  background: #f0f0f0 url("pattern.png") no-repeat center;
}

## Visual Effects
### **A. `opacity`**

Controls how transparent an element is (from `0` = fully transparent to `1` = fully visible).
```
img {
  opacity: 0.7; /* 70% visible */
}

```
### **B. `box-shadow`**

Adds a shadow behind an element.

```
div { box-shadow: 4px  4px  10px  rgba(0,0,0,0.3);
/* Syntax : offset-x offset-y blur-radius color */
}
```
### **C. `text-shadow`**

Adds a shadow to text.

`h1 { text-shadow: 2px  2px  5px gray;
}`

### **D. `border-radius`**

Rounds the corners of elements.
```
button {
  border-radius: 10px;
}
/* You can even make circles: */
img {
  border-radius: 50%;
}

```
### **E. `filter`**

Applies visual effects like blur, brightness, or grayscale.

`img { filter: grayscale(100%);
}` 

Common filter functions:  
`blur()`, `brightness()`, `contrast()`, `sepia()`, `invert()`

### **F. `overflow`**

Controls what happens when content overflows its box.

`section { overflow: hidden; /* hides overflow */ }`


## List Properties

1. `list-style-type`
Controls the bullet or numbering style.
```
ul {
  list-style-type: square;
}
ol {
  list-style-type: upper-roman;
}

```
2. list-style-image
Uses a custom image as bullet.
```
ul {
  list-style-image: url("star.png");
}

```
3.  list-style-position
Places bullet inside or outside the content box.
```
ul {
  list-style-position: inside;
}

```	

## Animation & Transition
These properties bring **motion** and **smooth changes** to your web pages.
A. **Transitions**
Used to create **smooth changes** between property values when something changes (like hover).
```
button {
  background-color: orange;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: darkorange;
}

```
Syntax
```
transition: property duration timing-function delay;

```
Examples:

-   `transition: all 0.5s ease;`
    
-   `transition: color 0.2s linear 0.1s;`

### **B. Animations**

Used for **continuous or keyframed** motion — not just hover effects.

1.  **Define the animation:**
```
@keyframes move {
  from { transform: translateX(0); }
  to { transform: translateX(100px); }
}
```
2.   **Apply it to an element:**
```
div {
  animation: move 2s infinite alternate;
}
```
### **C. Combining Transitions & Animations**

Transitions = one-time smooth change  
Animations = continuous movement

You can mix them for advanced effects.

Example:
```
.card {
  transition: transform 0.3s ease;
}
.card:hover {
  transform: scale(1.05);
  animation: glow 1s infinite alternate;
}

@keyframes glow {
  from { box-shadow: 0 0 5px #ff6600; }
  to { box-shadow: 0 0 20px #ff6600; }
}
```
 ##  **Units of Measurement**
 CSS uses two main types of units:
 ![Units](https://i.ibb.co/1YMGshxv/Screenshot-2025-10-22-111734.png)

### Absolute Units
These units are **fixed and constant** — they don’t scale based on screen size or parent element.
![enter image description here](https://i.ibb.co/5h9ZVftV/Screenshot-2025-10-22-112328.png)

Use **absolute units** when you need precise sizes — like **print styles** or fixed-size UI elements.

### Relative Units
These are **flexible and responsive** — their values depend on another reference (like parent font size or viewport size).

![enter image description here](https://i.ibb.co/d4Vf6wJ7/Screenshot-2025-10-22-112452.png)

### **Viewport-relative units**
These adapt based on the **browser window (viewport)** size.  
Perfect for responsive layouts!
![enter image description here](https://i.ibb.co/jPFmkHhw/vw.png)
✅ Ideal for **full-screen sections**, **hero banners**, and **responsive typography**.

### **Percentage (%)**

Relative to the **parent element’s size**.
```
div {
  width: 80%; /* 80% of parent width */
}

```

Percentages depend on the property:

-   `width` → relative to parent’s width
    
-   `padding`/`margin` → relative to parent’s width (not height)
    
-   `line-height` → relative to element’s font size

### Common Use Cases
![enter image description here](https://i.ibb.co/FbCTp60n/size.png)

## Default and Inherited Values

If you don’t set a property:

-   The browser uses its **default** (called _user agent stylesheet_).
    
-   Or it may **inherit** it from its parent (for text-related properties).

## CSS inheritance
**Inheritance** means that **some CSS properties automatically pass from a parent element to its child elements.**

So, if you set a style on a parent, the children **“inherit”** that style — unless another rule overrides it.

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

    **Preventing Inheritance**
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


