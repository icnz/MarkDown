### transform-origin

> 定义

**设置或检索对象以某个原点(或位置)进行转换。**
默认值为：50% 50% 0。适用于所有块级元素及某些内联元素。
该属性提供3个参数值。如果提供三个，第一个用于X轴(横坐标)，第二个用于Y轴(纵坐标)，第三个用于Z轴。如果提供两个，第一个用于横坐标，第二个用于纵坐标。如果只提供一个，该值将用于横坐标。
该属性必须与 transform 属性一同使用。
对应的脚本特性为**transformOrigin**。

> 语法

```css
transform-origin：[ <length-percentage> | left | center | right | top | bottom ] | [ [ <length-percentage> | left | center | right ] && [ <length-percentage> | top | center | bottom ] ] <length>?

一个值(X轴)：
  必须是<length>，<percentage>，或 left, center, right, top, bottom关键字中的一个。
两个值(X轴和Y轴)：
  其中一个必须是<length>，<percentage>，或left, center, right关键字中的一个。
  另一个必须是<length>，<percentage>，或top, center, bottom关键字中的一个。
  注：两个值时，X轴和Y轴的值中如果一个是left或right或center，另一个必须top或bottom或center。
两个值(X轴、Y轴和Z轴)：
  前两个值与只有两个值时的用法相同。
  第三个值必须是<length>。它始终代表Z轴偏移量。
```

> 示例

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>transform-origin原点变换</title>
</head>
<body>
  <ul>
	<li></li>
  </ul>
</body>
</html>
```

```css
ul {
	margin:0;
	padding:0;
	list-style:none;
	border:1px solid #000;
}
ul li {
	width:50px;
	height:50px;
	border:1px solid #000;
	background:#ddd;
	-moz-transform-origin:0 0;
	-moz-transform:rotate(45deg);
	-webkit-transform-origin:0 0;
	-webkit-transform:rotate(45deg);
	-o-transform-origin:0 0;
	-o-transform:rotate(45deg);
	-ms-transform-origin:0 0;
	-ms-transform:rotate(45deg);
	transform-origin:0 0;
	transform:rotate(45deg);
}
```



