# createTextNode() 方法创建新的文本节点，返回新创建的 Text 节点。

  ~~~ html 
  // 字符串值，可规定此节点的文本。
  document.createTextNode(data)
  ~~~

  ~~~ html
  <body>
  <script type="text/javascript">
		var main = document.body;
		var p = document.createElement("p");
		p.setAttribute("class", "message");
		//p.className = "message"; // 这样写也可以，因为 js 中 DOM 属性的 class 会写成 className。
		var text = document.createTextNode("I love JavaScript!");
		main.appendChild(p);
		p.appendChild(text);
  </script> 
  </body>
  ~~~
