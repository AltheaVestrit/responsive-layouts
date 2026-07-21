# Day 03: Enter max-width
## Adding in a max-width
If you set a width, always use a percentage. But to limit the size, you can set a max-width in pixels.
So a nice example of a centered element including a max-width:
```css
.container {
    width: 80%;
    max-width: 750px;
    margin: 0 auto;
}
```
Most of the time, you won't need `min-width`, as this will make the layout not responsive.