# 替换元素节点 replaceChild()：实现子节点(对象)的替换。返回被替换对象的引用。 
  ~~~ html
  node.replaceChild (newnode,oldnew ) 
  ~~~
  
  ~~~ html
  <body>
	<div><b id="oldnode">JavaScript</b>是一个很常用的技术，为网页添加动态效果。</div>
	<a href="javascript:replaceMessage()"> 将加粗改为斜体</a>
	<script type="text/javascript"> 
		function replaceMessage(){
			var oldNode = document.getElementById("oldnode");
			var newNode = document.createElement("i");
			newNode.innerHTML = oldNode.innerHTML;
			oldNode.parentNode.replaceChild(newNode, oldNode);
		}
	</script>
  </body>
  ~~~
