# Math 对象

> **注意**：Math 对象是一个固有的对象，无需创建它，直接把 Math 作为对象使用就可以调用其所有属性和方法。这是它与Date,String对象的区别。

1. toSource() // 返回该对象的源代码。

2. valueOf() // 返回 Math 对象的原始值。

3. ceil() 方法可对一个数进行向上取整。
 
   ~~~ html
   <script type="text/javascript">
	  document.write(Math.ceil(0.8) + "<br />")
	  document.write(Math.ceil(6.3) + "<br />")
	  document.write(Math.ceil(5) + "<br />")
	  document.write(Math.ceil(3.5) + "<br />")
	  document.write(Math.ceil(-5.1) + "<br />")
	  document.write(Math.ceil(-5.9))
	</script>
   ~~~
   ~~~ bash
   // 运行结果
   1
	7
	5
	4
	-5
	-5
   ~~~

4. floor() 方法可对一个数进行向下取整。

5. round() 方法可把一个数字四舍五入为最接近的整数。
   > **重要**
   > 如果 x 与两侧整数同等接近，则结果接近 +∞方向的数字值 。(如 -5.5 将舍入为 -5; -5.52 将舍入为 -6
   > parseInt(x) 相当于让 x 这个值向原点靠近。负左正右。

   ~~~ html
   <script>
	  document.write(Math.round(-6.4)+ "<br>"); // -6
	  document.write(Math.round(-6.6)); // -7
	</script>
   ~~~

6. random() 方法可返回介于 0 ~ 1（大于或等于 0 但小于 1 )之间的一个随机数。返回一个大于或等于 0 但小于 1 的符号为正的数字值。
   ~~~ html
   // 获得0 ~ 10之间的随机数
   <script type="text/javascript">
	  document.write((Math.random())*10);
	</script>
   ~~~
