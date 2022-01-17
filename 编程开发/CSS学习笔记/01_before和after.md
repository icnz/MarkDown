> 定义

::before用来创建一个伪元素，作为已选中元素的第一个子元素。通常会配合content属性来为该元素添加修饰性的内容。此虚拟元素默认为行内元素。

::after用来创建一个伪元素，作为已选中元素的最后一个子元素。通常会配合content属性来为该元素添加装饰性的内容。此虚拟元素默认是行内元素。

CSS3 引入 ::before  是为了将伪类和伪元素区别开来。浏览器也接受由CSS 2 引入的 :before 写法。

我们可以用几乎任何方法定义 content 中的文字和图片样式。

注意：由::before 和::after 生成的伪元素包含在元素格式框内，因此不能应用在替换元素上， 比如：\<img\>或\<br\>元素。

> 语法

```javascript
element:after  { style properties }  /* CSS2 语法(过时语法，仅用来支持 IE8) */
element::after { style properties }  /* CSS3 语法 */

element:before  { style properties }  /* CSS2 语法(过时语法，仅用来支持 IE8) */
element::before { style properties }  /* CSS3 语法 */
```

> 示例

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>::before和::after</title>
</head>
<body>
<ul>
  <li>Buy milk</li>
  <li>Take the dog for a walk</li>
  <li>Exercise</li>
  <li>Write code</li>
  <li>Play music</li>
  <li>Relax</li>
</ul>
</body>
</html>
```

```css
li {
  list-style-type: none;
  position: relative;
  margin: 2px;
  padding: 0.5em 0.5em 0.5em 2em;
  background: lightgrey;
  font-family: sans-serif;
}

li.done {
  background: #CCFF99;
}

li.done::before {
  content: '';
  position: absolute;
  border-color: #009933;
  border-style: solid;
  border-width: 0 0.3em 0.25em 0;
  height: 1em;
  top: 1.3em;
  left: 0.6em;
  margin-top: -1em;
  transform: rotate(45deg);
  width: 0.5em;
}
```

```javascript
var list = document.querySelector('ul');
list.addEventListener('click', function(ev) {
  if( ev.target.tagName === 'LI') {
     ev.target.classList.toggle('done');
  }
}, false);
```

