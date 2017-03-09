# CSS-Refresher-Review
My review of [Vasanth's CSS refresher](https://github.com/vasanthk/css-refresher-notes) with examples.

1.Position

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
Absolute position and fixed position removes the element from the normal flow. Each web-page has a default flow, which is like a set of rules. Like gravity affects a tower of building blocks, flow affects the building of HTML elements. Position relative makes an element like Clark Kent. It can defy the normal flow and move away from its original position, without disturbing the flow. Position relative does not push other elements. It just affects the z-index and causes overlap. Thus, it does not 'disturb the flow'. Any offsets will not cause elements around the box to be repositioned. [Working example](https://github.com/arjunkhode/CSS-Refresher-Review/blob/master/position-relative.html).
</li>

```
<style>
.box{
	height:50px;
	width: 50px;
}
.one{
	background: lightcoral;
	position: relative;
	left: 25px;
}
.two{
	background: mistyrose;
}
</style>
<div class="box one">
</div>
<div class="box two">
</div>
```
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
</li>
<li>
[A good reference link not in Vasanth's refresher](http://blog.teamtreehouse.com/css-positioning)
</li>

2.Display
<li>Default value is inline</li>
<li>Some elements are block in nature while some are inline</li>
<li>An inline element can't use height or width even if they may have them. It can have margin-top, margin-bottom, padding-top and padding-bottom but these will not make any changes, the values are just there for the sake of it, but they can come in handy if another child element inherits display from the current element.</li>
<li>Inline-block can have height and width which get applied.</li>
<li>Block level elements begin on a new line, inline ones don't.
<li>One example of a block element is 'div'. One example of an inline element is the anchor tag 'a'.</li>
<li>Display none removes the element from the flow of the page, but the element still exists in the DOM. If you just want to make the element invisible but take up space, use visibility:hidden. Inversely, visibility:visible.</li>
<li>By default (without setting a width) block elements take up as much horizontal space as they can. They take as much height by default as their children require.</li>
<li>display:table can help add semantic value to the elements. Also this can help vertical alignment of children. To use it, you can just name corresponding display properties with the name of the kind of table element you are using</li>
```
<div style="display: table;">
  <div style="display: table-row;">
    <div style="display: table-cell;">
      Gross but sometimes useful.
    </div>
  </div>
</div>
```
[Reference: CSS Tricks](https://css-tricks.com/almanac/properties/d/display/)
<li>Block level elements ignore vertical-align property.</li>
<li>you can put any block element inside another block element. You can also put any inline element inside a block element, as well as any inline element inside any other inline element. But you cannot put a block element inside an inline element. [reference](https://www.impressivewebs.com/difference-block-inline-css/)</li>
<li>Think of a display:inline-block element that has been rendered (or converted to an image) and then placed in the document inline.</li>