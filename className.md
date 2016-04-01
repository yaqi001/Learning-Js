# className

~~~ html
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>className属性</title>
<style>
    body{ font-size:16px;}
    .one{
		border:1px solid #eee;
		width:230px;
		height:50px;
		background:#ccc;
		color:red;
    }
	.two{
		border:1px solid #ccc;
		width:230px;
		height:50px;
		background:#9CF;
		color:blue;
	}
	</style>
</head>
<body>
    <p id="p1" class="two"> JavaScript使网页显示动态效果并实现与用户交互功能。</p>
    <input type="button" value="添加样式" onclick="add()"/>
    <p id="p2" class="one">JavaScript使网页显示动态效果并实现与用户交互功能。</p>
    <input type="button" value="更改外观" onclick="modify()"/>

	<script type="text/javascript">
      var p1 = document.getElementById("p1");
      document.write("<br/>" + p1.className + "------"); // 这里的 p1.className 没有随着 className 的改变而改变，原因是因为 body 里的 html 是可以随时被改变的而 script 里的不能随时改变？？？？？
	   function add(){
	      //var p1 = document.getElementById("p1");
	      p1.className = "one";
	   }
	   function modify(){
	      var p2 = document.getElementById("p2");
	      p2.className = "two";
	   }
	</script>
</body>
</html>
~~~
