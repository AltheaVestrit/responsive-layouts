# Day 11: Getting fancy with navigations
## Flex-grow and flex-shrink
Flex items have a flex-grow and flex-shrink property which dictate their behavior with regard to size changes. Here are a few examples of how these work. 

*To really show the effect of flex-shrink and flex-grow, a fixed width will be set for the container (normally, you'll set the width in percentages, not pixels).*
### Default
```css
.flex-item {
    width: 700px;
    flex-grow: 0;
    flex-shrink: 1;
}
```
This is the default. It means that this flex item is allowed to shrink as much as necessary, but is not allowed to grow larger than its set width.
### No shrink
```css
.flex-item {
    width: 700px;
    flex-grow: 1;
    flex-shrink: 0;
}
```
The flex item is allowed to grow larger than 700px, but it is not allowed to get smaller than its set width. This means that in case the item has less than 700px available (for example because its container is smaller than 700px), the item will overflow.
### Grow and shrink
```css
.flex-item {
    width: 700px;
    flex-grow: 1;
    flex-shrink: 1;
}
```
In this situation, the ideal width is set to 700px, but the item is allowed to grow as big as it can, and is also allowed to shrink as much as needed.
### Set width
```css
.flex-item {
    width: 700px;
    flex-grow: 0;
    flex-shrink: 0;
}
```
The flex item is not allowed to grow or shrink, so it will always be 700px. If the container is very large, it will leave empty space. If the container is very small, the item will overflow the container.

## Centering things the easy way
Even when you're working with flexbox, or even a flexbox within a flexbox, the easiest way to center an item between two other items is still:
```css
.item--center {
    margin: 0 auto;
}
```