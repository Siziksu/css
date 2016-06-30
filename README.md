# CSS

Learning CSS

## The display Property

The `display` property is the most important CSS property for controlling layout. It specifies if/how an element is displayed.

Every HTML element has a default display value depending on what type of element it is. The default display value for most elements is `block` or `inline`.

#### Block-level Elements

A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can). The `<div>` element is a block-level element. Examples of block-level elements:

- `<div>`
- `<h1> - <h6>`
- `<p>`
- `<form>`
- `<header>`
- `<footer>`
- `<section>`

#### Inline Elements

An inline element does not start on a new line and only takes up as much width as necessary. Examples of inline elements:

- `<span>`
- `<a>`
- `<img>`

#### Display: none;

`display: none;` is commonly used with JavaScript to hide and show elements without deleting and recreating them. The `<script>` element use `display: none;` as its default.

#### Hide an Element - display:none or visibility:hidden?

Hiding an element can be done by setting the `display` property to `none`. The element will be hidden, and the page will be displayed as if the element is not there. `visibility:hidden;` also hides an element. However, the element will still take up the same space as before. The element will be hidden, but still affect the layout.

#### The inline-block Value

It has been possible for a long time to create a grid of boxes that fills the browser width and wraps nicely (when the browser is resized), by using the float property. However, the `inline-block` value of the `display` property makes this even easier. This `inline-block` elements are like `inline` elements but they can have a width and a height. No clear property is needed after using this value.

## Using width and max-width;

A block-level element always takes up the full width available (stretches out to the left and right as far as it can).

Setting the `width` of a block-level element will prevent it from stretching out to the edges of its container. Then, you can set the margins to auto, to horizontally center the element within its container. The element will take up the specified width, and the remaining space will be split equally between the two margins.

**Note:** A problem appears when the browser window is smaller than the width of the element. The browser then adds a horizontal scrollbar to the page. Using `max-width` instead, in this situation, will improve the browser's handling of small windows. This is important when making a site usable on small devices.

## The position Property

The `position` property specifies the type of positioning method used for an element. There are four different position values:

- `static`
- `relative`
- `fixed`
- `absolute`

Elements are then positioned using the top, bottom, left, and right properties. However, these properties will not work unless the position property is set first. They also work differently depending on the position value.

#### position: static;

*HTML elements are positioned static by default*.

Static positioned elements are not affected by the top, bottom, left, and right properties. An element with `position: static;` is not positioned in any special way; it is always positioned according to the normal flow of the page.

#### position: relative;

An element with `position: relative;` is positioned relative to its normal position. Setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted away from its normal position. Other content will not be adjusted to fit into any gap left by the element. So the element will still take up the same space as before affecting the layout.

```css
div.relative {
    position: relative;
    left: 40px;
    top: 40px;
    padding: 5px;
    border: 1px solid #6799a9;
}
```

#### position: fixed;

An element with `position: fixed;` is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element. A fixed element does not leave a gap in the page where it would normally have been located.

```css
div.fixed {
    position: fixed;
    bottom: 20px;
    right: 20px;
    width: 300px;
    padding: 5px;
    border: 1px solid #6799a9;
}
```

#### position: absolute;

An element with `position: absolute;` is positioned relative to the nearest positioned ancestor. However; if an absolute positioned element has no positioned (`fixed` or `relative`) ancestors, it uses the document body, and moves along with page scrolling.

```css
div.absolute {
    position: absolute;
    top: 20px;
    right: 0;
    width: 300px;
    height: 100px;
    border: 1px solid #6799a9;
}
```

#### Overlapping Elements

When elements are positioned, they can overlap other elements. The `z-index` property specifies the stack order of an element (which element should be placed in front of, or behind, the others). An element can have a positive or negative stack order.

```css
img {
    z-index: -1;
}
```

## The float and clear Properties

The `float` property specifies whether or not an element should float. The `clear` property is used to control the behavior of floating elements.

Elements after a floating element will flow around it. To avoid this, use the `clear` property. The `clear` property specifies on which sides of an element floating elements are not allowed to float.

```css
img {
    float: right;
    margin: 0 0 10px 10px;
}
```
```css
div {
    clear: left;
}
```

#### overflow: auto;

If an element is taller than the element containing it, and it is floated, it will overflow outside of its container. Then we can add overflow: auto; to the containing element to fix this problem.

```css
div.container {
    overflow: auto;
}
```

