# Day 09: A deeper dive into flexbox
## Adding a hero image
If one of the children of a flex row is an image, by default it will get stretched out to match the height of the other children in that row. In order to remedy this, there are a few options. 

The first one is using the align-items property on the row:
```css
.row {
    display: flex;
    align-items: flex-start; /* align items on the top of the row instead of stretching them */
}
```
The second option is to wrap the `img` in a `div`. The `div` will still stretch as the flex item, but the `img` will keep its dimensions.
```html
<div class="row">
    <div class="hero-text">Some content...</div>
    <div><img class="hero-img" src="img/my-img.jpg"></div>
</div>
```

The final option is to set the align-self property on the image itself:
```css
.hero-img {
    align-self: flex-start;
}
```

## Column widths and flexbox
If the set widths of your flex items don't add up to 100% (for example: item-1 has {width: 60%}, item-2 has {width: 30%}), there'll be some space left on your row. To tell flexbox where to put that space, you set the justify-content property on the flex container.
```css
.row {
    display: flex;
    justify-content: space-between;
}
```

## Ensuring the image is responsive
When adding a hero image, you might have gone for the solution of wrapping it in a div. If this is the case, the image will not shrink of grow with the screen size, because the image is not a flex item. This will cause the image to overflow on small screen sizes and lead to side scrolling. To remedy this, add the following to the css file:
```css
img {
    max-width: 100%;
}
```
This is a good thing to always add to your css files, because it's useful for all images.