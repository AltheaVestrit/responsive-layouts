# Day 08: Flexbox Basics
## An introduction to flexbox
Create a flex container by setting display to flex. This will make the children of the container flex items. We'll assume we have a flex parent of class `.row`, with child elements of class `.col`.
```css
.row {
    display: flex;
}
```

Block elements (like `div`) have a width set to 100% by default. Flex items are only as big as they need to be. The content of the flex item is pushing them to be bigger, making the flex items within a flex container compete for space. If you want to ensure all items within a flex row have the same width, you can set the width of the flex items to 100%:
```css
.col {
    width: 100%;
}
```
What is happening now is the following:
- All flex items within the row want to be 100% of the parent's width.
- Because they are children of a flex container, flexbox is forcing them to be on the same row.
- As a result, they'll just share the available space equally.
- If there is really not enough space to fit all flex items, they'll overflow the container.

## Adding space in between columns
On the flex-parent, you can set a gap to create space between the flex items:
```css
.row {
    gap: 60px;
}
```

In case gap is not available, you can do a trick in css using the `+` combinator in the selector to only select `.col` elements that have another `.col` element before it:
```css
.col + .col {
    margin-left: 60px;
}
```