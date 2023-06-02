# CSS初始化

```css
style{
* {
            margin: 0;
            padding: 0;
        }
        /* 让斜体不斜体 */
        
        em,
        i {
            font-style: normal
        }
        /* 去掉li的小圆点 */
        
        li {
            list-style: none;
        }
        
        img {
            /* 如果有的图片有链接的化，会有边框 */
            border: 0;
            /* 让文字悬浮在图片旁边的中间，取消图片底下有空袭 */
            vertical-align: middle;
        }
        /* 通过提交按钮有个小手图标 */
        
        button {
            cursor: pointer;
        }
        /* 链接变色，和取消下划线 */
        
        a {
            color: #666;
            text-decoration: none;
        }
        
        a:hover {
            color: #c81623;
        }
        
        button,
        input {
            font-family: Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB;
        }
        
        body {
            /* 抗锯齿性 */
            -webkit-font-smoothing: antialiased;
            background-color: #fff;
            font: 12px/1.5 Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB;
            color: #666;
        }
 }  
```

# 插入方式

```html
嵌入式
<style type="text/css"></style>
外部链接式
<link href="xxx.css" rel="stylesheet">
标签内部嵌入式
<a href="#" style=" width:10px"></a>

```

# 选取标签方式

```css
#+id	选取id相同的标签
.+class	选取相同class的标签 可通过多类名来定义标签
*		选取所有标签
多用于清楚所有元素标签的内外边距
*{
margin:0;
padding:0;
}

name	直接根据标签名称来选取标签（不建议使用）

后代选择器
ol il{
    选择ol中il标签
}
.nav il{
    可以是任意选择器的组合
}

子选择器
选择亲儿子
div>p{
    用">"符号来选择
}

并集选择器
用","来连接两个标签
div,span{
    选择div和span 
    可任意组合，可将子选择器也一起用
}

伪类选择器
用":"来表示
有链接伪类
a:link	选择所有未被访问的链接
a:visited 选择所有已被访问的链接
a:hover		选择鼠标指针位于其上的链接
a:active	选择活动链接（鼠标按下未弹起的链接）
input[type='checkbox']:checked	当复选框被勾选时会做出相应的css
一般情况下用hover就可以了

:focus用于选取获得焦点的表单元素
焦点就是光标，一般情况<input>类表单元素才能获取，因此这个选择器也主要针对于表单元素来说，列如
input:focus{
    background-color: ;
    red
}

属性选择器
x[class]
x[class=""]		通过x标签中的class属性来选着
x[class^="ico"]	标签x的属性class中以ico"开头"的标签选中
x[class$="ico"]	标签x的属性class中以ico"结尾"的标签选中
x[class*="ico"]	标签x的属性class中"有"ico的标签选中

结构伪类选择器
E:first-child	选取E中第一个孩子 ul li:first-child{}选取ul中li第一个
E:first-last	选取E中最后一个孩子
E:nth-child(n/odd(奇数)/even(偶数))	选取E中第n/odd(奇数)/even(偶数)个孩子，n也可以为公式，从0开始
E:first-of-type	指定类型E的第一个
E:last-of-type	指定类型E的最后一个
E:nth-of-type()	指定类型第n个
区别，nth-of-type先看孩子，然后再看选第几个；而，nth-child先看选第几个，然后再看孩子，如果第n个不是孩子，则不选

伪元素选择器
::before	在元内部素前面插入内容
::after		在元素内部后面插入内容
必须要有content属性
```

# 字体

```css
font-family:'';
宋体，微软雅黑，用英文名更好，如微软雅黑=Microsoft Yahei
可写多个字体，但是要用逗号隔开。执行起来是按从前到后的顺序
最常见的：'Microsoft YaHei',tahoma,arial,'Hiragino Sans GB'

font-size:;
文字大小，谷歌默认16px，单位有px也有别的
标题标签特殊，h1~6，需要手动更改

font-weight: ;
文字粗细 
bold 粗体 
通过数字来来改变粗细；700相当于加粗，400表示正常

font-style: ;
文字样式
正常字体 normal
斜体文字 italic

复合写法
font: font-style font-weight font-size/line-height font-family;
	  样式		粗细		大小		行高			类别（微软雅黑）	
不能改变顺序
可以省略，但是font-size和font-family不能省略
```

