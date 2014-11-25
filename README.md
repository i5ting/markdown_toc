markdown_toc
============


## 用法

see demo/lite/index.html

```javascript
<script type="text/javascript" src="../../js/jquery-1.4.4.min.js"></script>
<script type="text/javascript" src="../../src/markdown_toc.js"></script>
<script type="text/javascript" >
$(document).ready(function(){
	$('#tree').markdown_toc({
		is_auto_number:true
	});
});
</script>
```
		
## 依赖

目前只有1个依赖库

- jquery-1.4+

## 定制

### 定制步骤

1. 修改markdown_toc里的compile_headers_with_item函数
1. 按照自己的需求修改返回的html结构，参数item是节点对象

### 定制方法

```javascript
<script type="text/javascript" src="../../js/jquery-1.4.4.min.js"></script>
<script type="text/javascript" src="../../src/markdown_toc.js"></script>
<script type="text/javascript" >
$(document).ready(function(){
	$('#tree').markdown_toc({
		is_auto_number:true,
		compile_headers_with_item:function(item){
			return " <h"+item.level +"><a href='#" +item.id+ "'>" + item.orderd_title + "</a></h"+item.level +">"
		}
	});
});
</script>
```

### item对象

```javascript
item = {
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

### item对象属性说明

- id是唯一编号，可以作为锚点id
- level是标题层级
- orderd_title是带有序号的标题
- origin_title是没有序号的原始标题
- open是十分可以展开，如果是，说明它由子节点
- pId是当前节点的父亲节点id
- target是打开方式
- url是锚点的url地址


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## 推荐

- [i5ting_ztree_toc](https://github.com/i5ting/i5ting_ztree_toc) 带有树形结构
- 生成器 [ruby版本tocmd](https://github.com/i5ting/tocmd.gem) 
- 生成器 [node版本i5ting_toc](https://github.com/i5ting/tocmd.npm)
- [gulp task for i5ting-toc](https://github.com/i5ting/gulp-i5ting-toc)


## 版本历史

- v0.1.0 初始化版本

## 欢迎fork和反馈

- write by `i5ting` shiren1118@126.com

如有建议或意见，请在issue提问或邮件

## License

this repo is released under the [MIT
License](http://www.opensource.org/licenses/MIT).