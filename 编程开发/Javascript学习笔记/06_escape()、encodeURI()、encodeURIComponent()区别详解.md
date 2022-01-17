JavaScript中有三个可以对字符串编码的函数，分别是： escape,encodeURI,encodeURIComponent，相应3个解码函数：unescape,decodeURI,decodeURIComponent 。

### 1、escape()

> 定义和用法

escape() 函数可对字符串进行编码，这样就可以在所有的计算机上读取该字符串。

该方法不会对 ASCII 字母和数字进行编码，也不会对下面这些 ASCII 标点符号进行编码： * @ - _ + . / 。其他所有的字符都会被转义序列替换。

**提示：** 使用 unescape() 方法对字符串进行解码。

**注意：** escape()函数不能用于编码 URIs(通用资源标识符（UniformResourceIdentifier,简称"URI"））,需用encodeURI()。

> 语法

```javascript
escape(string)

string 必需。要被转义或编码的字符串。
```

> 实例

```javascript
document.write(escape("http://url.com/") + "<br />")
document.write(escape("?!=()#%&"))

输出：
http%3A//www.url.com
%3F%21%3D%28%29%23%25%26
```

### 2、encodeURI()

>定义和用法

encodeURI() 函数可把字符串作为 URI 进行编码。

对以下在 URI 中具有特殊含义的 ASCII 标点符号，encodeURI() 函数是不会进行转义的： , / ? : @ & = + $ # ，可以使用 encodeURIComponent() 方法分别对特殊含义的 ASCII 标点符号进行编码。

**提示：**使用 decodeURI() 方法可以解码URI（通用资源标识符:UniformResourceIdentifier,简称"URI")。

>语法

```javascript
encodeURI(uri)

uri 必需。一个字符串，含有 URI 或其他要编码的文本。
```

>实例

```javascript
document.write(encodeURI("my url.html?name=ståle&car=saab")+ "<br>");

输出：
my%20url.html?name=st%C3%A5le&car=saab
```

### 3、encodeURIComponent()

> 定义和用法

encodeURIComponent() 函数可把字符串作为 URI 组件进行编码。

该方法不会对 ASCII 字母和数字进行编码，也不会对这些 ASCII 标点符号进行编码： - _ . ! ~ * ' ( ) 。

其他字符（比如 ：;/?:@&=+$,# 这些用于分隔 URI 组件的标点符号），都是由一个或多个十六进制的转义序列替换的。

**提示：**使用 decodeURIComponent() 方法可以对 URI 进行解码。

> 语法

```javascript
encodeURIComponent(uri)

uri 必需。一个字符串，含有 URI 组件或其他要编码的文本。
```

> 实例

```javascript
document.write(encodeURIComponent("http://url.com/my test.php?name=ståle&car=saab"));

输出：
http%3A%2F%2Furl.com%2Fmy%20test.php%3Fname%3Dst%C3%A5le%26car%3Dsaab
```