# 文本

```css
文本颜色
color: ;
预定义的颜色:red green blue...
十六进制：#FFOOOO,#FF66OO
RGB代码：rgb(x,y,z),rgb(x%,y%,x%)

对齐
text-align: ;
只能设置水平对齐方式
right右对齐
left左对齐--->默认
center水平居中对齐

装饰文本
text-decoration: ;
none默认没有装饰线
underline下划线
oberline上划线
line-throug删除线

首行缩进
text-indent: ;
可用px也可用em，em是相对单位1em就是当前文字相对大小

行间距
line-heigth: ;
行间距由，文本高度+上间距+下间距。上间距=下间距

垂直居中
让行高等于盒子的高度
line-height=height


#单行文本溢出显示省略号--必须满足三个条件
1 先强制一行内显示文本	white-space:nowrap;
2 超出部分隐分			overflow:hidden;
3 文字用省略号代替超出部分	text-overflow:ellpsis;

#多行溢出文字显示省略号
1 弹性伸缩盒子模型	display:-webkit-box;
2 限制在一个块元素显示的文本的行数	-webkit-line-clamp: x;第x行显示省略号
3 设置或检索伸缩盒对象的子元素的排列方式	-webkit-box-orient:vertical;


```

# 显示模式

```html
块级元素
<h1>~<h6>、<p> <div>、<ul>、<ol>、<li>
独占一行
高度、宽度、外边距以及内边距可控
宽度默认是父级一样
是一个容器及盒子，里面可以放行内或者块级元素
    注意:
   	文字类元素不能使用块级元素
    <p>里面不能放块级元素，特别是不能放div
     h1~h6等也是文字类块级标签，里面也不能放其它块级元素
        
        
行内元素
常见的有:<a><strong><b><em><i><del><s><ins><u><span>
一行上可以显示多个
宽和高直接设置是无效的
默认宽度是它本身内容的宽度
行内元素只能容纳文本或其它行内元素
    注意:
        链接里面不能再放链接
        特殊情况链接<a>里面可以放块级元素，但给<a>转换一下块级模式最安全
    

      
行内块元素
<img>、<input>、<td>、<textarea>(文本域)
特点:
        和相邻行内元素行内快在一行上，但是他们之间有空白间隙，一行可以显示多个
        默认宽度就是它本身内容宽度
        行高，高度，外边距，内边距，都可以控制，
行内块转换
        display: ;
        block是块元素
        inline是行内元素
        inline-block行内块元素
        none不显示
        table转换为块级元素并且在一行上显示
        
```

# 背景

```css
背景颜色
background-color: ;
transparent透明
或者直接加颜色

背景渐变
background:linear-gradient(起始方向，颜色1，颜色二，、、、)
background:-webkit-linear-gradient(left,red,blue);
background:-webkit-linear-gradient(left top,red,blue);
需要加私有前缀，-webkit，移动端用的多

背景图片
background-image:url() ;

背景平铺
background-repeat: ;
防止背景重复的显示
repeat平铺
no-repeat不平铺
repeat-x横向平铺
repeat-y纵向平铺

背景图片位置
background-position:x y ;
x y可以是方位名词 top left center bottom right
x y可以是精度单位,如果是精确单位，那么前面必须是x后面必须是y；如果只有一个单位，那么是x值，y值默认是居中
可混合单位，如 20px center


背景固定
background-attachment: ;
固定背景图片或者随着随着页面其余部分滚动
scroll背景滚动
fixed背景图像固定

复合写法
background: ;

背景色透明
background: ;
rgba(x,y,z,t)t为透明度，1表示不透明


背景图片尺寸
background-size: 100% 50%;  宽度占满屏幕，高度占50%
background-size: 100% 100%; 宽度高度都占满整个屏幕，除非图片完美适配，否则图片会变形
background-size: 100% auto; 宽度占满屏幕，高度自动适配，高度有所牺牲
background-size: auto 100%; 高度占满屏幕，宽度自动适配，宽度有所牺牲
至于是要牺牲宽度还是高度，具体问题具体分析，比如学子的沙发可以裁掉，有的背景图不能裁
background-size: cover；铺满整个容器，多余的部分会被裁掉
background-size: contain；至少有一张完整的图呈现出来，一定会有多余的空间




```

