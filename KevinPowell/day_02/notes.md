# Day 02: Getting familiar with relative units
## CSS em and rem explained
### `em`
For font-sizes, 1 em is equal to the font-size of the parent element.
For everyting else, em looks at the font-size of the element itself.

This means that em's compound: they add up. Consider this example:
```html
<!-- index.html -->

<div class="parent">
    <div class="child">
        Some text
        <div class="grandchild">More text</div>
    </div>
</div>
```
```css
/* style.css */

.parent {
    font-size: 16px;
}
.child {
    font-size: 2em; /* font-size = 16*2 = 32px */
}
.grandchild {
    font-size: 2em; /* font-size = 32*2 = 64px */
}
```
Changing the font size on the `.parent` element means the effect is doubled in the `.child` element, and multiplied by 4 in the `.grandchild` element.

### `rem`
rem stands for 'root em'. It is relative to the root font size, or the font size of the `html` element. A big advantage of this is that it doesn't compound.

### When to use
Use these units anywhere you can specify a size: font-size, margin, padding, width, height...

em's are really useful when specifying padding on an element like a button, because it changes with the font-size. An example:
```css
.my-button {
    padding: 1em 3em;
}
```
This way, the proportions will always look good, even if the font size changes.

For margins, you most likely will use rem's, so that the spacing is always the same regardless of font sizes.
em's can also be useful in some situations. Example: maybe you want the margin-bottom on a paragraph or a heading to depend on your font size.

rem's are also nice for font-sizes, so that you can change the root font size to alter the look of the whole webpage without throwing things out of wack.

## Why you shouldn't set font-sizes using em
Another `em` font size compounding example you want to avoid:
```css
/* style.css */

ul {
    font-size: 1.5em;
}
```
```html
<!-- index.html -->

<ul> <!-- font-size: 1.5em = 1.5*16 = 24px -->
    <li>Text</li>
    <li>Text</li>
    <li>Text</li>
    <ul> <!-- font-size: 1.5em = 1.5*24 = 36px -->
       <li>Text</li>
        <li>Text</li>
        <li>Text</li> 
        <ul> <!-- font-size: 1.5em = 1.5*36 = 54px -->
            <li>Text</li>
            <li>Text</li>
            <li>Text</li> 
        </ul>
    </ul>
</ul>
```

Recommendations: 
- Never use em's for font size to avoid compounding! rem's are fine.
- Don't change the html font-size, keep it at 16px so you get a feeling for sizes in rem's.

## Summary of when to use what
These are general recommendations, not rules.
- Padding: use `em`
- Margins:
    - if you want consistent distances: use `rem`
    - if you want margins dependent on font size (specifically margin-bottom on text element): use `em`
- Font sizes: use `rem`
- Don't change the html / root font size