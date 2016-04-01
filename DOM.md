# DOM(Document Object Model)：定义了访问和处理 HTML 文档的标准方法。

  DOM 将 HTML 文档呈现为带有元素属性和文本的树结构（节点树）。

* DOM 节点：
  1. 元素节点
  2. 属性节点
  3. 文本节点

* getElementByName()：返回带有指定名称的节点对象的集合。

  ~~~ html
  // 与getElementById() 方法不同的是，id 返回的是单数的 element，name 返回的是复数的 elements 通过元素的 name 属性查询元素，而不是通过 id 属性。
  // 1. 因为文档中的 name 属性可能不唯一，所以 getElementsByName() 方法返回的是元素的数组，而不是一个元素。
  // 2. 和数组类似也有 length 属性，可以和访问数组一样的方法来访问，从 0 开始。
  document.getElementsByName(name)
  ~~~

* getElementsByTagName()：返回带有指定标签名的节点对象的集合。返回元素的顺序是它们在文档中的顺序。
  
  ~~~ html
  getElementsByTagName(Tagname)
  ~~~

  
* getAttribute()：通过元素节点的属性名称获取属性的值。

  ~~~ html
  // name 是字符串类型
  elementNode.getAttribute(name) 
  ~~~

  ~~~ html
  <!DOCTYPE HTML>
  <html> 
     <head>
	  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
	  <title>getAttribute()</title>
	  </head>
	  <body>   
	  <p id="intro">课程列表</p>  
	     <ul>  
		     <li title="第1个li">HTML</li>  
			  <li>CSS</li>  
			  <li title="第3个li">JavaScript</li>  
			  <li title="第4个li">Jquery</li>  
			  <li>Html5</li>  
		  </ul>  
	  <p>以下为获取的不为空的li标签title值:</p>
	  <script type="text/javascript">
	     var con=document.getElementsByTagName("li");
		  for (var i=0; i< con.length;i++){
		     var text = con[i].getAttribute("title");
			  if(text!=null)
			  {
			    document.write(text+"<br>");
			  }
		  } 
	  </script> 
	  </body>
  </html>
  ~~~

* setAttribute()：方法增加一个指定了名称和值的新属性，或者把一个现有的属性设定为指定的值。

  ~~~ html
  elementNode.setAttribute(name,value);
  ~~~

* 节点属性：在文档对象模型（DOM）中，每个节点都是一个对象。

  | **属性/节点类型** | **元素节点** | **属性节点** | **文本节点** | **文档节点** | **注释节点** |
  | ----------------- | ------------ | ------------ | ------------ | ------------ | ------------ |
  | nodeName | 标签名 | 属性名 | #text | #document | |
  | nodeValue | null/undefined | 属性值 | 文本本身 | |
  | nodeType | 1 | 2 | 3 | 9 | 8 |
  
* 访问子节点 childNodes
 
1. node.firstChild 相当于 node.childNodes[0]
2. node.lastChild 相当于 node.childNodes[node.childNodes.length - 1]

  ~~~ html
  <body>
	 <div>javascript<p>javascript</p><div>jQuery</div><h5>PHP</h5></div>
	 <script type="text/javascript">
		 var div = document.getElementsByTagName("div");
		 var nodes = div[0].childNodes;
		 document.write(nodes.length);
		 for (var j = 0; j < nodes.length; j ++){
			document.write(nodes[j].nodeName + ":" + nodes[j].nodeValue + "<br>");
		 }
	 </script>
	 </body>
  ~~~

  ~~~ bash
  // 运行结果
  4#text:javascript
  P:null
  DIV:null
  H5:null   
  ~~~
  
  ~~~ html
  <!DOCTYPE HTML>
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <title>无标题文档</title>
  </head>
  <body>
  <ul id="con">
  <li id="lesson1">javascript
	 <ul> 
		  <li id="tcon"> 基础语法</li>
		  <li>流程控制语句</li>
		  <li>函数</li>
		  <li>事件</li>
		  <li>DOM</li>
	 </ul>
  </li>
  <li id="lesson2">das</li>
  <li id="lesson3">dadf</li>
  <li id="lesson4">HTML/CSS 
	 <ul>
		<li>文字</li>
		<li>段落</li>
		<li>表单</li>
		<li>表格</li>  
	 </ul> 
  </li>
  </ul>  
  <script  type="text/javascript">
	  function omitSpace(o){
			
	  }
	  var mylist = document.getElementById("tcon");
	  var newArr = new Array();
	  var ul0 = mylist.parentNode.parentNode.parentNode.childNodes;
	  for (var i = ul0.length - 1; i >= 0; i --){
		  if (ul0[i].nodeType == 1){
			  var lastUL = ul0[i].childNodes;
			  for (var j = lastUL.length - 1; j >= 0; j --){
				  if (lastUL[j].nodeType == 1){
						var lastLI = lastUL[j].childNodes;
						for (var k = lastLI.length - 1; k >= 0; k --){
							 if (lastLI[k].nodeType != 1){
								  continue;
							 }
							 else{
								  document.write(lastLI[k].innerHTML + "<br>");
							 }
						}
						break;
				  }
				  else{
						continue;
				  }
			  }
			  break;
		  }
		  else{
				continue;
		  }
	  }
	  //document.write();
  </script> 

  </body>
  </html>
  ~~~
  ~~~ bash
  // 运行结果：目的就是提取出以下的四个科目。
  ...
  表格
  表单
  段落
  文字
  ~~~

* nextSibling 属性可返回某个节点之后紧跟的节点（处于同一树层级中）。
  ~~~ html
  // 如果无此节点，则该属性返回 null。
  nodeObject.nextSibling
  ~~~

* previousSibling 属性可返回某个节点之前紧跟的节点（处于同一树层级中）。
  ~~~ html
  // 如果无此节点，则该属性返回 null。
  nodeObject.previousSibling  
  ~~~

* 插入子节点 appendChild()：在指定节点的最后一个子节点列表之后添加一个新的子节点。
  ~~~ html 
  appendChild(newnode)
  ~~~
  
  ~~~ html
  <body>
  <ul id="test">
	 <li>JavaScript</li>
	 <li>HTML</li>
  </ul> 
  <script type="text/javascript">
	 var otest = document.getElementById("test");  
	 var php = document.createElement("li");
	 php.innerHTML="PHP";
	 otest.appendChild(php);
  </script> 
  </body>
  ~~~

* insertBefore() 方法可在已有的子节点前插入一个新的子节点。
  ~~~ html
  // newnode: 要插入的新节点。
  // node: 指定此节点前插入节点。
  insertBefore(newnode,node);
  ~~~
  
  ~~~ html
  <script type="text/javascript">
	 var otest = document.getElementById("test");
	 var lis = otest.childNodes;
	 var newLI = document.createElement("li");
	 newLI.innerHTML = "php";
	 for (var i = 0; i < lis.length; i ++){
		 if (lis[i].innerHTML == "HTML"){
			 otest.insertBefore(newLI, lis[i]);
		 }
		 else{
			  continue;
		 }
	 }
  </script> 
  ~~~

* 
