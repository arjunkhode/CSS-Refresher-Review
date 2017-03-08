# CSS-Refresher-Review

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
Absolute position and fixed position removes the element from the normal flow. Each web-page has a default flow, which is like a set of rules. Like gravity affects a tower of building blocks, flow affects the building of HTML elements. Position relative makes an element like Clark Kent. It can defy the normal flow and move away from its original position, without disturbing the flow. Position relative does not push other elements. It just affects the z-index and causes overlap. Thus, it does not 'disturb the flow'.

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
</li>


