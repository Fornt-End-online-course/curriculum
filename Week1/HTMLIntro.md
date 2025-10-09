## Introduction to HTML 

## What is HTML 
HTML (HyperText Markup Language) is the skeleton of a webpage. It defines the structure and content—like headings, paragraphs, images, links, lists, and more.

Think of HTML as the framework of a building, while CSS and JavaScript add style and interactivity.

## 🧩 **Basic Structure of an HTML Document**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>My First Webpage</title>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>This is my first HTML page!</p>
</body>
</html>

```
## Anatomy of an HTML element
The main parts of our element are as follows:

1.  **The opening tag:**  This consists of the name of the element (in this case, p), wrapped in opening and closing  **angle brackets**. This states where the element begins or starts to take effect — in this case where the paragraph begins.
2.  **The closing tag:**  This is the same as the opening tag, except that it includes a  _forward slash_  before the element name. This states where the element ends — in this case where the paragraph ends. Failing to add a closing tag is one of the standard beginner errors and can lead to strange results.
3.  **The content:**  This is the content of the element, which in this case, is just text.
4.  **The element:**  The opening tag, the closing tag, and the content together comprise the element.

## 🔸Breakdown of the Structure
-   `<!DOCTYPE html>` → Tells the browser this is an HTML5 document.
    
-   `<html>` → Root element of the webpage.
	- lang="en" specifies the language as English.
    
-   `<head>` → Contains meta-information (like title, styles, scripts).
    
	-   `<title>` → Sets the title shown in the browser tab.
    
-   `<body>` → Contains the visible content of the page.
    
	-   `<h1>` → A heading (largest).
    
	-  `<p>` → A paragraph of normal text.


👉 Elements can also have **attributes** .
## HTML Attributes
**Attributes** give **extra information** or **special behavior** to HTML elements.  
They are always written **inside the opening tag**.

### **Basic Syntax:**
```
<tagname attribute_name="value">Content</tagname>
```
**Common Global Attributes**

Global attributes are attributes that can be used on  any HTML element.

- `id` Unique identifier for the element

`<div id="intro">Hello</div>`

- `class`  Groups elements for styling

`<div class="container">...</div>`

- `style` Inline CSS styling

- `title`  Shows tooltip text on hover

`<p title="I'm a tooltip!">Hover over me</p>`

- `hidden` Hides the element 

- `lang` Language of content
### Element-Specific Attributes
Some attributes only work with certain tags

### **Boolean Attributes**

Some attributes **don’t need a value**. If they’re present, they are “on”.
`<input type="checkbox" checked>
`
👉 Boolean attributes can also be written as `attribute="attribute"` but just writing the name is enough.

**Note** 
You can use several attributes inside one tag

## 📌 **Key HTML Tags**

**Headings** →   ``` <h1> - <h6> ``` (h1 is largest, h6 is smallest)
👉 Use headings to **structure your content**, like titles and subheadings.  
✅ Only **one `<h1>`** per page is recommended for SEO.
**Paragraph** → 
 ```