## Selectors
|Selector|Example|Description|
|---|---|---|
|`.class`|`.info`|Selects all elements with `class="intro"`|
|`#id`|`#first-name`|Selects the element with `id="first-name"`|
|`*`|`*`|Selects all elements|
|`element`|`p`|Selects all `<p>` elements|
|`element, element`|`div, p`|Selects all `<div>` elements and all `<p>` elements|
|`element element`|`div p`|Selects all `<p>` elements inside `<div>` elements|
|`element > element`|`div > p`|Selects all `<p>` elements where the parent is a `<div>` element|
|`element + element`|`div + p`|Selects all `<p>` elements that are placed immediately after `<div>` elements|
|`element1 ~ element2`|`p ~ ul`|Selects every `<ul>` element that are preceded by a `<p>` element|
|`[attribute]`|`[target]`|Selects all elements with a target attribute|
|`[attribute = value]`|`[target = _blank]`|Selects all elements with `target="_blank"`|
|`[attribute ~= value]`|`[title ~= flower]`|Selects all elements with a title attribute containing the word "flower"|
|`[attribute `&#124;`= value]`|`[lang `&#124;`= en]`|Selects all elements with a lang attribute value starting with "en"|
|`[attribute ^= value]`|`a[href ^= "https"]`|Selects every `<a>` element whose href attribute value begins with "https"|
|`[attribute $= value]`|`a[href $= ".pdf"]`|Selects every `<a>` element whose href attribute value ends with ".pdf"|
|`[attribute *= value]`|`a[href *= "google"]`|Selects every `<a>` element whose href attribute value contains the substring "google"|
|`:active`|`a:active`|Selects the active link|
|`::after`|`p::after`|Insert something after the content of each `<p>` element|
|`::before`|`p::before`|Insert something before the content of each `<p>` element|
|`:checked`|`input:checked`|Selects every checked `<input>` element|
|`:disabled`|`input:disabled`|Selects every disabled `<input>` element|
|`:empty`|`p:empty`|Selects every `<p>` element that has no children (including text nodes)|
|`:enabled`|`input:enabled`|Selects every enabled `<input>` element|
|`:first-child`|`p:first-child`|Selects every `<p>` element that is the first child of its parent|
|`::first-letter`|`p::first-letter`|Selects the first letter of every `<p>` element|
|`::first-line`|`p::first-line`|Selects the first line of every `<p>` element|
|`:first-of-type`|`p:first-of-type`|Selects every `<p>` element that is the first `<p>` element of its parent|
|`:focus`|`input:focus`|Selects the input element which has focus|
|`:hover`|`a:hover`|Selects links on mouse over|
|`:in-range`|`input:in-range`|Selects input elements with a value within a specified range|
|`:invalid`|`input:invalid`|Selects all input elements with an invalid value|
|`:lang(language)`|`p:lang(it)`|Selects every `<p>` element with a lang attribute equal to "it" (Italian)|
|`:last-child`|`p:last-child`|Selects every `<p>` element that is the last child of its parent|
|`:last-of-type`|`p:last-of-type`|Selects every `<p>` element that is the last `<p>` element of its parent|
|`:link`|`a:link`|Selects all unvisited links|
|`:not(selector)`|`:not(p)`|Selects every element that is not a `<p>` element|
|`:nth-child(n)`|`p:nth-child(2)`|Selects every `<p>` element that is the second child of its parent|
|`:nth-last-child(n)`|`p:nth-last-child(2)`|Selects every `<p>` element that is the second child of its parent, counting from the last child|
|`:nth-last-of-type(n)`|`p:nth-last-of-type(2)`|Selects every `<p>` element that is the second `<p>` element of its parent, counting from the last child|
|`:nth-of-type(n)`|`p:nth-of-type(2)`|Selects every `<p>` element that is the second `<p>` element of its parent|
|`:only-of-type`|`p:only-of-type`|Selects every `<p>` element that is the only `<p>` element of its parent|
|`:only-child`|`p:only-child`|Selects every `<p>` element that is the only child of its parent|
|`:optional`|`input:optional`|Selects input elements with no "required" attribute|
|`:out-of-range`|`input:out-of-range`|Selects input elements with a value outside a specified range|
|`:read-only`|`input:read-only`|Selects input elements with the "readonly" attribute specified|
|`:read-write`|`input:read-write`|Selects input elements with the "readonly" attribute NOT specified|
|`:required`|`input:required`|Selects input elements with the "required" attribute specified|
|`:root`|`:root`|Selects the document's root element|
|`::selection`|`::selection`|Selects the portion of an element that is selected by a user|
|`:target`|`#news:target`|Selects the current active #news element (clicked on a URL containing that anchor name)|
|`:valid`|`input:valid`|Selects all input elements with a valid value|
|`:visited`|`a:visited`|Selects all visited links|
