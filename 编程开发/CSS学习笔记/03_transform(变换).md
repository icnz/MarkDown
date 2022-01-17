### transform

> 定义

**设置或检索对象的转换。**
默认值为：none。适用于所有块级元素及某些内联元素。
对应的脚本特性为**transform**。

> 语法

```css
transform：none | matrix(<number>,<number>,<number>,<number>,<number>,<number>)? translate(<length>[,<length>])? translateX(<length>)? translateY(<length>)? rotate(<angle>)? scale(<number>[,<number>])? scaleX(<number>)? scaleY(<number>)? skew(<angle>[,<angle>])? skewX(<angle>) || skewY(<angle>)?

none：无转换
matrix(<number>,<number>,<number>,<number>,<number>,<number>)：以一个含六值的(a,b,c,d,e,f)变换矩阵的形式指定一个2D变换，相当于直接应用一个[a,b,c,d,e,f]变换矩阵
translate(<length>[, <length>])：指定对象的2D translation（2D平移）。第一个参数对应X轴，第二个参数对应Y轴。如果第二个参数未提供，则默认值为0
translateX(<length>)：指定对象X轴（水平方向）的平移
translateY(<length>)：指定对象Y轴（垂直方向）的平移
rotate(<angle>)：指定对象的2D rotation（2D旋转），需先有transform-origin属性的定义
scale(<number>[, <number>])：指定对象的2D scale（2D缩放）。第一个参数对应X轴，第二个参数对应Y轴。如果第二个参数未提供，则默认取第一个参数的值
scaleX(<number>)：指定对象X轴的（水平方向）缩放
scaleY(<number>)：指定对象Y轴的（垂直方向）缩放
skew(<angle> [, <angle>])：指定对象skew transformation（斜切扭曲）。第一个参数对应X轴，第二个参数对应Y轴。如果第二个参数未提供，则默认值为0
skewX(<angle>)：指定对象X轴的（水平方向）扭曲
skewY(<angle>)：指定对象Y轴的（垂直方向）扭曲
```

> 示例

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>transform变换</title>
</head>
<body>
<ul>
	<li class="translate">
		<p>transform:translate(5%,10px)</p>
	</li>
	<li class="translate2">
		<p>transform:translate(-10px,-10px)</p>
	</li>
	<li class="translateX">
		<p>transform:translateX(20px)</p>
	</li>
	<li class="translate3">
		<p>transform:translate(20px)</p>
	</li>
	<li class="translateY">
		<p>transform:translateY(10px)</p>
	</li>
	<li class="translate4">
		<p>transform:translate(0,10px)</p>
	</li>
</ul>
<h1>旋转：rotate()</h1>
<ul class="test">
	<li class="rotate">
		<p>transform:rotate(-15deg)</p>
	</li>
	<li class="rotate2">
		<p>transform:rotate(15deg)</p>
	</li>
</ul>
<h1>缩放：scale()</h1>
<ul class="test">
	<li class="scale">
		<p>transform:scale(.8)</p>
	</li>
	<li class="scale2">
		<p>transform:scale(1.2)</p>
	</li>
</ul>
<h1>扭曲：skew()</h1>
<ul class="test">
	<li class="skew">
		<p>transform:skew(-5deg)</p>
	</li>
	<li class="skew2">
		<p>transform:skew(-5deg,-5deg)</p>
	</li>
</ul>
</body>
</html>
```

```css
ul {
	zoom:1;
	width:700px;
	margin:0;
	padding:0;
	list-style:none;
}
li {
	float:left;
	margin:20px 30px 0 0;
	border:1px solid #000;
}
li p {
	width:300px;
	height:100px;
	margin:0;
	background:#ddd;
}
.matrix {
	-moz-transform:matrix(0,1,1,1,10px,10px);
	-webkit-transform:matrix(0,1,1,1,10,10);
	-o-transform:matrix(0,1,1,1,10,10);
	-ms-transform:matrix(0,1,1,1,10,10);
	transform:matrix(0,1,1,1,10,10);
}
.translate p {
	-moz-transform:translate(5%,10px);
	-webkit-transform:translate(10px,10px);
	-o-transform:translate(10px,10px);
	-ms-transform:translate(10px,10px);
	transform:translate(10px,10px);
}
.translate2 p {
	-moz-transform:translate(-10px,-10px);
	-webkit-transform:translate(-10px,-10px);
	-o-transform:translate(-10px,-10px);
	-ms-transform:translate(-10px,-10px);
	transform:translate(-10px,-10px);
}
.translateX p {
	-moz-transform:translateX(20px);
	-webkit-transform:translateX(20px);
	-o-transform:translateX(20px);
	-ms-transform:translateX(20px);
	transform:translateX(20px);
}
.translate3 p {
	-moz-transform:translate(20px);
	-webkit-transform:translate(20px);
	-o-transform:translate(20px);
	-ms-transform:translate(20px);
	transform:translate(20px);
}
.translateY p {
	-moz-transform:translateY(10px);
	-webkit-transform:translateY(10px);
	-o-transform:translateY(10px);
	-ms-transform:translateY(10px);
	transform:translateY(10px);
}
.translate4 p {
	-moz-transform:translate(0,10px);
	-webkit-transform:translate(0,10px);
	-o-transform:translate(0,10px);
	-ms-transform:translate(0,10px);
	transform:translate(0,10px);
}
.rotate {
	-moz-transform:rotate(-5deg);
	-webkit-transform:rotate(-5deg);
	-o-transform:rotate(-5deg);
	-ms-transform:rotate(-5deg);
	transform:rotate(-5deg);
}
.rotate2 {
	-moz-transform:rotate(5deg);
	-webkit-transform:rotate(5deg);
	-o-transform:rotate(5deg);
	-ms-transform:rotate(5deg);
	transform:rotate(5deg);
}
.scale {
	-moz-transform:scale(.8);
	-webkit-transform:scale(.8);
	-o-transform:scale(.8);
	-ms-transform:scale(.8);
	transform:scale(.8);
}
.scale2 {
	-moz-transform:scale(1.2);
	-webkit-transform:scale(1.2);
	-o-transform:scale(1.2);
	-ms-transform:scale(1.2);
	transform:scale(1.2);
}
.skew {
	-moz-transform:skew(-5deg);
	-webkit-transform:skew(-5deg);
	-o-transform:skew(-5deg);
	-ms-transform:skew(-5deg);
	transform:skew(-5deg);
}
.skew2 {
	-moz-transform:skew(-5deg,-5deg);
	-webkit-transform:skew(-5deg,-5deg);
	-o-transform:skew(-5deg,-5deg);
	-ms-transform:skew(-5deg,-5deg);
	transform:skew(-5deg,-5deg);
}
```

