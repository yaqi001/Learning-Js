# 日期对象：日期对象可以储存任意一个日期，并且可以精确到毫秒数（1/1000 秒）。

> **注意**
> 在创建 Date 对象并赋值时有个需要注意的地方！！！！！
  ~~~ html
  <html>
  <script>
  var time = new Date(); // 当前时间
  document.write(time);
  var time1 = new Date(1991, 8, 2); // 返回下个月的今天
  document.write("<br>---" + time1); 
  var time2 = new Date('Sep 2, 1991'); // 正常返回 1991 年 9 月 2 日
  document.write("<br>" + time2);
  </script>
  </html>
  ~~~
  ~~~ bash
  // 返回结果
  Tue Mar 29 2016 19:20:44 GMT+0800 (CST)
  ---Mon Sep 02 1991 00:00:00 GMT+0900 (CDT)
  Mon Sep 02 1991 00:00:00 GMT+0900 (CDT)
  ~~~

* 日期对象的方法：
  ~~~ html
  <html>
	 <script>
		var time = new Date();
		document.write(time);
      //time.setDay 是星期 0 ~ 6 , 日 ～ 六
		time.setDate(2);
		time.setMonth(8);
		time.setFullYear("1991");
		time.setYear("2016");
		time.setHours("17");
		time.setMinutes("0");
		time.setSeconds("0");
		//time.setTime("1991,9,1");
		document.write("<br>" + time);
	 </script>
  </html>
  ~~~

  ~~~ html
  // 获取星期几
  <!DOCTYPE HTML>
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
  <title>获得星期</title>
  <script type="text/javascript">
	 var mydate=new Date();
	 var weekday=["星期日","星期一","星期二","星期三","星期四","星期五","星期六"];
	 document.write("今天是：" + weekday[mydate.getDay()]);
  </script>
  </head>
  <body>
  </body>
  </html>
  ~~~
  ~~~ bash
  // 运行结果
  今天是：星期二
  ~~~

  ~~~ html
  <!DOCTYPE html>
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
  <title>日期对象 </title>
  <script type="text/javascript">
	var mydate=new Date();
	 document.write("当前时间："+mydate+"<br>");
	 mydate.setTime(mydate.getTime() + 2 * 60 * 60 * 1000);
	 document.write("推迟二小时时间：" + mydate);
	 // get/setTime() 返回/设置时间，单位毫秒数，计算从 1970 年 1 月 1 日零时到日期对象所指的日期的毫秒数。
	 document.write(mydate.getTime());
  </script>
  </head>
  <body>
  </body>
  </html>
  ~~~
