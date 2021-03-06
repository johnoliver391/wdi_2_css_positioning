![General Assembly Logo](http://i.imgur.com/ke8USTq.png)

# CSS Positioning

## Objectives

Students should, at the end of the lesson, be able to:

- Establish spacing inside and outside of elements using margin and padding.
- Explain the difference between different types of distance measurement in a web page, including 'px', '%', and 'em'.
- Use 'float' and 'clear' to stack elements alongside each other.
- Explain the difference between 'static', 'relative', 'absolute', and 'fixed' positioning.

## Overview

So far, we've mostly talked about using CSS for styling our page - adding colors, fonts, etc. Next, we'll be examining how CSS can be used to control a webpage' layout.

### Basic Positioning

* In addition to setting an element's `height` and `width`,elements have three other properties that can be used to explicitly control spacing with other elements.:
  1. 'Border' sets a perimeter around an element. In addition to specifying a color and a particular type of border, you can also specify a thickness.
  2. 'Margin' specifies spacing between the outside of an element's border and any adjacent elements.
  3. 'Padding' specifies spacing between the inside of an element's border and the contents of that element (which includes `height` and `width`!)

* All of these properties, including `height` and `width`, can be specified in the following terms
  * `px` : number of pixels
  * `%`  : ties an element's dimensions to the size of the element that contains it ("parent"). As a value of `height`, `%` refers to a fraction of the parent's `height`, but as a value of everything else, `%` refers to a fraction of the parent's `width` value.
  * `em` : ties dimensions to *font size* - one `em` is the width of the letter 'm'. For all dimensions except `font-size`, `em` will refer to the font size of the element; as a value for `font-size`, `em` refers to the font size of the *parent*

### Float and Clear
* The problem with block elements is that they always stack vertically, never side by side. This is because each block element has a 'new-line' built into it.
* This can be circumvented using the `float` property; floated elements pop out of the normal flow of a document and stack up in the upper left or upper right corner of their container, while the rest of the content wraps around them.
* As more elements get floated, they continue stacking up alongside the first floated element from left to right (if floated left; if floated right, elements stack up from right to left.)
* Setting `float` to `none` will cause that element not to be floated, but any inline elements it holds will still wrap around any floated elements.
* To make something fall beneath a set of floated elements, rather then wrapping around it, you can use the `clear` attribute; set clear to `left` to clear a `left` float, `right` to clear a `right` float, or `both` to clear either kind of float.

#### Lab
In pairs, create your own look-alikes for the following websites using what you've learned about so far about CSS positioning, including margin, padding, float and clear.
* http://boston.craigslist.org/
* http://en.wikipedia.org/wiki/Main_Page
* http://reddit.com
Start this process by drawing a box model - a guess as to how the elements on the page are broken out into `<div>`s (or equivalent elments).

## `Position`
* All of the rules that you've learn so far are based on one paradigm of positioning, called 'static' positioning. However, it's possible to change this paradigm and employ a different approach for positining elements using the `position` attribute.
* `relative` positioning allows you to define where an element should go based on where it would go if it was statically positioned. For instance, changing a static element's positioning to the following
  ```
  position: relative;
    left: 10 px
  ```
would shift it to the right by 10 pixels.
*`absolute` positioning allows you to define the position of an element with respect to the element that contains it. Giving an element the following positioning will place it ten pixels to the right and 20 pixels down from the top-left corner of its parent element.
  ```
  position: absolute;
    left: 10px;
    top: 20px;
  ```
*`fixed` positioning defines the position of an element with respect to the *view window*, essentially 'fixing' its position on the screen. Fixed positioning is frequently used in parallax scrolling.
```
position: fixed;
  left: 130px;
```
#### Lab
As in the previous exercise, work in pairs, create your own look-alike for the following websites; however, this time, try to use all four types of positioning.
* https://youtube.com
* https://twitter.com/GA
* http://artisansasylum.com/
* http://brooklynboulders.com/somerville/

## Notes
* Ordinarily, elements expand to hold their containers. However, floated elements are excluded from this, so floating an element may lead to its container's height shrinking down to nothing. Keep this in mind when using floats!