# css三大特性

## 层叠性

样式冲突的情况遵循就近原则，哪个样式离机构近，就执行哪个样式

样式不冲突不会层叠

## 继承性

继承text-、font-、line-这些元素开头的还有color

子元素会继承父元素的行高

行高可以不跟单位，1.5代表行高为当前文字的1.5倍

## 优先级

选择器相同，则执行层叠性

选择器不同，则根据选择器权重执行

![选择器](E:\桌面\html学习\图片笔记\选择器.png)

```css
**类选择器**，**属性选择器**，**伪类选择器**的权重是0，0，1，0	列如:hover	x[class=""](再加上x权重为11)
伪元素选择器权重为0，0，0，1，结合标签使用大部分为0，0，0，2
```



```css
important用法: color:pink!important;
```

# 盒子模型

## 组成

```css
withd:;可以时数值如px em rem
	   也可以时calc(公式)；列如calc(100% - 30px)	注意：符号前后要有空格
height:;可以时数值如px em rem
	   也可以时calc(公式)；列如calc(100% - 30px)


border边框
border-width	边框的粗细
border-style	边框的样式（必须要有 ）
border-color	边框的颜色
简写	border: 1px solid red;没有顺序
边框分开写法
border-top:;
border-bottom: ;
border-left: ;
border-right: ;
合并边框（多用于表格）
border-collapse:collapse;合并相邻的边框
边框会影响盒子的边框
可使用box-sizing:border-box;


padding内边距
padding-left/top/bottom/right表示上下左右的内边距
实例：
在做导航栏时可以通过内边距来撑开盒子，不要固定盒子宽度，看起来会不合理
也可使用box-sizing:border-box;

margin外边距
margin-left/top/bottom/right表示上下左右的外边距
应用：前提条件必须有with宽度，然后margin:auto;或margin:0 auto;
若相让盒子中的元素居中则在父类中添加text-aline:center;
外边距的塌陷问题(对于两个嵌套关系的块元素，父元素有上外边距同时子也有上边距，这时会出现塌陷)
解决方法
	1.为父元素定义上边框
	2.为父元素定义内边距
	3.可以为父元素添加overflow:hidden;
```

## 圆角边框

```css
border-radius:length;
当length为盒子高度的一半时，盒子为圆形
也可用50%来表示
border-radius:左上角 右上角 右下角 左下角;可以分别给不同的角加上圆角
border-left/right-bottom/top-radius: ;用来表示某个角
```

## 盒子阴影

```css
box-shadow:h-shadow v-shadow blur spread color inset;
必要
h-shadow,v-shadow分别表示水平位置和垂直位置，
可选
blur模糊距离(即模糊程度)
spread模糊尺寸
color模糊颜色
inset/outset将外部阴影改为内部阴影
```

## 文字阴影

```css
text-shadow:h-shadow v-shadow blur color;
对应的英文和盒子阴影一样的意思

```

# 浮动

