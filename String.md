# 字符串
# 字符串对象

  在之前的学习中已经使用字符串对象了，定义字符串的方法就是直接赋值。比如：

1. 转换大小写方法
	~~~ html
	var mystr = "I love JavaScript!"
	var Mystr = mystr.toUpperCase(); // I LOVE JAVASCRIPT!
	~~~
  
2. charAt() 方法可返回指定位置的字符。返回的字符是长度为 1 的字符串。
   ~~~ html
   stringObject.charAt(index) 
   ~~~

3. indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。

   ~~~ html
   stringObject.indexOf(substring, startpos) // startpos 规定在字符串中开始检索的位置。
   ~~~

   ~~~ html
   <!DOCTYPE html>
	<html>
	<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
	<title>string对象 </title>
	<script type="text/javascript">
	  var mystr="Hello World!"
	  document.write(mystr.indexOf('o', 5) + "<br/>");
	  document.write(mystr.indexOf('o', 4)); // 从 4 开始，就包括索引为 4 的这个位置了。
	</script>
	</head>
	<body>
	</body>
	</html>
   ~~~

4. split() 方法将字符串分割为字符串数组，并返回此数组。

   ~~~ html
   stringObject.split(separator,limit) // limit 分割次数，可选参数。
   ~~~
   ~~~ html
   document.write(mystr.split("")+"<br>");
   document.write(mystr.split("", 5));
   ~~~
   ~~~ bash
   // 运行结果
	w,w,w,.,i,m,o,o,c,.,c,o,m
   w,w,w,.,i
   ~~~
   ~~~ html
   <!DOCTYPE HTML>
	<html>
	<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
	<title>无标题文档</title>
	<script type="text/javascript">
	var mystr="86-010-85468578";
	document.write(mystr.split('-') + "<br />");
	document.write(mystr.split('') + "<br />");
	document.write(mystr.split("", 3));
	</script>
	</head>
	<body>
	</body>
	</html>
   ~~~
   ~~~
   // 运行结果
   86,010,85468578
	8,6,-,0,1,0,-,8,5,4,6,8,5,7,8
	8,6,-
   ~~~

5. substring() 方法用于提取字符串中介于两个指定下标之间的字符。

   ~~~ html
   // 返回内容是从 startPos 开始到 stopPos - 1 的位置停止。length = stopPos - startPos，从这可知如果 stopPos = startPos，说明返回的是空串。
   // ！！！！！！！！ 如果 start 比 stop 大，那么该方法在提取子串之前会先交换这两个参数。 ！！！！！！！！
   stringObject.substring(starPos,stopPos) // starPos 起始位置是非负整数，必需。stopPos 结束位置是非负整数，可选。
   ~~~

6. substr() 方法从字符串中提取从 startPosi 位置开始的指定数目的字符串。

   ~~~ html
   stringObject.substr(startPos,length)
   ~~~
  
   > **注意**：如果参数 startPos 是负数，从字符串的尾部开始算起的位置。也就是说，-1 指字符串中最后一个字符，-2 指倒数第二个字符，以此类推。
   > 如果startPos为负数且绝对值大于字符串长度，startPos 为 0。

