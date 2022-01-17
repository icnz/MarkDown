格式化字符串（Format String）是在编程过程中，允许编码人员通过特殊的占位符，将相关对应的信息整合或提取的规则字符串。

格式化字符串包括格式化输入和格式化输出。

### 方案一（推荐）

```javascript
String.prototype.format = function(args) {
    var result = this;
    if (arguments.length > 0) {    
        if (arguments.length == 1 && typeof (args) == "object") {
            for (var key in args) {
                if(args[key]!=undefined){
                    var reg = new RegExp("({" + key + "})", "g");
                    result = result.replace(reg, args[key]);
                }
            }
        }
        else {
            for (var i = 0; i < arguments.length; i++) {
                if (arguments[i] != undefined) {
                    var reg = new RegExp("({[" + i + "]})", "g");
                    result = result.replace(reg, arguments[i]);
                }
            }
        }
    }
    return result;
}

// 两种调用方式
var template1="我是{0}，今年{1}了";
var template2="我是{name}，今年{age}了";
var result1=template1.format("loogn",22);
var result2=template2.format({name:"loogn",age:22});
// 两个结果都是"我是loogn，今年22了"
```

### 方案二

```javascript
function stringFormat() {
    if (arguments.length == 0){
        return null;
    }
    var str = arguments[0];
    for (var i = 1; i < arguments.length; i++) {
        var re = new RegExp('\\{' + (i - 1) + '\\}', 'gm');
        str = str.replace(re, arguments[i]);
    }
    return str;
}

// 方法调用
StringFormat("&Type={0}&Ro={1}&lPlan={2}&Plan={3}&={4}&Id={5}&Id={6}", data1, data2, data3,data4, data5,data6,data7);
```

### 方案三

```javascript
String.format = function(str) {
    var args = arguments, re = new RegExp(”%([1-" + args.length + "])”, “g”);
    return String(str).replace(
        re,
        function($1, $2) {
            return args[$2];
        }
    );
};

// 方法调用
String.format('<a href="%1" onclick="alert(\'%2\');">%3</a>', url, msg, text);
```

### 其他思路（JQuery实现）

```
https://code.google.com/archive/p/jquery-utils/wikis/StringFormat.wiki
```