```css
float: none/left/rigth;
没有浮动，左浮动，右浮动
浮动的特性
1.脱标（脱离标准流）
2.浮动元素会一行内显示且元素顶部对齐
3.浮动元素会有行内块元素的特性
任何元素都可以浮动，不管原先是什么模式元素，添加浮动之后具有行内块元素相似的特性（如果行内元素添加了浮动，这时不需要添加转换标签display）

注意点:
1.与标准流父元素一起用，即先创建一个大父盒子(定在页面中央)，然后让子盒子浮动
2.一个兄弟浮动了，其它兄弟理论上也得浮动
浮动的盒子只会影响浮动盒子后面的标准流，不会影响前面的标准流




```

## 清除浮动

```css
清除浮动
why??
1父盒子高度不能确定
2子盒子浮动了
3影响了下面的布局了
clear: ;
left清除左侧浮动的影响
right清除右侧浮动
both同时清除左右两侧浮动影响(用的最多)
清除浮动的策略，闭合浮动

清除浮动的方法
1.父级添加overflow属性
	将其属性值设置为hidden、auto、sroll;弊端会出现溢出
	最终方案：.clearfix::before,.clear::after{  content:''; display:table; clear:both; }
	通过最终方案，在父元素调用classfix的类属性完全解决高徒塌陷的问题
2.父级添加after伪元素
最好用的
只需要在父元素class中加入clearfix(什么名字都可以)类
clearfix:after{
    content: "";
    display:block;
    height:0;
    clear:both;
    visibility:hiddent;
    
}
.clearfix{
    *zoom:1;(照顾i6和i7版本)
}
	
3.父级添加双向伪元素
找到父盒子在其中class加入clearfix类
.clearfix:before,.clearfix:after{
    content:"";
    display:table;
}
.clearfix:after{
    clear:both;
}
.clerfix{
    *zoom:1;
}
4，额外标签法
	会在浮动元素末尾添加一个空的标签，例如<div style="clear:both"><div>、<br>等
	可以用额外标签法，列如
.clearfix::fater{
    conttent:'';
    display:block;
    heiht:0;
    clear:both;
    visibility:hidden;
}


闭合浮动
```



# ul和li

```css
list-style:none;
删除圆点	none,disc(默认标记实心圆)，square，decimal...
list-style-position:设置在何处放置列表项标记.即标记相对于列表项内容的位置。值有inside、outside（默认，文本左侧）、inherit（从父元素继承list-style-position的值）
list-style-image ：设置使用自定义图像来替换列表项的标记。值有URL，none（默认），inherit（继承）
```

# 常见的图片格式



![image-20230318192946772](E:\桌面\html学习\图片笔记\常见的图片格式.png)

# 页面布局的整体思路

![页面布局整体思路](E:\桌面\html学习\图片笔记\页面布局整体思路.png)

# CSS书写顺序

![Snipaste_2023-03-18_20-35-38](E:\桌面\html学习\图片笔记\CSS书写顺序.png)

# 定位

```css
让盒子自由自在的移动 
position: ;
static 静态定位
relative 相对定位
absolute 绝对定位
fixed 固定定位
sticky 粘性定位ssss
```

## 静态定位

```css
position:static;
标准流 
```

## 相对定位

```css
position:relative;
总是以自己原来的位置进行改变，不是脱标，它的原来的位置不会被顶掉
```

## 绝对定位

```css
position:absolute;
绝对定位是元素在移动位置的时候，是相对于它的祖先元素来说
(子'绝'父'相') 
注意:
1.如果没有祖先元素或者祖先元素没有定位，则以浏览器为准定位；
2.如果"祖先元素有定位"（相对，绝对，固定，粘性），则以最近一级的有定位祖先元素为参考点移动位置；
3.绝对定位不再占有原先位置("脱标")
4.绝对定位中，margin:0 auto;不能实现居中
	想要居中则:left:50%;margin-left:-盒子的一半;
	高度居中也是同样的原理

```

## 固定定位

