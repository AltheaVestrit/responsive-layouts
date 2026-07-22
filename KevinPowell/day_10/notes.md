# CSS Grid
## Learn CSS Grid the easy way
### Basic setup
Set up your grid on the grid parent first:
- Make a container into a grid parent by using `display: grid`. 
- Set gaps by using the gap property. This will set both horizontal and vertical gaps.
- set columns and rows (setting up the rows is optional).
```css
.grid {
    display: grid;
    gap: 1.5rem;
    grid-template-columns: repeat(4, 1fr); /* create 4 equal columns (of each 1 fraction) */
}
```
Grid will implicitely create more rows when you need them. Don't add unnecessary complexity by explicitely defining them, unless you really need them.

### Finetuning with grid-row and grid-column
#### > Spanning multiple columns
Say you have a few grid items that need to span 2 columns, while the other items only span 1 column. Just give them a special class that you style as follows:
```css
.grid-col-span-2 {
    grid-column: span 2;
}
```

#### > Moving items around
Say you have a specific grid item that you want to place in a specific spot in the grid, where it doesn't get placed naturally. You can do that by targeting the item and styling it as follows:
```css
#special-grid-item {
    grid-column: 4;
    grid-row: 1 / span 2; /* this is a shorthand for grid-row-start and grid-row-end */
}
```

### Media queries
General guidelines:
- Use a media query for large screen sizes, make mobile screens the default.
- Keep the grid and gap definitions outside of the media query. This will let you keep the gap between items.
- Put everything regarding column and row definitions / finetuning in the media query.

An example:
```css
.grid {
    display: grid;
    gap: 1.5rem;
}

@media(min-width: 50em) {
    .grid {
        grid-template-columns: repeat(4, 1fr);
    }

    #special-grid-item {
        grid-column: 4;
        grid-row: 1 / span 2;
    }

    .grid-col-span-2 {
        grid-column: span 2;
    }
}
```

### Grid template areas
You can create named grid template areas on the grid parent, that can be used by the grid items. Set the grid parent as follows:
```css
.grid {
  display: grid;
  gap: 1.5rem;
  grid-auto-columns: 1fr;
  grid-template-areas:
    'one'
    'two'
    'three'
    'four'
    'five';
}
@media(min-width: 30em) {
  .grid {
    grid-template-areas:
     'one one'
     'two five'
     'three five'
     'four four';
  }
}
@media(min-width: 50em) {
  .grid {
    grid-template-areas:
     'one one two five'
     'three four four five';
  }
}
```
On each line within grid-template-areas, you specify which area lives in which column. An area can live in multiple columns and rows, just put them down whereever you need them to be. Also, you can name them whatever you want.

In the example, on mobile each row has just one area living there. On web however, theres a more complex design. You can visualize it like this:

|   |   |   |   |
|---|---|---|---|
| 1 | 1 | 2 | 5 |
| 3 | 4 | 4 | 5 |

Note that .grid has a property grid-auto-columns set to 1fr. This is to ensure that all columns are still the same width, even though they're not explicity declared in this setup.

When that's all done, you can set your grid items as follows:
```css
.grid:nth-child(1) {
    grid-area: one;
}
.grid:nth-child(2) {
    grid-area: two;
}
.grid:nth-child(3) {
    grid-area: three;
}
.
.
.
```

### Autofitting columns
If you want to let grid decide how many columns there should be, you can use grid-template-columns with a repeat function like this:
```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr))
}
```
In the minmax function, you define the miniumum size of each item and the maximum size of each item.
Example: suppose the grid container is 1000px wide. Three columns at minimum size: 300 + 300 + 300 = 900 px. That leaves 100px extra space. Because each column is allowed to be as big as 1fr, they share that space equally: 333px | 333px | 333px.

### Setting grid flow direction
By default, grid will place the elements first on the first row until that's full, then on the second row, and so forth. You can change that to a column flow direction like this:
```css
.grid {
    display: grid;
    grid-auto-flow: column;
}
```

## Flexbox or grid - How to decide?
Grid will always make cells align with each other. It's very structured. 

Flexbox is very good at intrinsic sizing based on content.

Use flexbox:
- if you want to place items next to each other, with each item just keeping their own size.
- if you want a flexible layout.

Use grid:
- if you want items to be the same size.
- if you want a rigid layout.

You'll often want to use grid for the big layout, and then flexbox for smaller elements within the big items on that same page.