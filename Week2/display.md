
# Understanding the `display` Property

Every HTML element has a **default display behavior**, controlled by the CSS `display` property.

It tells the browser **how an element is laid out** in the document flow:

### `display: block`

### 🔹 Behavior

- Starts on a **new line**.

- Takes up **full available width** by default.

- You can set **width, height, margin, and padding**.

- Respect vertical margins (they can collapse).

### Example

```
<div  style="display:block;  width:60%;">
  I am a block element. </div>
   <p  style="display:block;">I start on a new line.</p>
  ```

✅ Each box takes a full row.

### 🔹 Examples of block elements

`<div>`, `<p>`, `<h1>–<h6>`, `<section>`, `<article>`, `<header>`, `<footer>`

# `display: inline`

### 🔹 Behavior

- Does **not start on a new line**.

- Flows **in line with text**.

- Width & height **cannot** be changed directly.

- Only **horizontal padding/margins** work (top/bottom don’t push away neighbors).

### 🔹 Examples of inline elements

`<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<label>`

### 🔹 Example

```
<p>  This is
 <span  style="display:inline; background:yellow;">
 inline</span>
 text and it flows
  <span  style="display:inline;background:lightgreen;">
  together</span>. </p>
  ```

✅ Inline elements line up horizontally like words.

# `display: inline-block`

### 🔹 Behavior

- Mix between **inline** and **block**:

  - Flows inline (doesn’t break line).

  - **Can have width, height, padding, and margin**.

- Useful for **buttons, cards, nav items**, etc.

### 🔹 Example

```
<span  style="display:inline-block; width:120px;
 height:40px; ">  Button 1 </span>
  <span  style="display:inline-block; width:120px;
   height:40px;">  Button 2 </span>
  ```

✅ Inline-block lets you design elements side-by-side **while still controlling box dimensions**.

## CSS  Flexbox

**Flexbox** (Flexible Box Layout) is used for **1D layouts** system (row _or_ column).  designed to organize items **along a single axis** — either horizontally (row) or vertically (column).

It makes aligning, distributing, and resizing elements inside a container far easier and more predictable than older methods.

## 1) Flexbox Structure

A Flexbox layout always has two parts:

`Flex Container  →  the parent element with display:flex
Flex Items      →  the direct children of that container`

```
<section class="container">
  <atricle class="item">Box 1</atricle>
  <atricle class="item" >Box 2</atricle>
  <atricle class="item" >Box 3</atricle>
</section>

```

```
.container { 
display: flex; /* turns on flexbox */
 } 
Now, `.container` is the flex container,
 and its children are flex items. 
```

----------

## The Flex Axes

Flexbox works on two perpendicular axes:

```
+--------------------------------------------+
Main Axis → flex-direction: row (default) | 
 |  Cross Axis ↓                        | 
  +------------------------------------------+
 ```

- **Main axis** = direction items are laid out (`row` or `column`)

- **Cross axis** = perpendicular to main axis

This concept is key because most flex-alignment properties refer to _main_ vs _cross_ axis.

## Container Properties

A. **`display`**
Activates Flexbox.

```
.container { display: flex; } /* block-level flex container */ 
 .container { display: inline-flex; }/* inline-level flex container */
```

B. `flex-direction`
Defines the **main axis direction**.

- `flex-direction` → row (left → right) | row-reverse (right → left) | column(top → bottom) | column-reverse (bottom → top)
    `

C. `flex-wrap`
Controls whether items wrap to new lines if there’s not enough space.
 `flex-wrap: wrap |  nowrap(default) | wrap-reverse(opposite direction) ;`

 D. `flex-flow`
Shorthand for `flex-direction` + `flex-wrap`.

`.container { flex-flow: row wrap; }`

 E. `justify-content`
Aligns items **along the main axis** (horizontal if row, vertical if column).

- flex-start (default) | flex-end | center | space-between | space-around | space-evenly

 F. `align-items`
Aligns items **along the cross axis** (vertical if row).

- flex-start | flex-end | center | stretch (default)| baseline

   G. `align-content`
Used when there are **multiple rows/columns** (wrap enabled).  
Controls spacing between the rows themselves (like `justify-content` but on the cross axis).
  
- flex-start (default) | flex-end | center | space-between | space-around | space-evenly

----------

# Item Properties

These are applied to **individual flex items** (children).

 A. `order`
Changes the **visual order** of items (default = 0).

`.item1 { order: 2; } .item2 { order: 1; }`

✅ Items are rearranged without changing HTML order.

 B. `flex-grow`
Defines how much an item **expands** relative to others  to fill extra space.
`.item1 { flex-grow: 1; } .item2 { flex-grow: 2; } /* takes twice as much space */`

C. `flex-shrink`
Defines how an item **shrinks** when space is limited.

`.item { flex-shrink: 0; } /* prevent shrinking */`

 D. `flex-basis`
Sets the **starting size** of the item before space distribution.(default size before grow/shrink)
`.item { flex-basis: 200px; }`

 E. `flex`
Shorthand for all three:
`.item { flex: flex-grow flex-shrink flex-basis; }`

Example:

`.item { flex: 1  1  150px; } /* grow=1, shrink=1, basis=150px */`

Common pattern:
`.item { flex: 1; } /* equal flexible boxes */`

  F. `align-self`

Overrides `align-items` for one specific item.

`.item3 { align-self: flex-end; }`

## **Debugging & Tips**

   ✅ Use **browser DevTools → Layout → Flexbox overlay** (in Chrome/Edge/Firefox)  
✅ Use **gap** (instead of margins) for clean spacing:

`.container { display: flex; gap: 20px; }`

✅ Use `min-width` or `max-width` on items for better responsiveness.  
✅ Combine Flexbox for alignment **inside components** (and Grid for full page layout).

>Flexbox gives you precise control over alignment, spacing, and distribution of items along one axis — simple, powerful, and responsive.


## CSS Grid Layout 

check [Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) details 