```css
position:fixed;
固定定位是元素固定于浏览器可视区的位置，主要使用场景:可以在浏览器页面滚动时元素位置不变。
特点：
1、以浏览器的可视窗口为参照点移动元素

小技巧，让盒子贴着版心
position:fixed;
left:50%;
margin-left:中心盒子的一半;
注意该盒子要在版心盒子之前
```

## 粘性定位

```css
position:sticky;
在top/bottom/right/left中任意必须要有一个
占有原先的位置
```

## 叠放次序

```css
z-index:1;
数字越大，盒子越靠上
```

## 定位的特性

```css
1.行内元素如果添加了绝对定位或者相对定位，可以直接设置宽度和高度
2.块元素如果添加了绝对定位或相对定位，不设置宽度和高度，默认大小是内容的大小
3.浮动不会压住标准流的文字，但会压住标准流的盒子。而定位中的脱标会压住文字
```

# 元素的显示与隐藏

## display

```css
display:none;隐藏对象
display:block;除了转换为块级之外同时还有显示元素的意思
不但隐藏了，而且位置也没了
多应用于js可以做特效

```

## visibility

```css
visibility:	;
inherit继承上一个父对象的可见性
visible对象可视
hidden对象隐藏
collapse主要用于隐藏表格的行和列，隐藏的行或列能过被其它内容使用，对于表格外的其他对象，起作用等同于hidden
注visibility: ;
隐藏元素后，继续占有原来的位置
```

## overflow

```css
overflow: ;
visible 不剪切内容也不添加滚动条，加入显示声明此默认值，对象将被剪切为包含对象window或frame的大小，并且cip属性设置将失效
auto 此为body对象和textarea的默认值，在需要时剪切内容并添加滚动条
hidden 不显示超过对象尺寸的内容
scroll 总显示滚动条 
```

# 精灵图

```css
精灵图的意思就是，只用一张图让整个页面中的小图标都有
一张大的精灵图可以要使用的话需要知道图上每个图的坐标x,y然后用以下代码定位
background-position: x y;
用pxCook进行剪切

```

# 字体图标

```css
有的图标不建议用精灵图直接用css样式建立
下载网站
http://icomoon.io	外国
http://www.iconfont.cn/	中国 
```

## 使用

```css
先下载下来
然后解压，找到font文件
放到根目录下面(和html同一个文件夹中)
通过css引入html中，通过style.css来复制粘贴到，html中的style中，一直复制到第一个中括号"[]"

引入后使用
先在html中创建一个盒子，然后在之前解压的文件夹中找到"Demo.html",会展示所有图标，然后直接复制
再给字体设置样式，font-family="icomoon(例子)"，icomoon为之前下载图标的文字样式

追加
在解压后的包里找到"selection.json"从新上传，然后选中自己想要的图标，从新压缩包上穿即可
```

# CSS三角

```css
要想给一个盒子添加一个三角则，在上面添加一个盒子，然后宽高都等于0，然后边框设置为，transparent(透明边框)，然后再让其中的一个为显示的颜色，
class{
    width:0;
    heigth:0;
    border:10px solid transparent;
    border-top/bottom/right/left-color: pink/rgb()/#fff;
    其它样式
}


#直角三角形
只要上边框，和左或者右边框
width:0;
height:0;
border-color:transparent red transparent transparent;//red可以是别的颜色
border-style:solid;
border-width:22px 8px 0 0;	//上面稍微大一写（高度），下面稍微小一些
案例
<div class="price">
        <span class="miaosha">$1650
            <i></i>
        </span>
        <span class="yuanjia">$2300</span>
</div>


.miaosha {
            position: relative;
            float: left;
            width: 90px;
            height: 24px;
            background-color: orange;
        }
        
        .miaosha i {
            position: absolute;
            right: 0;
            width: 0;
            height: 0;
            border-color: transparent #fff transparent transparent;
            border-style: solid;
            border-width: 24px 10px 0 0;
        }
        
        .yuanjia {
            text-decoration: line-through;//删除线
        }
```

# 鼠标样式

