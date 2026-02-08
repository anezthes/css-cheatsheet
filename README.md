# CSS Selector Cheatsheet

## Type Selector

Targets all elements of a given tag.

```css
p {
  color: blue;
}
```

Selects all `<p>` elements.

---

## Class Selector

Targets elements with a specific class.

```css
.card {
  border: 1px solid black;
}
```

Selects any element with `class="card"`.

---

## ID Selector

Targets a single element with a specific ID.

```css
#header {
  background: gray;
}
```

Selects the element with `id="header"`.

---

## Descendant Selector

Targets elements inside another element (any depth).

```css
div p {
  font-size: 16px;
}
```

Selects all `<p>` elements inside a `<div>`.

---

## Attribute Selector

Targets elements based on attributes.

```css
input[type='text'] {
  border: 2px solid blue;
}
```

### Common Attribute Patterns

```css
a[href]            /* has attribute */
a[href='#']        /* exact value */
a[href^='https']   /* starts with */
a[href$='.pdf']    /* ends with */
a[href*='docs']    /* contains */
```

# CSS Cascade & Specificity Cheatsheet

## 1. Cascade

Determines which CSS rules apply when multiple rules target the same element.
Order of priority:

1. IDs (`#id`)
2. Classes and attributes (`.class`, `[attr]`)
3. Element types (`div`, `p`)

Later rules override earlier ones if specificity is equal.

---

## 2. Specificity

Points assigned to selectors to resolve conflicts:

| Selector Type   | Points |
| --------------- | ------ |
| ID selector     | 100    |
| Class/attribute | 10     |
| Type            | 1      |

Example:

```css
p {
  color: blue; /* 1 point */
}
.class p {
  color: red; /* 11 points => wins */
}
#id p {
  color: green; /* 101 points => wins */
}
```

---

## 3. Inheritance

Some CSS properties naturally inherit from parent elements:

**Inherited by default:**

* `color`
* `font-family`
* `font-size`
* `line-height`
* `visibility`

**Not inherited by default:**

* `margin`
* `padding`
* `border`
* `width` / `height`
* `background`

# CSS Box Model Cheatsheet

## 1. What is the Box Model?

Every HTML element is a rectangular box. Understanding boxes is essential because everything in CSS involves boxes.

---

## 2. Layers of the Box Model (Inside → Outside)

1. **Content** – Text, image, or whatever is inside the element
2. **Padding** – Space inside the element, between content and border
3. **Border** – Edge around the padding (visible or invisible)
4. **Margin** – Space outside the element, separating it from other elements

---

## 3. Padding vs Margin

* **Padding** – Inside the element. Pushes content away from the border.
* **Margin** – Outside the element. Pushes other elements away from the box.

Example:

```css
.box {
  padding: 16px;           /* space inside */
  margin: 16px;            /* space outside */
  border: 2px solid black;
  background-color: lightblue;
}
```

**Visual notes for beginners:**

* Padding increases clickable area (useful for buttons!)
* Margin does not; it only separates elements
* Background color covers padding, but not margin

---

## 4. Box Sizing

By default, `width` and `height` do **not** include padding or border:

```css
div {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
}
/* Total width = 200 + 20 + 20 + 5 + 5 = 250px */
```

To make sizing easier, use:

```css
* {
  box-sizing: border-box;
}
/* Width includes padding and border. Less math, fewer surprises */
```

Widely recommended for beginners and professionals alike.

# CSS Overflow Cheatsheet

## 1. What is Overflow?

The `overflow` property controls what happens when content inside a box is larger than the box itself.

---

## 2. Overflow Values

1. **visible** (default)

   * Content spills out of the box
   * Box does **not** clip the content

```css
div {
  overflow: visible;
}
```

2. **hidden**

   * Content that exceeds the box is **clipped**
   * No scrollbars appear

```css
div {
  overflow: hidden;
}
```

3. **scroll**

   * Always shows **scrollbars** (even if content fits)
   * Allows scrolling

```css
div {
  overflow: scroll;
}
```

4. **auto**

   * Scrollbars appear **only if content overflows**

```css
div {
  overflow: auto;
}
```

---

## 3. Notes for Beginners

* Use `hidden` to **cut off extra content** without scrollbars
* Use `auto` for **responsive scrolling**
* If you don't set `overflow`, the default is `visible`, meaning content may spill out of the box

# CSS Flexbox Cheatsheet

## 1. What is Flexbox?

One-dimensional layout system for arranging items in a row or a column. It is designed for alignment, spacing, and distributing space between items.

---

## 2. display: flex

Turns an element into a flex container. Only direct children are flex items.

```css
.container {
  display: flex;
}
```

---

## 3. flex-direction

Controls the main axis direction.

```css
.container {
  flex-direction: row;
}
```

Values:

* row            (default: left to right)
* row-reverse    (right to left)
* column         (top to bottom)
* column-reverse (bottom to top)

---

## 4. justify-content

Aligns items along the main axis.

```css
.container {
  justify-content: center;
}
```

Values:

* start
* end
* center
* space-between
* space-around
* space-evenly

---

## 5. align-items

Aligns items along the cross axis (perpendicular to the main axis).

```css
.container {
  align-items: center;
}
```

Values:

* stretch (default)
* start
* end
* center
* baseline

---

## 6. gap

Controls spacing between flex items.

```css
.container {
  gap: 16px;
}
```

Note:

* `row-gap` and `column-gap` can be used to control spacing independently

---

## 7. Common Flexbox Pattern

Center content horizontally and vertically:

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```
