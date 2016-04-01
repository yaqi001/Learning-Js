# navigator 对象：包含有关浏览器的信息，通常用于检测浏览器与操作系统的版本。

* 对象属性
  
| **属性** | **描述** |
| -------- | -------- |
| appCodeName | 浏览器代码名的字符串表示 |
| appName | 浏览器名称 |
| appVersion | 浏览器版本 |
| platform | 浏览器的操作系统平台 |
| userAgent | 返回由客户端向服务器端发送的 user agent 的头部 |
  
  ~~~ html
  <!DOCTYPE HTML>
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <title>无标题文档</title>
  </head>
  <script type="text/javascript">
	 document.write(window.navigator.appCodeName + "<br>");
	 document.write(window.navigator.appName + "<br>")
	 document.write(window.navigator.appVersion + "<br>");
	 document.write(window.navigator.platform + "<br>");
	 document.write(window.navigator.userAgent);
  </script>
  <body>
  </body>
  </html>
  ~~~

  ~~~ bash
  // 运行结果
  Mozilla
  Netscape
  5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.87 Safari/537.36
  Linux x86_64
  Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.87 Safari/537.36
  ~~~

