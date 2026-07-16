# Day 01: Using percentages & avoiding heights
## Percentages vs Fixed widths
If you set a fixed width on an element, it might look good on your screen size, but it will break down on different screen sizes. Instead of defining pixels, use a percentage.

Basic css, without defining any widths, is responsive by default.

Block-level element: default width is 100% of the parent element.

Don't set a width on the body, always keep the body element on 100% width and use a child element to change widths.

Center a block-level element within its parent by setting a width and auto margins:
```css
.child {
    width: 80%;
    margin: 0 auto;
}
```

## Percentages on the child
Fixed width (e.g. 750px) on a child element will break down design: on smaller screen sizes, the element will overflow to the right and lead to side scrolling.

## Why it's a good idea to avoid hights
If you set a height on an element, your content will overflow on the bottom of the element.

Without a set height, the height will adapt to the content of the element and the size of the screen.

If you want to make sure your element (e.g. a header) always has some height, even if it has little content, you can use padding.
```css
padding: 5em; /* 16 * 5 = 80px */
```

`em`: the font size of the parent of the element you're setting the style on. By default, in most browsers it's 16px.