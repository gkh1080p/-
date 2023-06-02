# Less

```css
Less是一门css扩展语言，也成为css预处理器。
作为css的一种形式扩展，它并没有减少css的功能，而是在css语法上，为css加入程序式语言的特性
引入变量,Mixin,运算以及函数等功能，大大简化的css编写，并且降低了css维护成本
Less中文网站：http://lesscss.cn/
常见的css预处理器：Sass、Less、Stylus
```

## Less变量

```less
@变量名:值;
规范
1.必须以@为前缀
2.不能包含特殊字符
3.不能以数字开头
4.大小写铭感
```

## 编译

```css
要把less文件编译成css文件
通过VScode插件easy Less来编译
```

## 嵌套

```less
less允许嵌套
.box1{
	width:200px
	height:200px
	a{
		color:#fff
	}
}
a标签里面的文字都为#fff色
有&符号时相当于并连接
没有&相当于子元素
```

## 运算

```less
可以在less文件中通过 + - * / 等运算来实现
如width:20px+20;	是将原有的基础上加20px
除法要加括号
(运算符要加空格)
两个数参与运算，单位以第一个为准
```

## 导入css中

```less
@import "common";
    common为要导入的less文件
```