<p>This is a simple paragraph. You can write as much text as you like here.</p>
```
👉 Paragraphs **automatically create space** before and after the text.
**Hyperlink** → ```<a>```  is used to create a **link** to another page, website, or even a file.
```
<a href="https://www.google.com">Visit Google</a>
```
👉 `href` = “hyperlink reference” (the URL you want to go to)  
👉 The text between `<a>` and `</a>` is what the user clicks.
**Image** → ```<img>```
```
<img src="photo.jpg" alt="My Photo">
```
👉 `src` = path or URL of the image  
👉 `alt` = text shown if the image doesn’t load (and used by screen readers for accessibility)

**Unordered / Ordered lists**→  ``` <ul> ``` /``` <ol> ```

HTML supports **3 main types of lists**:

### 1️⃣ **Ordered List (`<ol>`)** — Numbered list

`<ol> <li>Wake up</li> <li>Brush teeth</li> <li>Eat breakfast</li> </ol>` 

👉 The browser automatically numbers the list items:

1.  Wake up
    
2.  Brush teeth
    
3.  Eat breakfast
    

----------

### 2️⃣ **Unordered List (`<ul>`)** — Bulleted list

`<ul> <li>Apples</li> <li>Bananas</li> <li>Oranges</li> </ul>` 

👉 This shows bullets (•) before each item:

-   Apples
    
-   Bananas
    
-   Oranges
----------
### 3️⃣ **Nested Lists** — List inside another list

You can place a list **inside** another `<li>`:

`<ul> <li>Fruits <ul> <li>Apple</li> <li>Orange</li> </ul> </li> <li>Vegetables</li> </ul>` 

👉 This is useful for menus, categories, or topics with sub-points.
### **Line Break & Horizontal Line**

-   `<br>` → adds a **line break** (goes to the next line)
    
-   `<hr>` → adds a **horizontal line** across the page

## Inline vs Block Elements
In HTML, every element is either **block-level** or **inline** by default.  
👉 Understanding this helps you control layout and design better.
### **Block Elements**

-   Always **start on a new line**
    
-   Take up the **full width** available (stretch across the page)
    
-   You can set **width, height, margin, and padding** easily
    
-   They stack **vertically** (one under the other)

**Common Block Elements**:
`<div>, <p>, <h1>–<h6>, <header>, <footer>, <section>, <article>, <table>, <form>`

### **Inline Elements**

-   Do **not start on a new line**
    
-   Only take up **as much width as needed**
    
-   You **can’t** easily set `width` or `height` directly (without CSS tricks)
- -   They line up **horizontally** with other elements

 **Common Inline Elements**:
`<span>, <a>, <b>, <i>, <strong>, <em>, <img>, <label>, <mark>
`

### Comments in HTML 
A **comment** is a piece of text in your HTML code that is **not shown in the browser**.  
It's only there to **help you (or other developers)** understand the code.

Syntax:
`<!-- This is a comment -->
`
### **Where Can You Use Comments?**

You can place comments:

-   **Above code** to explain what it does
    
-   **Beside code** for quick notes
    
-   **Temporarily disable code** without deleting it
🚫 Don’t put **sensitive info** in comments (like passwords or API keys).  
Even though users can’t see comments in the browser, they can still “View Source” and read them.


## HTML `<head>` & Metadata

### What is the `<head>` Section?

The `<head>` element is the **top section of an HTML document**, placed **between** the `<html>` and `<body>` tags.

The `<head>` section **does not display anything on the webpage**.  
Instead, it provides **information about the page** to the **browser**, **search engines**, and **external services**.

**Common Elements Inside `<head>`**

`<title>` Sets the title shown in browser tab and search results
```
<head>
    <title>My Awesome Website</title>
</head>

```
- `<meta>` Provides metadata (info about the page)

- `<link>`  Links external files like CSS , 
Favicon (Website Icon)
```
<link rel="icon" type="image/png" href="favicon.png">
```
This icon appears in the browser tab.

- `<script>` Loads JavaScript files

- `<style>` Internal CSS styling

- `<base>` Sets a base URL for relative links

- `<noscript>` Message shown if JS is disabled

## **`<meta>` Tags (Metadata)**
> Metadata = “data about data” — information that **describes the page** but is **not displayed**.
>

 **(a) Meta Charset**
 Specifies which **character encoding** the page uses.
 `<meta charset="UTF-8">`
 `UTF-8` is the standard — it supports most languages and special characters.
 **(b) Meta Viewport** (Very Important for Mobile 📱)
👉 Controls how the page is displayed on mobile devices.

`<meta  name="viewport"  content="width=device-width, initial-scale=1.0">` 

👉 This tells the browser:

-   Make the page width equal to the device width
    
-   Set the initial zoom to 1
    

✅ Without this, websites can look broken on mobile screens.

 **(c ) Meta Description** (Important for SEO)

Provides a short summary of the page.

`<meta  name="description"  content="This is a demo website for learning HTML.">` 

👉 Search engines like Google often display this text below your site title in search results.




