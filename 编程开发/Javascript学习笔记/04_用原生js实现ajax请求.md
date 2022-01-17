原生js发送ajax请求的就是“**XMLHttpRequest**”，因此必须要弄清楚XMLHttpRequest实现ajax的步骤，只有搞清楚了它的工作流程，我们才可以自己来封装。

 XMLHttpRequest实现ajax总共分为五步，每一个步骤单独来看，都非常的清晰明了，基本上跟http的表面请求响应流程差不多：

​        1、建立XMLHttpRequest对象；

​       2、设置回调函数；

​       3、使用open方法与服务器建立链接；

​       4、向服务器发送数据；

​       5、在回调函数中针对不同的响应状态进行处理；

接下来，试着来手动实现一个。

```javascript
<!doctype html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>用原生js实现ajax请求</title>
</head>
<body>
    <button id="test">test</button>
    <script type="text/javascript">
        var test = document.getElementById('test');
        test.onclick = function() {
            ajax({
                type: 'get',
                url: 'http://localhost:8080/readNum',
                dataType: 'json'
                success: function(data) {
                    console.log('success', data);
                },
                error: function(XMLHttpRequest, textStatus, errorThrown) {
                    console.log('error', errorThrown);
                }
            });
        }
        //data传入的参数也需要做兼容处理，对于中文还需要encode转码
        function params(data) {
            //if (typeof data === 'string') {
            //    return data;
            //}
            if (typeof data === 'object') {
                var arr = [];
                for (var key in data) {
                    arr.push(encodeURIComponent(key) + "=" + encodeURIComponent(data[key]));
                }
                return arr.join("&");
            }
            return data;
        }
        // ajax实现
        function ajax(options) {
            //非空处理
            options = options || {};

            //处理参数，给出默认值
            //请求方式
            options.type = options.type.toUpperCase() || 'GET';
            //是否异步
            options.async = options.async || true;
            //请求地址
            options.url = options.url || window.location.href;
            //请求参数
            options.data = options.data || '';
            //响应格式
            options.dataType = options.dataType || 'JSON';
            //超时时间
            options.timeout = options.timeout || 10000;
            //请求完成后的回调
            options.complete = options.complete || function(){};
            //请求成功后的回调
            options.success = options.success || function(){};
            //请求失败后的回调
            options.error = options.error || function(){};

            //初始化异步对象
            var xhr = new XMLHttpRequest();

            //参数处理
            var data = params(options.data);

            //需要判断get和post
            if (options.type === 'GET') {
                //打开请求，如果url已经有参数了，直接追加，没有从问号开始拼接
                if (options.url.indexOf('?') !== -1) {
                    xhr.open(options.type, options.url + '&' + data);
                } else {
                    xhr.open(options.type, options.url + '?' + data);
                }
                //发送请求，因为参数都跟在url后面，所以不用在send里面做任何处理
                xhr.send();
            }
            if (options.type === 'POST') {
                // 打开请求
                xhr.open(options.type, options.url);
                // 设置请求头，如果不写，就是浏览器默认，就是下面这个
                xhr.setRequestHeader('Content-type', 'application/x-www-form-urlencoded');
                // 发送请求，post请求的时候，会将data中的参数按照&拆分出来
                xhr.send(data);
            }
 
            //解析结果
            xhr.onreadystatechange = function() {
                // readyState五个状态 0:未发送请求，1:已发送请求，2:已经握手，3:正在处理请求，4:请求处理完成
                // 0：请求未初始化（还没有调用 open()）;
                // 1：请求已经建立，但是还没有发送（还没有调用 send()）;
                // 2：请求已发送，正在处理中（通常现在可以从响应中获取内容头）;
                // 3：请求在处理中，通常响应中已有部分数据可用了，但是服务器还没有完成响应的生成;
                // 4：响应已完成，您可以获取并使用服务器的响应了;

                //console.log('xhr', xhr);

                if (xhr.readyState === 4) {
                    options.complete();
                    if (xhr.status === 200) {
                        options.success(xhr.responseText);
                    } else {
                        options.error(xhr, xhr.status, xhr.statusText);
                    }
                }
            }
        }
    </script>
</body>
</html>
```

