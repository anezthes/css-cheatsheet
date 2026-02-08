# CSS Selectors Cheatsheet

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
