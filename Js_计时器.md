# Js —— 计时器

* 计时器类型：
一次性计时器：仅在指定的延迟时间之后触发一次。
间隔性触发计时器：每隔一定的时间间隔就触发一次。

* 计时器方法：

| **方法** | **说明** |
| -------- | -------- |
| setTimeout() | 在指定的延迟时间之后来执行代码 |
| clearTimeout() | 取消 setTimeout() 设置 |
| setInterval() | 每隔指定的延迟时间后就执行一次代码 |
| clearInterval() | 取消 setInterval() 设置 |

* setInterval()：在执行时,从载入页面后每隔指定的时间执行代码。
  ~~~ html
  // 代码：要调用的函数或要执行的代码串。
  // 周期性执行或调用表达式之间的时间间隔，以毫秒计（1s=1000ms）
  setInterval(代码,交互时间);
  ~~~

  调用函数格式(假设有一个clock()函数):
  ~~~ html
  setInterval("clock()",1000)
  ~~~
  或
  ~~~ html
  setInterval(clock,1000)  
  ~~~
 
  ~~~ html
  // 示例
  <!DOCTYPE HTML>
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <title>定时器</title>
  <script type="text/javascript">
	 var attime;
	 function clock(){
		var time=new Date();          
		attime=time.getHours() + ":" + time.getMinutes() + ":" + time.getSeconds();
		document.getElementById("clock").value = attime;
	 }
	 var int = setInterval(clock, 60000); // 打开网页，一分钟后会第一次执行 setInterval()。
	 document.write(int);
  </script>
  </head>
  <body>
  <form>
  <input type="text" id="clock" size="50" />
  </form>
  </body>
  </html>
  ~~~

* clearInterval() 方法可取消由 setInterval() 设置的交互时间。

  ~~~ html
  // id_of_setInterval：由 setInterval() 返回的 ID 值。
  clearInterval(id_of_setInterval)
  ~~~
  ~~~ html
  <!DOCTYPE HTML>
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <title>计时器</title>
  <script type="text/javascript">
	  function clock(){
		  var time=new Date();						  
		  document.getElementById("clock").value = time;
	  }
  //   var ID = window.setInterval(clock,3000);
	  var ID = window.setInterval("clock()", 5000);

  </script>
  </head>
  <body>
	 <form>
		<input type="text" id="clock" size="50" />
		<input type="button" value="Stop" onclick="clearInterval(ID)" />
	 </form>
  </body>
  </html>
  ~~~

* setTimeout()计时器，在载入后延迟指定时间后,去执行一次表达式,仅执行一次。
  ~~~ html
  <!DOCTYPE HTML>
  <html>
  <head>
  <script type="text/javascript">
  var num=0;
  function numCount(){
	document.getElementById('txt').value=num;
	num=num+1;
	setTimeout("numCount()",5000);
	}
  </script>
  </head>
  <body>
  <form>
  <input type="text" id="txt" />
  <input type="button" value="Start" onClick="numCount()" />
  </form>
  </body>
  </html>
  ~~~

* 取消计时器clearTimeout()
  ~~~ html
  // 语法
  clearTimeout(id_of_setTimeout)
  ~~~

  ~~~ html
  <!DOCTYPE HTML>
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <title>计时器</title>
  </head>
  <script type="text/javascript">
	 var num=0;
	 var i;
	 function startCount(){
		document.getElementById('count').value=num;
		num=num+1;
		i=setTimeout("startCount()",2000);
	 }
	 function stopCount(){
		clearTimeout(i);
	 }
  </script>
  </head>
  <body>
	 <form>
		<input type="text" id="count" />
		<input type="button" value="Start" onclick = "startCount()"/>
		<input type="button" value="Stop"  onclick = "stopCount()" />
	 </form>
  </body>
  </html>
  ~~~

----------------------

~~~ html
// 自动倒计时
<!DOCTYPE html>
<html>
   <head>
      <title>浏览器对象</title>  
      <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>   
   </head>
   <body>
      <!--先编写好网页布局-->
      <h2>操作成功</h2>
      <br>
      <font id="sec">5</font>
      // 注意：下面一定要写 javascript:，表示使用 js 脚本实现链接跳转。
      <font>秒后回到<a href="javascript:window.history.back();">主页</a></font>

      <script type="text/javascript">  
         var Font = document.getElementById("sec");
         var num = parseInt(Font.innerHTML);
         // 这里为什么将函数的定义放到另一个函数中呢？
         // 因为被定义的函数是需要使用这里的变量 num，而 setInterval() 函数不能将这个值传给他，如果 js 中有静态变量会很好解决。
         var i = setInterval(
            function min(){
               if (num > 0){
                   Font.innerHTML = num --;
               }
               else{
                   window.location.href = "http://www.imooc.com";
               }
            }, 1000);
      </script>
   </body>
</html>
~~~