```css
cursor: ;
default	小白默认
pointer	小手
move	移动
text	文本
not-allowed	禁止

```

# 轮廓线and防止拖拽文本域

```css
表单的轮廓线
outline: none;

防止拖拽文本域resize
textarea{ resize: none;}	textarea为文本域
```

# 图片一些操作

```css
vertical-align: ;
经常用于设置图片或者表单（行内块元素），和文字垂直对齐。官方解释：用于设置一个元素的垂直对齐方式，但只针对于行内元素或者行内快元素有效。
baseline	元素放在父元素的基线上；
top 		把元素的顶端与行中最高的顶端对齐
middle		把此元素放置在父元素中部
bottom		把元素的顶端与行中最低的元素的顶端对齐
#让文字跟在图片旁边对齐

对于解决文字的底下空白问题
1 certical-align：middle;什么都行
2 或者转成"块"元素

图片变模糊
filter:函数();列如：filter:blur(5px);blur模糊处理 数值越大越模糊
```

# 布局技巧

## 盒子边框不重叠

```css
通过margin-left:-1px;来改变多个浮动挨着时，边框重叠的问题
要想通过鼠标那个盒子，哪个盒子出现边框，这时可以通过加相对定位
 		li {
            width: 200px;
            height: 300px;
            background-color: pink;
            border: 1px solid black;
            margin-left: -1px;
            float: left;
            list-style: none;
       	 	}
        
        li:hover {
            border-color: olive;
            border-width: 4px;
            position: relative;
            /* 若每个盒子都有相对定位，则通过等级来 */
            z-index: 1;
        }
```

## 文字围绕浮动元素

```html
先创建一个大盒子，把图片包在盒子里面，然后再让盒子浮动
<div>
    <div>
        <img>图片
    </div>
    <p>
        文字
    </p>
</div>
```

## 行内块巧妙布局

```css
先创建多个行内块元素，让后在他们父盒子中添加text-align:center
```

# 过度

```css
transition:要过度的属性 花费的时间 运动曲线 何时到达;
属性:想要变化的css属性，宽度高度 背景颜色 内外边距都可以 可以写all 过度所有属性
花费时间:单位是秒
运动曲线:默认是ease（慢慢减速）、linear（匀速）、ease-in（加速）、ease-out（减速）、ease-in-out（先加速再减速）
何时开始:单位是秒 可以设置延迟触发时间 默认是0s

#让页面滚动条有滑动效果
html{scroll-behavior:smooth;}

注意：
如果要写多个属性，则用逗号分隔
```

# 网站图标

```css
1 制作图标
	把图标切成png图片
	把png图片转换为ico图标，第三方网站http://www.bitbug.net/
2 favicon图标放到网站根目录下
3 HTML页面引进favicon图标
在<head></head>中引入
<link rel="shortcut icon" href="favicon.ico(文件的名字)">
```

# TDK三大标签SEO优化

```html
SEO优化目的是对网站的深度优化，从而帮助网站获取免费流量，从而提升网站排名

T---->title标签
D---->description网站说明<meta name="description" content="....">
K---->keywords关键字<meta name="keywords" content="">
```

![类名书写规范](E:\桌面\html学习\图片笔记\类名书写规范.png)

## logo SEO优化

```html
1.logo里面首先放一个h1标签，目的是为了提权，告诉搜索引擎，这个地方很重要
2.h1里面再放一个链接，可以返回首页，把logo的背景图片给链接即可
3.为了搜索引擎收录我们，我们链接里面要放文字（网站名称），但文字不要显示出来
	方法一 text-indent:9999px移到盒子外面，然后overflow:hidden,淘宝的做法。
	方法二 直接给font-size:0;看不到文字了
4.最后给链接一个title属性，这样鼠标放在logo上就可以看到提示文字。
```

# 注册页面类名命名

![注册页面专用术语](E:\桌面\html学习\图片笔记\注册页面专用术语.png)

# 2D转换

