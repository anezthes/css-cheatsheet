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
