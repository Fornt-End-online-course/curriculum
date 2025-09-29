




##  CSS  Flexbox
**Flexbox** (Flexible Box Layout) is used for **1D layouts** (row _or_ column).  
It makes it easy to align, distribute, and reorder items inside a container.
## 1) **Basic Structure**

```
.container { 
display: flex; /* turns on flexbox */
 } 
.item { 
flex: 1; /* makes items flexible */
 }
``` 

----------

## 2) **Main Properties of Flexbox**

### On the **Container** (`display: flex;`)

-   **`flex-direction`** → row | row-reverse | column | column-reverse
    
    `flex-direction: row; /* horizontal (default) */  flex-direction: column;/* vertical */` 
    
-   **`justify-content`** → alignment along **main axis**
    
    -   flex-start | flex-end | center | space-between | space-around | space-evenly
        
    
    `justify-content: space-between;` 
    
-   **`align-items`** → alignment along **cross axis**
    
    -   flex-start | flex-end | center | stretch | baseline
        
    
    `align-items: center;` 
    
-   **`flex-wrap`** → wrap items onto new lines
    
    `flex-wrap: wrap;` 
    
-   **`align-content`** → space between multiple lines
    
    `align-content: space-around;` 
    

----------

### On the **Items**

-   **`flex-grow`** → how much the item grows relative to others.
    
-   **`flex-shrink`** → how much it shrinks.
    
-   **`flex-basis`** → default size before grow/shrink.
    
-   **`flex` (shorthand)** → `flex-grow flex-shrink flex-basis`.
    
    `.item1 { flex: 1; } .item2 { flex: 2; }` 
    
-   **`align-self`** → override alignment per item.
    
    `.item { align-self: flex-end; }`


## CSS Grid

**Grid** is for **2D layouts** (rows _and_ columns).  
It’s more powerful than Flexbox for full-page or complex layouts.

----------

## 1) **Basic Structure**

`.container { display: grid; grid-template-columns: 1fr 1fr 1fr; /* 3 equal columns */  grid-template-rows: auto 200px auto; /* 3 rows */  gap: 10px; /* space between grid items */ } .item { background: lightblue;
}` 

----------

## 2) **Main Properties of Grid**

### On the **Container**

-   **`grid-template-columns` & `grid-template-rows`**
    
    `grid-template-columns: 200px  1fr 2fr; /* fixed + flexible */  grid-template-rows: 100px auto;` 
    
-   **`gap`** (or `row-gap` / `column-gap`) → spacing between items.
    
-   **`justify-items`** → horizontal alignment inside each cell.
    
-   **`align-items`** → vertical alignment inside each cell.
    
-   **`justify-content`** / **`align-content`** → alignment of the whole grid.
    

----------

### On the **Items**

-   **`grid-column`** → span columns.
    
    `.item1 { grid-column: 1 / 3; } /* spans from col 1 to 2 */` 
    
-   **`grid-row`** → span rows.
    
    `.item2 { grid-row: 1 / 3; } /* spans two rows */` 
    
-   **`grid-area`** → assign a named area.