```css
转换(transform)是css3中颠覆性的特征之一，可以实现元素的位移、旋转、缩放等效果
	移动：translate
	旋转：rotate
	缩放：scale

可以混合写
transform:translate(x,y) rotate(xdeg) scale(x);
顺序最好是先移动，再旋转或者放大缩小
```

## 移动

```css
transform:translate(x,y);
对于原来的位置进行移动
不会影响其它盒子
对于行内盒子无效的

可以将盒子居中对齐
{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
}

```

## 旋转

```css
transform:totate(度数);
度数单位deg
角度为正，顺时针，负时，逆时针
默认旋转中心点，图形中心
```

旋转中心点

```css
transform-origin:x y;
注意x y用空格隔开
xy默认转换的中心点时元素的中心点(50%,50%)
还可以给xy设置像素或者方位名词(top bottom left right center)
```

## 缩放

```css
transform:scale(x,y);
可以写一个参数，相当于x=y
可以写小数相当于缩小
x=y=1相当于不变
可以设置转换中心缩放，且不影响其它盒子
```

# 动画

```css
相比较于过度，动画可以实现更多变化，更多控制，连续自动播放等
用keyframes定义动画(类似于类选择器)

定义动画
/*form 和 to 等价于 0% 100%*/
@keyframes 动画名称{
    0%{
        
    }
    /*(可以设置更多节点)*/
    100%{
    }
}

使用动画
class{
    /*调用动画*/
    animation-name:动画名称;
    /*设置时间*/
    animation-duration:持续时间;
}
```

## 动画属性

![动画属性](E:\桌面\html学习\图片笔记\动画属性.png)

```CSS
animation:动画名称 持续时间 运动曲线 何时开始 播放次数 是否反方向 动画起始或者结束的状态
```

# 3D转换

```css
x轴水平向右	向右是正值
y轴垂直向下	向下是正值
z轴垂直屏幕	向外是正值
```

## 3d位移

```css
translform:translateX(100px)沿着x轴上移
translform:translateY(100px)沿着y轴上移
translform:translateZ(100px)沿着Z轴上移(一般用px单位)-->会使z-index失效
translform:translate3d(x,y,z)
```

## 透视

```css
perspective
在网页中产生3D效果
就是视距，视距就是一个距离人的眼睛到屏幕的距离
透视写在被观察元素的父盒子上面
视距越大，物体越小。视距越小，物体越大
```

## 旋转

```css
需要加上透视
transform:rotateX(50deg);
transform:rotateY(60deg);
transform:rotateZ(60deg);
分别沿着x，y，z轴进行旋转;
transform:rotate3d(x,y,z,deg);



```

## 3d旋转

```css
在父盒子中加入
transform-style:preserve-3d;
可以让子盒子进行3d旋转
选着哪个轴进行旋转可适量叠加，然后再进行角度的改变
backface-visibility:hidden;背景隐藏，在反转背景后，使用背景隐藏比较好
案例

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>反转案例</title>
    <style>
        .box {
            transform-style: preserve-3d;
            position: relative;
            width: 400px;
            height: 400px;
            margin: 300px auto;
            transition: all 0.2s;
        }
        
        .box:hover {
            transform: rotateY(180deg);
        }
        
        .one,
        .two {
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            text-align: center;
            line-height: 400px;
            font-size: 60px;
        }
        
        .one {
            background-color: pink;
            z-index: 2;
            transform: translateZ(1px);
        }
        
        .two {
            background-color: purple;
            transform: rotateY(180deg);
            z-index: 1;
        }
    </style>
</head>

<body>
    <div class="box">

        <div class="one">谷凯辉</div>
        <div class="two">真帅</div>

    </div>
</body>

</html>
```

# 私有前缀

```css
-moz-:代表firefox浏览器私有属性
-ms-:代表ie浏览器私有属性
-webkit-:代表safari、chrome私有属性
-o-:代表Opera私有属性
```

