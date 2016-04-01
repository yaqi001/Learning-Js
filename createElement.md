# createElement() 方法可创建元素节点。此方法可返回一个 Element 对象。
 
~~~ html
// tagName：字符串值，这个字符串用来指明创建元素的类型。
document.createElement(tagName)
~~~

~~~ html
<script type="text/javascript">
var main = document.body;
createa("http://www.imooc.com", "imooc");
{
    var link = document.createElement("a");
    link.setAttribute("href", url);
    link.innerHTML = text;
    main.appendChild(link);
}
</script> 
~~~


