# innerHTML 属性

<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>innerHTML</title>
</head>
<body>
<h2 id="con">javascript</H2>
<script type="text/javascript">
  var mychar = document.getElementById("con");
  document.write("原标题:"+mychar.innerHTML+"<br>"); //输出原h2标签内容
  mychar.innerHTML = "I love" + mychar.innerHTML;
  document.write("修改后的标题:"+mychar.innerHTML); //输出修改后h2标签内容
</script>
</body>
</html>

// 运行结果：
I love javascript  // 注意这里已经变成了最终的摸样！！！！！！说明 html 和 js 是并行运行的？

原标题:javascript
修改后的标题:I love javascript

