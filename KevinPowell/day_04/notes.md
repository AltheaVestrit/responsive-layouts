# Day 04: Extra curricular activities
## CSS Viewport Units
Random tip! Set box-sizing to border-box on your all elements for easier image sizing:
```css
*, *::before, *::after {
    box-sizing: border-box;
}
```

### Using `vh` and `vw` versus percentages
`vh` and `vw` stand for viewport height and viewport width. `1vh` is one percent of the viewport height.
Compare this to using percentages: setting a percentage is always relative to the parent element, not the viewport.

A nice use for these units is making the padding on an element depend on your viewport size:
```css
.container {
    padding: 10vh 0;
}
```
In this example, the padding will grow or shrink with your viewport height.

Another good use for these units is making a title font-size depend on viewport width:
```css
.hero-title {
    font-size: 8vw;
}
```
This will keep the font-size of the title proportional, no matter what your screen size might be.
This negates the need for media queries a little bit, but you'll probably still want to use a media query with a set font-size for really big or really small screen sizes. You don't want the title to get too big or too small. 
Don't do this for paragraph text though, you always want your paragraph font-size to be the same comfortable reading size.

### Using `vmin` and `vmax`
`vmin` and `vmax` look at whichever viewport unit (height or width) is smaller or bigger, respectively. Consider the following example:
```css
.container {
    height: 80vmax;
}
```
This will set the height of the `.container` element to 80% of the viewport height or width, whichever one of them is the larger one.

A good use for these units is sizing a title. In the section above, we sized it with `vw`. But at large screen sizes, this makes the title grow too big. A good alternative might be using `vmin`:
```css
.hero-title {
    font-size: 8vmin;
}
```
As long as the width is smaller than the height (portrait screen layout), the title font-size changes with the viewport width. But as soon as the width becomes bigger than the height (landscape screen layout), the font-size stops increasing in size.

`vmax` will not be as useful and won't be used as much as `vmin`.

### General advice
Most of the time, you won't use viewport units. If you do, make sure you do extensive tests with all possible different screen sizes and screen orientations. The best use cases are:
- using `vh` for setting element heights, or 
- using viewport units for setting font-size on the big titles in your design.