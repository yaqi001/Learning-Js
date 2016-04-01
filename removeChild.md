# removeChild() 方法从子节点列表中删除某个节点。如删除成功，此方法可返回被删除的节点，如失败，则返回 NULL。
  
  ~~~ html
  nodeObject.removeChild(node)
  ~~~

  ~~~ html
  <body>
	  <div id="content">
		 <h1>html</h1>
		 <h1>php</h1>
		 <h1>javascript</h1>
		 <h1>jquery</h1>
		 <h1>java</h1>
	  </div>
	  <script type="text/javascript">
	  // 一次性清除所有节点。。
	  function clearText() {
		 var content=document.getElementById("content");
		 var h1s = content.childNodes;
		 while(h1s.length != 0){
			 var con = content.removeChild(h1s[0]);
			 //document.write(h1s.length + "--" + con.innerHTML + "<br>");
		 } 
	  }
	  </script>
	  <button onclick="clearText()">清除节点内容</button>
  </body>
  ~~~

