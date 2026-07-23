# Day 18: Challenge solution & Mobile-first
Following along with Kevin's solution to Flexbox Challenge #4. Below are some notes from things Kevin mentioned during the video.

## Using min-height
In general, it's never okay to set a fixed height on things. However, it can be useful to set a `min-height` on a section for example, instead of setting padding.

## Structuring your css file
These are the things you want to put in your css file, from top to bottom. General rule: typography first, layout second.
1. Import other stylesheets, like google fonts.

2. Set box sizing to border-box.
```css
*, *::before, *::after {
    box-sizing: border-box;
}
```

3. Set the most general typography on your body tag. Also, set the body margins to 0.
```css
body {
    margin: 0;
    font-family: Roboto, sans-serif;
    font-size: 1.3125rem;
    line-height: 1.6;
    color: #222c2a;
}
```
4. Set max-width on images so they don't get stretched.
```css
img {
    max-width: 100%;
}
```
5. Set up some general typography, plus margins and padding on much-used tags (like `h1`, `h2`, `section`, etc.).
6. Style the utility classes, like `.container` or `row`.
7. Style the rest of the page top to bottom, following the order of the html file.
8. Media queries go at the bottom. Within the media queries, put typography first, layout second.