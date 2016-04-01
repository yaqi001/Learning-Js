# history 对象：history对象记录了用户曾经浏览过的页面(URL)，并可以实现浏览器前进与后退相似导航的功能。

> **对象**
> 注意:从窗口被打开的那一刻开始记录，每个浏览器窗口、每个标签页乃至每个框架，都有自己的history对象与特定的 window 对象关联。

~~~ html
// 注意：window 可以省略。
window.history.[属性|方法]
~~~

* 对象属性：
1. length

* 对象方法：
1.	back();
2. go();
3. forward(); 

~~~ html
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>History对象</title>
</head>
<script type="text/javascript">
  document.write(window.history.length);
  //window.history.back(); //加载上一个 url
  //window.history.forward(); //加载下一个 url
  //window.history.go(2); // 加载后面第二个 url
  //window.history.go(-1); // 加载上一个 url
</script>
<body>
</body>
</html>
~~~


