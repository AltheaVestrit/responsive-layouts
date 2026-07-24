# Improving web design skills
## Kevin Powell
[Conquering Responsive Layouts](https://courses.kevinpowell.co/p/courses/conquering-responsive-layouts)

## Design tips
- General tips: https://medium.com/refactoring-ui/7-practical-tips-for-cheating-at-design-40c736799886
- A little bit about white space: https://refactoring-ui.nyc3.cdn.digitaloceanspaces.com/Refactoring%20UI%20-%20Start%20with%20too%20much%20white%20space.pdf
- Building your Color Palette: https://refactoringui.com/previews/building-your-color-palette/
- More about colors: search on YouTube for "web color palette"
- About using labels in the UI: https://refactoringui.com/previews/labels-are-a-last-resort/

## Inspiration
- Dashboard UI: https://vimeo.com/305601486/a1388ac3a9

## Class Naming Convention
[BEM - Block Element Modifier](https://getbem.com/). 

General naming rule:

    block__element--modifier-value

For example:
```html
<form class="form form--theme-xmas form--simple">
  <input class="form__input" type="text" />
  <input
    class="form__submit form__submit--disabled"
    type="submit" />
</form>
```

### Block
Standalone entity that is meaningful on its own. Examples:
- header | container | menu | checkbox | input

### Element
A part of a block that has no standalone meaning and is semantically tied to its block. Examples:
- menu item | list item | checkbox caption | header title

### Modifier
A flag on a block or element. Use them to change appearance or behavior. Examples:
- disabled | highlighted | checked | fixed | size big | color yellow