# CSS Introduction !

### What is CSS?

**CSS** stands for **Cascading Style Sheets**. It is a stylesheet language used to describe the look and formatting of a webpage written in **HTML** . While HTML provides the structure of a page (headings, paragraphs, images, etc.), CSS controls how those elements are presented (colors, fonts, layouts, spacing, and more).

### How browsers render HTML + CSS together (structure + style) : 
Browsers render **HTML + CSS** together through a series of well-defined steps that transform your code into the final visual web page
Here’s a clear breakdown:

 - **Parsing HTML (Structure)**
	-   The browser starts by reading the **HTML file**.
    -   It parses (reads and interprets) the HTML into a **DOM Tree (Document Object Model)** a hierarchical structure representing all elements on the page.
    Example : 
    in HTML File 
    ```
         <body>
      <h1>Hello</h1>
      <p>Welcome to my page.</p>
    </body>
becomes a tree like:

        Document
     └── body
          ├── h1
          └── p
 What is Dom ? 
 
 - **Parsing CSS (Style)**
	 -   The browser also reads all **CSS files** and inline styles.
    
	-   It parses them into another structure called the **CSSOM (CSS Object Model)**, which represents all the styling rules.
	Example : 
```
    h1 { color: blue; }
    p { font-size: 16px; }
```
becomes a CSSOM like: 
```
CSSOM
 ├── h1 → color: blue
 └── p → font-size: 16px

```
 -  **Combining DOM + CSSOM → Render Tree**
	 -   The **DOM (structure)** and **CSSOM (style)** are combined to create a **Render Tree**.
    
	-   This tree contains only the _visible elements_ (for example, `<head>` is skipped).
    
	-   Each node has visual information (like color, size, position).

###  Adding CSS to HTML
**Methods**
1.  **Inline CSS** – applied directly inside an HTML element with the `style` attribute. 
    
2.  **Internal CSS** – written inside a `<style>` tag within the HTML document.
    
3.  **External CSS** – stored in a separate `.css` file and linked with the HTML file (most common and recommended).

Lets Breakdown : 
 **Inline CSS** 
 This type of CSS is written directly inside the HTML element using the `style` attribute.

✅ Simple and quick  
❌Hard to maintain (you repeat styles everywhere)
Use this only for **testing** or **temporary fixes**.
**Example:**

`<p  style="color: red; font-size: 18px;">This is inline CSS</p>` 

Here, only that paragraph will be red and 18px in size.

 **Internal CSS**

This type of CSS is written inside the `<style>` tag, usually in the `<head>` section of the HTML file.

✅ Easier to manage than inline
❌ Only affects that one HTML file

**Example:**
```js
<!DOCTYPE html>
<html>
<head>
  <style>
    h1 {
      color: blue;
      text-align: center;
    }
    p {
      font-size: 16px;
    }
  </style>
</head>
<body>
  <h1>This is internal CSS</h1>
  <p>All paragraphs on this page will follow the same style.</p>
</body>
</html>

```

## **External CSS**

This type of CSS is written in a **separate file** (with a `.css` extension) and linked to the HTML file using the `<link>` tag.

✅  Best practice — clean, reusable, and fast
❌ Needs an extra file (but browsers cache it for speed)

**Example:**  
📂 Files:
-   `index.html`
    
-   `style.css`
    

**index.html**
```js 
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>This is external CSS</h1>
  <p>The styles are coming from another file!</p>
</body>
</html>
```
**style.css**
```js 
h1 {
  color: green;
  text-align: center;
}
p {
  font-size: 18px;
  color: gray;
}
```
## **Priority (Cascade) Order**

If all three are used, **browser priority** goes like this:

1.  **Inline CSS** → highest priority
    
2.  **Internal CSS**
    
3.  **External CSS** → lowest (but most maintainable)
    

So if all define the same property, the **closest rule to the element wins**.

## **Importing CSS**

You can also import one CSS file into another:

`@import url("theme.css");` 

👉 Place this at the top of your main stylesheet.

