markdown_toc
============


## 用法

```
<script type="text/javascript" src="../../js/jquery-1.4.4.min.js"></script>
<script type="text/javascript" src="../../src/markdown_toc.js"></script>
<SCRIPT type="text/javascript" >
<!--
$(document).ready(function(){
	$('#tree').markdown_toc({
		is_auto_number:true
	});
});
//-->
</SCRIPT>
```
		
## 依赖

目前只有1个依赖库

- jquery-1.4+

## 定制方法

```
<script type="text/javascript" src="../../js/jquery-1.4.4.min.js"></script>
<script type="text/javascript" src="../../src/markdown_toc.js"></script>
<SCRIPT type="text/javascript" >
<!--
$(document).ready(function(){
	$('#tree').markdown_toc({
		is_auto_number:true,
		compile_headers_with_item:function(item){
			return " <h"+item.level +"><a href='#" +item.id+ "'>" + item.orderd_title + "</a></h"+item.level +">"
		}
	});
});
//-->
</SCRIPT>
```

说明item对象属性包含

```
{
  "id": 2105,
  "level": 1,
  "orderd_title": "21.5. 三部分的关系",
  "origin_title": "三部分的关系",
  "open": true,
  "pId": 21,
  "target": "_self",
  "url": "#2105"
}
```

- id是唯一编号，可以作为锚点id
- level是标题层级
- orderd_title是带有序号的标题
- origin_title是没有序号的原始标题
- open是十分可以展开，如果是，说明它由子节点
- pId是当前节点的父亲节点id
- target是打开方式
- url是锚点的url地址

