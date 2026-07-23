# Day 15: Intro to media queries
## Basics
A basic example:
```css
/* 600px or bigger */
@media(min-width:600px) {
    .example {
        background-color: olivedrab;
    }
}
```
General rules / advice:
- Always style your page mobile-first.
- The order of the media queries matters! The last media query is applied last.
- For the same reason, always put your media queries at the end of the css file.
- Don't use different media queries for different parts of the web page.
- Use the minimum number of breakpoints that you need to have a functional design. Don't overcomplicate things.

## Breakpoints
The right breakpoints are often determined by looking at the most common screensizes. They can be devided into 5 categories
- Phone: 0px - 600px
- Tablet portrait: 600px - 900px
- Tablet landscape: 900px - 1200px
- Desktop: 1200px - 1800px
- Big desktop: 1800px - ...

In general, your breakpoints will lie around these values: **600px, 900px, 1200px**. You probably don't care about the big desktops.

But even more important than this: let the design dictate the breakpoints.