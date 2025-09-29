
#  📦 CSS Box Model

Every element in a webpage is treated as a **rectangular box**.  
The **box model** describes the space an element takes up, including **content, padding, border, and margin**.
![A Beginner's Guide to the CSS Box Model - DEV Community](https://media2.dev.to/dynamic/image/width=400%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2F18sfy7anxl7uj5soub2i.png)
## Structure of the Box Model

From **inside to outside**:

1.  **Content** → The actual text, image, or element content.
```
div {
  width: 200px;
  height: 100px;
}

``` 
2.  **Padding** → Space between the content and the border (inside background).
Space **inside** the element, around content.
```
div {
  padding: 20px;              /* all sides */
  padding: 10px 15px;         /* top/bottom 10px, left/right 15px */
  padding: 5px 10px 15px 20px;/* top, right, bottom, left */
}

```
    
3.  **Border** → The line around the element. Surrounds the padding & content.
```
div {
  border: 2px solid black;
  border-radius: 10px; /* rounded corners */
}
```    
4.  **Margin** → Space outside the border, separating the element from others.
 ```
 div {
  margin: 20px;               /* all sides */
  margin: 10px auto;   /* top/bottom 10px, left/right auto (centered) */
}
```
## Total Element Size (Default)

By default, the **total size** of an element =

`Total width  = content width + padding left + padding right + border left + border right
Total height = content height + padding top + padding bottom + border top + border bottom` 

Example:

`div { width: 200px; /* content */  padding: 10px; border: 5px solid; margin: 20px;
}` 

👉 Total width = `200 + 10 + 10 + 5 + 5 = 230px`  
👉 Total height = `content height + 10 + 10 + 5 + 5`

----------

## 🔹 `box-sizing` Property

By default, CSS uses **`content-box`**, but we can change it:

-   **`content-box`** (default): Width/height apply to **content only**.
    
-   **`border-box`**: Width/height include **padding + border**.
    

Example:

`div { width: 200px; padding: 10px; border: 5px solid; box-sizing: border-box; /* total size stays 200px */ }` 

👉 With `border-box`, the element **never grows bigger** than the defined width/height.



📦 CSS Box Model
Every element in a webpage is treated as a rectangular box.
The box model describes the space an element takes up, including content, padding, border, and margin.
A Beginner's Guide to the CSS Box Model - DEV Community

Structure of the Box Model
From inside to outside:

Content → The actual text, image, or element content.
div {
  width: 200px;
  height: 100px;
}

Padding → Space between the content and the border (inside background).
Space inside the element, around content.
div {
  padding: 20px;              /* all sides */
  padding: 10px 15px;         /* top/bottom 10px, left/right 15px */
  padding: 5px 10px 15px 20px;/* top, right, bottom, left */
}

Border → The line around the element. Surrounds the padding & content.
div {
  border: 2px solid black;
  border-radius: 10px; /* rounded corners */
}
Margin → Space outside the border, separating the element from others.
div {
 margin: 20px;               /* all sides */
 margin: 10px auto;   /* top/bottom 10px, left/right auto (centered) */
}
Total Element Size (Default)
By default, the total size of an element =

Total width = content width + padding left + padding right + border left + border right Total height = content height + padding top + padding bottom + border top + border bottom

Example:

div { width: 200px; /* content */ padding: 10px; border: 5px solid; margin: 20px; }

👉 Total width = 200 + 10 + 10 + 5 + 5 = 230px
👉 Total height = content height + 10 + 10 + 5 + 5

🔹 box-sizing Property
By default, CSS uses content-box, but we can change it:

content-box (default): Width/height apply to content only.

border-box: Width/height include padding + border.

Example:

div { width: 200px; padding: 10px; border: 5px solid; box-sizing: border-box; /* total size stays 200px */ }

👉 With border-box, the element never grows bigger than the defined width/height.

Markdown 2274 bytes 335 words 77 lines Ln 1, Col 0HTML 1443 characters 305 words 41 paragraphs