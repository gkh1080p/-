# 开头

lang=""	

en---->英文网站

zh-CN------->中文网站 

charset=""----->UTF-8（万国码）的编码方式，还有GB2312、BIG5、GBK

```html
<!DOCTYPE html>
<html lang="zh-CN">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible",content="Ie-edge"> 
        <meta name="viewport" content="width=device-width, initial-scale">
    </head>
   <body>
       
    </body>
</html>
```

# 常用标签

```html
<h1><h1>
<h2></h2>一直到h6，总要性一直减小
<strong>加粗</strong>
<em>倾斜</em>
<del>删除线</del>
<ins>下划线</ins>
    
    
<div>
    就是一个盒子
    一行只能放一个大盒子
    </div>
<span>
    没有语义，就是个盒子
    一行可以放好多个
    </span>
 <img src="图像位置" / alt="替换文本，当图片显示不出来的时候，显示文字">图像位置尽量使用相对位置
    title="提示文本，当鼠标放在文字上时，会出现提示文字"
    width="" 宽度
    height="" 高度
    border="" 边框
 <a href="跳转目标" target="目标窗口的弹出方式">文本</a>
    target=""	_blank再打开一个窗口_self当前窗口打开的方式
    href=""	可以为内部链接也可以为官网连接，但是内部链接基本上已经放弃使用，
    		也可以放一个下载文件压缩包，
    		网页元素加链接，如图片和嵌入式视频
    		锚点链接：当我们点了某个链接后，跳转到链接中的某一个位置，#名字如
    			<a href="#tow">跳转到id为two的地方</a>
    			<h1 id="two">跳转到这</h1>
<del>删除线</del>
<ins>下滑线</ins> 
<blockquote cite="引用来源标注">这里是长引用</blockquote>
<abbr title="你可以看见我啦">鼠标放上来会有提示</abbr>
#&...表示转义
<object data="">
    指在html中嵌入java applet,Pdf阅读器Flash阅读器，也可嵌入html
    </object>

   
    
    
```

# 表单

```html
<form action="" method="get/post">
    <fieldset>元素组合表单的相关数据
    <legend>
        为fieldset标签定义标题
        </legend>
    <input type="text/radio/submit">
    type属性
        text表示输入文本	当有required属性时，没有文本框为空时表单不能提交
    	radio表示点击按钮
    	submit表示提交按钮
    	action代表把表单数据发送到的后台服务器网站
    	method表示表单表示表单提交的方式
    	search搜索框
        file提交文件
   required="required"必填选项属性
   placeholder="提示文本" 可通过input::placeholder{}伪类来实现样式改变
   autofocus="autofocus"光标进入网页自动聚焦
   autocomplete="off/on"自动保存已写过的数据，或者关闭自动保存（前提form有name属性）
   multiple在上穿文件属性时，使文件一次可以上传多份
</form>

<form action="">
        男<input type="radio" name="sex" checked> 
    	女<input type="radio" name="sex">
    	当name相同时不能多选，checked代表默认为...
    
    	复选框（多选框）：<input type="checkbox"name="" id="">与单选框类似
    
    	姓名:<input type="text" name="..." value="">
    	value代表着默认值
    	<input type="submit" value="...">
    	value代表着按钮中文字
</form>
    
在js中表单对象.reset()可以重置表单
```

![input表单属性](E:\桌面\html学习\图片笔记\input表单属性.png)

## form属性

```html
form中其它属性
	target 属性规定提交表单后在何处显示响应。
            _blank	响应显示在新窗口或选项卡中。
            _self	响应显示在当前窗口中。
            _parent	响应显示在父框架中。
            _top	响应显示在窗口的整个 body 中。
            framename	响应显示在命名的 iframe 中。
	autocomplete 属性规定表单是否应打开自动完成功能。是否记住上次的输入
		启用自动完成功能后，浏览器会根据用户之前输入的值自动填写值。如
		<form action="" autocomplete="on"></form> 
	novalidate 属性是一个布尔属性。
		如果已设置，它规定提交时不应验证表单数据。(可深度学习php)
		<form action="" novalidata="novalidata"></form>
 
	
     
```

## 表单元素

```css
下拉列表
<select>
    <option value="...">...</option>
    <option value="...">...</option>
    <option value="...">...</option>
    <option value="...">...</option>
</select>

输入多行文本
<textarea>
    。。。。
</textarea>
点击按钮
<button type="button" onclick="alert('Hello World!')">点击我！</button>
onclick表示链接到某种操作或网站，多用于js

<datalist>输入框选择按钮


    input中list一定要与datalist的id相同
    <form action="action_page.php">
    <input list="browsers">
    <datalist id="browsers">
       <option value="Internet Explorer">
       <option value="Firefox">
       <option value="Chrome">
       <option value="Opera">
       <option value="Safari">
    </datalist> 
    </form>
    
placeholder属性
placeholder 属性规定可描述输入字段预期值的简短的提示信息( 在输入框里面的提示文字，内容不会被提交)，例如一个样本值或是预期格式的简短的描述。
placeholder 定义的提示会在用户输入值之前显示在输入字段中。
注意：placeholder 属性适用于下面的 input 类型：text、search、url、tel、email 和 password。

```



