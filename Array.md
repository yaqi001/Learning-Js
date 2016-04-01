# Js —— 数组(万物皆对象)

var myarr = new Array();
或
var myarr = new Array(9);
或
var myarr = [];

注意：
1.创建的新数组是空数组，没有值，如输出，则显示undefined。
2.虽然创建数组时，指定了长度，但实际上数组都是变长的，也就是说即使指定了长度为8，仍然可以将元素存储在规定长度以外。

* 数组对象是一个对象的集合，里边的对象可以是不同类型的。不像 Java 中的数组，因为 Java 声明数组的时候需要定义类型的哦！！！！！

1. 定义了一个空数组:
   ~~~ html
   var arr = new Array();
   ~~~

2. 定义时指定有 n 个空元素的数组：
   ~~~ html
   var arr1 = new Array(5);
   ~~~

3. 定义数组的时候，直接初始化数据：
   ~~~ html
   var arr2 = [1, 2, "3, 4, 5"];
   ~~~

![array](images/js_array.jpg)

4. concat() 方法：用于连接两个或多个数组。此方法返回一个新数组，不改变原来的数组。
   ~~~ html
   // 语法
   arrayObject.concat(array1,array2,...,arrayN)
   ~~~~
   
   > **重要**
   > 注意:  该方法不会改变现有的数组，而仅仅会返回被连接数组的一个副本。
   
   ~~~ html
   <script type="text/javascript">
	  var mya1= new Array("hello!")
	  var mya2= new Array("I","love");
	  var mya3= new Array("JavaScript","!");
	  var mya4=mya1.concat(mya2,mya3);
	  document.write(mya4);
	</script>
   ~~~
   ~~~ bash
   // 运行结果
   hello!,I,love,JavaScript,!
   ~~~

5. join()方法用于把数组中的所有元素放入一个字符串。元素是通过指定的分隔符进行分隔的。

   ~~~ html
   // 语法：
	arrayObject.join(分隔符) // separater 是可选参数，如果不指定的话就默认是逗号。
   // 返回一个新的字符串，并不影响 arrayObject 本身。
   ~~~
   ~~~ html
   <!DOCTYPE html>
	<html>
	<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
	<title>Array对象 </title>
	<script type="text/javascript">
		 var myarr1= new Array("86","010")
		 var myarr2= new Array("84697581");
		 var myarr3= myarr1.concat(myarr2);
		 document.write(myarr3.join("-"));
	</script>
	</head>
	<body>
	</body>
	</html>
   ~~~
   ~~~ bash
   // 返回结果
   86-010-84697581
   ~~~

6. reverse() 方法用于颠倒数组中元素的顺序。
   
   > **重要**：该方法会改变原来的数组，而不会创建新的数组。

   ~~~ html
   // 语法：
   arrayObject.reverse()
   ~~~
   ~~~ html
   <!DOCTYPE html>
	<html>
	<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
	<title>Array对象 </title>
	<script type="text/javascript">
		var myarr1= ["我","爱","你"];
      document.write(myarr1.reverse() + "<br>"); // 你,爱,我
      document.write(myarr1); // 你,爱,我
	</script>
	</head>
	<body>
	</body>
	</html>
   ~~~

7. slice() 方法可从已有的数组中返回选定的元素。

   ~~~ html
   // start：必需，如果是负数就从数组的尾部开始开始算起，-1 指最后一个位置。
   // end：可选，数组片段结束处的数组下标，不包含该元素。如果是负数，就从数组尾部开始算起。
   arrayObject.slice(start,end) // 返回一个新数组
   ~~~

8. sort()方法使数组中的元素按照一定的顺序排列。

   ~~~ html
   // 语法:
   arrayObject.sort(方法函数) // 方法函数：可选，用于规定排序顺序，必须是函数，默认情况下按unicode码顺序排列。
   ~~~
   ~~~ html
   // 实现升序排序
   <script type="text/javascript">
		function sortNum(a,b) {
			return a - b;
			//升序，如降序，把“a - b”该成“b - a”
		}
		var myarr = new Array("80","16","50","6","100","1");
		document.write(myarr + "<br>"); // 80,16,50,6,100,1
		document.write(myarr.sort(sortNum)); // 1,6,16,50,80,100
	</script>
   ~~~
   ~~~ html
   // 实现降序排序
   <script type="text/javascript">
		function sortNum(a,b) {
			return b - a;
		}
		var myarr = new Array("80","16","50","6","100","1");
		var myNewArr = myarr.sort(sortNum);
		document.write(myNewArr);
   </script>
   ~~~

* **结论**：
* concat(), join(), slice(), sort() 不会影响原来的数组，而是创建了一个新的数组。
* reverse() 会改变原来的数组。
* 注意在 Js 中，"80" + "1" = "81"

~~~ html
// 计算班级总分
<!DOCTYPE  HTML>
<html >
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>系好安全带,准备启航</title>

<script type="text/javascript">

  //通过javascript的日期对象来得到当前的日期，并输出。
  
  var time = new Date();
  var year = time.getFullYear();
  var month = time.getMonth() + 1;
  var date = time.getDate();
  var day = time.getDay();
  var week = ["星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六"];
  
  //成绩是一长窜的字符串不好处理，找规律后分割放到数组里更好操作哦
  var scoreStr = "小明:87;小花:81;小红:97;小天:76;小张:74;小小:94;小西:90;小伍:76;小迪:64;小曼:76";
  var scoreStrToArr = scoreStr.split(';');
  var sum = 0;
  for (var i = 0; i < scoreStrToArr.length; i ++){
      var scoreArray = scoreStrToArr[i].split(":");
      var score = parseInt(scoreArray[1]);
      sum += score;
  }

  document.write(year + "年" + month + "月" + date + "日" + week[day] + "班级总分：" + sum);

</script>
</head>
<body>
</body>
</html>
~~~
