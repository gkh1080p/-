# 视口

## 布局视口layout viewport

```
 ios Android基本将这个视口分辨率设置为980px,所以pc上的页面都能在手机上呈现，只不过元素看上去小

```

## 视觉视口visual viewport

```css
 我们可以通过缩放去操作视觉视口，但不会影响布局视口，布局视口任保持原来的宽度
```

## 理想视口 ideal viewport

```
为了使网站在移动端有最理想的浏览和阅读宽度而设定
理想视口，对设备来讲，是最理想的视口尺寸
需要手动添写meta视口标签通知浏览器操作
meta视口标签的主要目的：布局视口的宽度应该与理想视口的宽度一致，简单理解就是设备有多宽，我们布局的视口就有多宽
```

## 视口标签

```css
<meta namme="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0,maximum-scale=1.0,minimum-scale=1.0">
user-scalable=no	不允许用户进行缩放
maximum-scale=1.0	最大缩放倍数为1.0
minimum-scale=1.0	最小缩放倍数为1.0
```

# 二倍图

```
物理像素点指的是屏幕显示的最小颗粒，是物理真实存在的。这是厂商出厂时设置好的
我们开发时候1px不一定等于1个物理像素
pc端1px等于1个物理像素，但移动端就不尽相同
一个px的能显示的物理像素点的个数，称为物理像素比或屏幕像素比

Retina(视网膜屏幕)是一种显示技术，可以将更多的物理像素点压缩至一块屏幕里，从而达到更高的分辨率，提高屏幕的细腻程度。
```

```css
#图片缩放
通过先对图片缩小n倍，然后在客户端时会被自然放大，这样图片的清晰度不会降低
n为相应客户端缩放pc端的倍数
#背景图像
background-size:x y ;只写一个就是宽度，高度会等比例缩放
					也可以用百分比
					cover完全覆盖
					contain使宽度或者高度适合区域
```

# 移动端开发选择

## 单独制作移动端页面(主流)

通过设备来检测，通过设备的不同来判断打开什么页面

```css
流式布局(百分比布局)
flex弹性布局(强烈推荐)
less+rem+媒体查询布局
混合布局
```

## 相应式页面兼容移动端(其次) 

通过页面的大小来改变的页面

制作麻烦需要大力精力开发

```css
媒体查询
bootstarp
```

# 初始化样式

```css
Normalize.css
官方地址:http://necolas.github.io/normalize.css/

#####
body初始化样式
Max-width:540px;
min-width:320px;
margin:0 auto;
font:normal 14px/1.5 tahoma,"Lucida Grande",Verdana,"MicroseoftYahei",STXihei,hei;
color:#000;
background:#f2f2f2;
overflow-x:hidden;
-webkit-tap-highlight-color:transparent;

```

# 盒子模型

```css
box-sizing:border-box;		//移动端，外边距和边框不会撑开盒子
box-sizing:content-box;		//传统box，外边距和边框会撑开盒子
```

# 特殊样式

```css
清除高亮显示，如链接高亮
-webkit-tap-highlight-color:transparent;
去掉默认外观样式,如按钮等样式
-webkit-appearance:none;
禁用长按页面时的弹出菜单,如图片链接等
-webkit-touch-calloout:none;


```

# 布局

## 流式布局(百分比布局)

```css
通过盒子的宽度设置成百分比来根据屏幕的宽度来进行伸缩，不受固定像素的限制，内容向两侧填充
式移动web开发使用的比较常见的布局方式
max-width: ;	最大的宽度
min-width: ;	最小的宽度
```

## flex布局

```css
IE11以下的版本不支持
父盒子disp:flex;
子盒子float clear vertical-align将失效
伸缩布局=弹性布局=伸缩盒布局=弹性布局=flex布局
```

### 给父亲常加的元素

