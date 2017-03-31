# CSS-Refresher-Review
My review of [Vasanth's CSS refresher](https://github.com/vasanthk/css-refresher-notes) with examples.
# Table of Contents
1. [Position](#1)
1. [Display](#2)
1. [Selectors](#3)
1. [Repaint and Reflow](#4)
1. [Responsive Images](#5)
1. [Misc.](#6)

# <a name="1">1.Position</a>

<ul>
<li>
Z-index does not work on position:static.
</li>
<li>
Z-index works on position:relative, position:absolute and position:fixed and all those elements get a default z-index greater than static elements. So they are positioned on top of static elements if there ever is an overlap.
</li>
<li>
Relative position creates a coordinate system for its child elements.
</li>
<li>
Absolute position and fixed position removes the element from the normal flow. Each web-page has a default flow, which is like a set of rules. Like gravity affects a tower of building blocks, flow affects the building of HTML elements. Position relative makes an element like Clark Kent. It can defy the normal flow and move away from its original position, without disturbing the flow. Position relative does not push other elements. It just affects the z-index and causes overlap. Thus, it does not 'disturb the flow'. Any offsets will not cause elements around the box to be repositioned. <a href="https://github.com/arjunkhode/CSS-Refresher-Review/blob/master/position-relative.html">Working example</a>
</li>
<li>
Absolute position elements move within the coordinate system of their parent. If the parent does not have a coordinate system, the default coordinate system of the window is applied.
</li>
<li>
Since position relative creates a coordinate system, its children can be position relative themselves thereby creating a second coordinate system, or children with position absolute can move within the boundaries of the parent's coordinate system. The second case is more commonly used.
</li>
<li>
The most important point to keep in mind while using position absolute is that it removes the element from the flow of the page.
It doesn't affect other elements and the other elements don't affect it. It can also be used to stretch within the parent's scope.
</li>
<li>
Position fixed also removes the element from the flow. Like position absolute, position fixed can be used to stretch the element within the page. How fixed differs from absolute is that in position fixed, the parent is always the viewport and the coordinate system laid out is on top of the viewport. The top left corner of a position fixed element with top:0 and left:0, is the top left corner of the browser window

<a href="http://blog.teamtreehouse.com/css-positioning">A good reference link not in Vasanth's refresher</a>
</li>
</ul>

#<a name="2"> 2.Display</a>
<ul>
<li>Default value is inline</li>
<li>Some elements are block in nature while some are inline</li>
<li>An inline element can't use height or width even if they may have them. It can have margin-top, margin-bottom, padding-top and padding-bottom but these will not make any changes, the values are just there for the sake of it, but they can come in handy if another child element inherits display from the current element.</li>
<li>Inline-block can have height and width which get applied.</li>
<li>Block level elements begin on a new line, inline ones don't.
<li>One example of a block element is 'div'. One example of an inline element is the anchor tag 'a'.</li>
<li>Display none removes the element from the flow of the page, but the element still exists in the DOM. If you just want to make the element invisible but take up space, use visibility:hidden. Inversely, visibility:visible.</li>
<li>By default (without setting a width) block elements take up as much horizontal space as they can. They take as much height by default as their children require.</li>
<li>display:table can help add semantic value to the elements. Also this can help vertical alignment of children. To use it, you can just name corresponding display properties with the name of the kind of table element you are using, like table-row, table-cell, etc.</li><a href="https://css-tricks.com/almanac/properties/d/display/">Reference</a>
<li>Block level elements ignore vertical-align property.</li>
<li>you can put any block element inside another block element. You can also put any inline element inside a block element, as well as any inline element inside any other inline element. But you cannot put a block element inside an inline element. <a href="https://www.impressivewebs.com/difference-block-inline-css/">Reference</a></li>
<li>Think of a display:inline-block element that has been rendered (or converted to an image) and then placed in the document inline.</li>
<li><a href="http://thesagittariusme.blogspot.com/search/label/flexbox">Flexbox Notes</a></li>
<li><a href="https://github.com/arjunkhode/Project-flexbox">Flexbox Examples</a></li>
</ul>

# <a name="3">3.Selectors</a>
Play the game [flukeout](https://flukeout.github.io) to get the most out of CSS selectors.
Here is the summary of the game

* **The difference between dot between elements and space between elements in selectors**

article.container{...} means this is an article that has a classname to it called container. 
* .container div{...} means that all the divs inside class container will be selected. The subtle nuance between this and the previous example is that a space means think of "the preceding element has the succeeding element as its child" while the dot means think of "the succeeding element embodies the preceeding element". Also, the first example necessarily applies to child classes, classes that are inside the preceding element. The second example can have elements that are children of elements and need not be classes.
* `A  B`
Selects all B inside of A. B is called a descendant because it is inside of another element.
* `#id  A`
You can combine any selector with the descendent selector.
* `A.className`
You can combine the class selector with other selectors, like the type selector.
* `A, B`
Selects all As and Bs
* `A  *`
This selects all elements inside of A.
* `A + B`
Selects only one B which is the immediate sibling of A.
* `A ~ B`
Selects all Bs that are siblings of A
* `A > B `
Selects one B that is the immediate child of A
* `div p:first-child` 
Selects all first child p elements that are in a div.
* `ul li:only-child `
Selects the only li element that are in a ul.
* `ul li:last-child `
Selects the last li elements inside of any ul
* `div p:nth-child(2) `
Selects the second p in every div
* `:nth-last-child(2)` 
Selects all second-to-last child elements.
* `span:first-of-type` 
Selects the first span in any element.
* `.example:nth-of-type(odd) `
Selects all odd instances of a the example class. 
* `span:nth-of-type(6n+2) `
Selects every 6th instance of a span, starting from (and including) the second instance.
* `p span:only-of-type `
Selects a span within any p if it is the only span in there.
* `p span:last-of-type` 
Selects the last span in every p
* `div:empty` 
Selects all empty div elements.
* `:not(#fancy)` 
Selects all elements that do not have id="fancy".
* `div:not(:first-child)` 
Selects every div that is not a first child.
* `a[href] `
Selects all a elements that have a href="anything" attribute
* `a[href]` 
Selects all a elements that have a href="anything" attribute.
* `.toy[category^="Swim"]`
Selects toy classes with categories that begins with Swim
* `.toy[category$="Swim"]`
Selects toy classes with categories that ends with Swim
* `.toy[category*="Swim"]`
Selects toy classes with categories that contain Swim

#Selector efficiency

```
div.nav > ul li a[title]

```
A browser seeing the above selector will first try to match a[title] in the html, and then proceed to the left matching li, ul, and finally div.nav.

This last part of the selector (in this case a[title]) is called the “key selector” and it’s ultimately what will determine how efficient your selector will be.

The sooner browsers can filter out a mismatch, the less they have to check and, the more efficient the selector.

Below is the order of efficiency for selectors. IDs are the most efficient and pseudo classes and pseudo elements are the least efficient.

* id (#myid)
* class (.myclass)
* tag (div, h1, p)
* adjacent sibling (h1 + p)
* child (ul > li)
* descendent (li a)
* universal (*)
* attribute (a[rel=”external”])
* pseudo-class and pseudo element (a:hover, li:first)

[Source: vanseodesign](http://vanseodesign.com/css/css-selector-performance/)

# <a name="4">4.Repaint and Reflow</a>
* Repaint is expensive in terms of performance, as it requires the engine to search through all elements to determine what is visible, and what should be displayed.
* This is even more expensive than repaint. It happens when an element is appended to the DOM, or browser window is resized. The browser has to compute the entire flow of elements again.

* What causes a reflow

	* Resizing a window.
	* Changing the font.
	* Adding or removing a stylesheet.
	* Content changes, such as a user typing text in an input box.
	* Activation of CSS pseudo classes such as :hover (In IE the activation of the pseudo class of a sibling).
	* Manipulating the class attribute.
	* A script manipulating the DOM
	* Calculating offsetWidth and offsetHeight
	* Setting a property of the style attribute.

# <a name="5">5.Responsive Images</a>

* Images will be responsive and scale up and down if the width property is set to 100%. A better option would be to set `max-width` property to 100% since the image will scale down if it has to, but never scale up to be larger than its original size.

* Background images can also respond to resizing and scaling.

* If the background-size property is set to "contain", the background image will scale, and try to fit the content area. However, the image will keep its aspect ratio
* If the background-size property is set to "100% 100%", the background image will stretch to cover the entire content area.
* If the background-size property is set to "cover", the background image will scale to cover the entire content area. The "cover" value keeps the aspect ratio, and some part of the background image may be clipped

# <a name="6">6.Misc.</a>

* If supplied, an optional third value for `box-shadow` defines the blur distance of the shadow. Only positive values are allowed, and the larger the value, the more the shadow’s edge is blurred.
* To give a background to text, use `background: url(something); -webkit-background-clip:text; -webkit-text-fill-color:transparent;`. Note that the background clip statement should come after the background has been defined.
* Setting the viewport: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
* For devices smaller than 400px: `@media only screen and (min-device-width: 400px) {...}`

# Animation

```
@keyframes rotating{
	from{
	transform: rotate(0deg);
	}
	to{
	transform: rotate(360deg);
	}
}

.element{
animation: rotating 2s linear infinite;
}
```