# 列表

```html
表单tr=行；td=列,th一般为表头标签
table标签表示表单，border表示边框粗细,cellpadding表示表中内容与边框之间的距离,cellspacing表示边框与边框之间的距离；bgcolor表示表格的背景颜色,background表示背景图片，bgcolor与background都可在单独的表格中进行元素的添加;align表示对内容排版，左对齐或者右对齐;frame表示框架模板
<table border="10" cellpadding="10" cellspacing="10" bgcolor="red/rgb()" background="" align="left/right" frame="box/above/below/hsides/vsides">
<caption>我是标题标签</caption>
<tr>
	<th></th>
    <th></th>
</tr>
<tr>
	<td></td>
    <td></td>
</tr>
</table>
<th colspan="2">表示跨两列</th>
<td rowspan="2">表示跨两行</tr>
<thead>表眉</thead>
<tbody>内容</tbody>
<tfoot>脚</tfoot>
创建列表删除前面的圆点可用css中的属性list-style: none;
<ul>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

```css
border-collapse:collapse;将表格边框进行合并
collapse：将边框合并为单一的边框
separate：默认值，边框被分开，不会合并
inherit：继承父元素的 border-collapse 属性值。
```



# 转义字符

```html
&nbsp;	表示空格
```

# 更多标签

```html
<iframe src="URL" width="200" hight="200"></iframe>	用于在网页内部再镶嵌一个网页
width	代表宽度
hight	代表高度

<iframe src="/example/html/demo_iframe.html" name="iframe_a"></iframe>
将链接链接到iframe的名称，即target等于name的值
<p><a href="http://www.w3school.com.cn" target="iframe_a">W3School.com.cn</a></p>
<section>定义文章的节，有主题有内容 (大号div)</section>
<article>独立的自包含内容，文档有其自身的意义，并且可以独立于网站其它内容进行阅读</article>
<header>页眉</header>
<footer>页脚</footer>
<nav>导航链接集合</nav>
<aside>页面元素之外的内容（侧边栏标签）</aside>
<figure>
<figcaption>通常和figure一起连用，可作为图片标题</figcaption>
</figure>



```

# 框架

```html
数值框架
<html>

<frameset cols="50%,50%,25%">

  <frame src="/example/html/frame_a.html">
  <frame src="/example/html/frame_b.html">
  <frame src="/example/html/frame_c.html">

</frameset>

</html>

水平框架

<html>

<frameset cols="50%,50%,25%">

  <frame src="/example/html/frame_a.html">
  <frame src="/example/html/frame_b.html">
  <frame src="/example/html/frame_c.html">

</frameset>

</html>

```

# 在页面中嵌入计算机语言

```html
<code>
这个里面的计算机语言会删掉空格和换行
</code>

<pre>
这个里面代码会换行
且显示原先的代码不改变代码方式
</pre>
<var>
数学语言
</var>
```

# 声音视频

```html
视频嵌入
<video width="320" height="240" controls="controls" autoplay="autoplay">
  <source src="/i/movie.ogg" type="video/ogg" />
  <source src="/i/movie.mp4" type="video/mp4" />
  <source src="/i/movie.webm" type="video/webm" />
  <object data="/i/movie.mp4" width="320" height="240">
    <embed width="320" height="240" src="/i/movie.swf" />
  </object>
</video>

autoplay="autoplay"	自动播放
muted="muted"		静音
controls="controls"	 显示插件（暂停，播放等按钮）
loop="loop"			循环播放
preload="auto/none"	 预加载和不预加载
poster=放一张图片	 加载等待时间的画面



上例中使用了 4 中不同的视频格式。HTML 5 <video> 元素会尝试播放以 mp4、ogg 或 webm 格式中的一种来播放视频。如果均失败，则回退到 <embed> 元素。
    
    
嵌入声音
<audio controls="controls" height="100" width="100">
  <source src="song.mp3" type="audio/mp3" />
  <source src="song.ogg" type="audio/ogg" />
</audio>
<embed height="100" width="100" src="song.mp3" />
    
autoplay="autoplay"	自动播放
controls="controls"	 显示插件（暂停，播放等按钮）
loop="loop"			循环播放

```