```css
flex-direction:设置主轴的方向
	row	默认 从左到右
	row-reverse	从右到左
	column	从上到下
	column-reverse	从下到上
############################################################################################
justify-content:设置主轴上的子元素排列方式
	flex-start	默认值，从头开始，如果主轴是x轴则从左到右
	flex-end	从尾部开始排列
	center		在主轴居中对齐(如果主轴是x轴则水平居中)
	space-around	平分剩余空间
	space-between	先两边贴边，再平分剩余空间（重要）
############################################################################################
flex-wrap:设置子元素是否换行(默认不换行，相当于当子元素该换行时可以缩小盒子宽度，从而不换行)
	nowrap	默认值，不换行
	wrap	换行
############################################################################################
align-content:设置侧轴上的子元素的排列方式（多行）
	flex-start	默认值，在侧轴的头部开始排列
	flex-end	在侧轴的尾部开始排列
	center	在侧轴中间显示
	space-around	子项在侧轴平分剩余空间
	space-bteween	子项在侧轴先分布在两头，再平分剩余空间
	stretch	设置子项元素高度平分父元素高度
############################################################################################
align-items:设置侧轴上的子元素排列方式（单行）
	flex-start	从上到下
	flex-end	从下到上
	center		挤在一起居中（垂直居中）
	stretch		拉伸（默认值）
############################################################################################
flex-flow:复合属性，相当于同时设置了flex-direction和flex-wrap
```

### 给子项常加的属性

```css
flex	子项目占的份数
	参数为数字，代表着子盒子在父盒子中占有的份数
	也可以写%，相对于父级来说的
############################################################################################
align-self控制子项自己在侧轴的排列方式
 	self-end	自己在下面
	self-strat	自己在上面
	...
############################################################################################
order属性定义子项的排列顺序（前后顺序）	
	数值越小越靠前，默认是0，可以为负数
	注意：和z-index不一样
```

## rem适配布局

```css
rem是一个相对单位，类似于em，em父元素字体大小
不同的是rem是相对于html元素的字体大小
比如：根元素(html)设置font-size=12px；非根元素设置width:2rem;则换成px为24px
```

### 媒体查询(Media Query)

```css
使用媒体查询可以针对不同的媒体类型定义不同的样式
@media可以针对不同的屏幕尺寸设置不同的样式
当你重置浏览器大小过程中，页面也会根据浏览器的宽度和高度重新渲染页面

@media mediatype and|not|only (media feature){
        css-Code;
}
用@media开头 注意@符号
mediatype 媒体类型
    all	用于所有设备
    print	用于打印机和打印预览
    scree	用于电脑屏幕，平板电脑，智能手机
关键字 and not only
    and	可以将多个媒体特性连接到一起，相当于"且"的意思
    not	派出某个媒体类型，相当于"非"的意思
    only	指定某个特定的媒体类型
media feature媒体特性 必须有小括号包含
    width	定义可见域宽度
    min-width	定义输出设备中页面最小可见区域宽度
    max-width	定义输出设备中页面最大可见区域宽度
```

### 媒体查询引入样式

```css
<link rel="stylesheet" media="mediatype and|not|only (media feature)" href="mystylesheet.css">
```

### rem实际开发适配方案1 

![](E:\桌面\html学习\图片笔记\元素大小取值方法.png)

## 响应式开发

### 原理

```
通过不同屏幕的大小的而改变页面变化
```

### 响应式布局容器

```
响应式需要一个父级做为布局容器，来配合子级元素来实现变化效果
原理就是在不同屏幕下，通过媒体查询来改变这个布局容器大小，再改变里面子元素的排列方式和大小，从而实现不同屏幕下，看到不同的页面布局和样式变化。
```

### 响应式屏幕尺寸划分

![](E:\桌面\html学习\图片笔记\响应式屏幕尺寸.png)

# swiper插件

```css
通过b战学习
https://www.bilibili.com/video/BV14J4114768?p=484&share_source=copy_web
```

# 利用git提交到网站到码云

```css
https://www.bilibili.com/video/BV14J4114768?p=496&share_source=copy_web
```

