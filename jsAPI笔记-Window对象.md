# BOM

```js
BOM包含DOM
BOM是浏览器对象模型
是最大的对象
所有通过var定义在全局作用域中的变量，函数都会变成window对象的属性或者方法
```

# 定时器-延时函数

```js
setTimeout(回调函数，等待的毫秒数)
只执行一次

//清楚延时函数
let timer=setTimeout(,)
clearTimeout(timer)
```

# js执行机制

```js
js是单线程机制，一次只能执行一个事
"同步任务"
同步任务都是在主线程上执行，形成一个执行栈
"异步任务"
js的异步是通过回调函数执行(耗时的任务，0秒也是耗时)
一般而言，异步任务有以下三种类型:
1.普通事件如click,resize等
2.资源事件如load,error等
3.定时器


///执行机制
1.先执行执行栈中的同步任务
2.异步任务放入任务队列中
3.一旦执行栈中所有的同步任务执行完毕，系统就会按照次序读取"任务队列"重点异步任务,于是被读取的异步任务结束等待状态，进入执行栈，开始执行
```

# location对象（网页跳转）

```js
它拆分并保存了URL地址的各个组成部分

```

## 常用方法与属性

```js
//属性
location.href='...'利用js进行跳转页面
//属性
search属性获取地址中携带的参数，符号?后面部分
location.search
//属性
hash属性获取地址中的哈希值，符号#后面部分
//方法
reload方法用来刷新当前页面，传入参数true时表示强制刷新
location.reload(true)
```

# navigator对象

```js
记录浏览器的自身的相关信息

"通过userAgent检测浏览器的版本及平台"
        !(function () {
            const userAgent = navigator.userAgent
            //验证是否为Android或iPhone
            const android = userAgent.match(/(Android):?[\s\/]+([\d.]+)?/)
            const iphone = userAgent.match(/(iPhone\sOS)\s([\d_ ]+)/)
            //如果是Android或iPhone，则跳转至移动站点
            if (android || iphone) {
                location.href = 'http://m.itcast.cn'
            }
        })()
```

# histroy对象（历史记录）

```js
主要管理历史记录，该对象与浏览器地址栏的前进后退等有关

```

## 属性和方法

```js
//方法
back()可以后退功能
forward()前进一步
go(1)前进
```

# 本地存储

```js
1.数据存储在用户浏览器中
2.设置，读取方便，甚至页面刷新不丢失数据
3.容量较大，sessionStorage和localStorage约5M左右
4.只能存字符串
```

## localStorage操作

```js
//存
localStorage.setItem(键,值)
通过键值对的形式进行存储，需要加引号
在浏览器F12中通过Application来查看
//取
localStorage.getItem(key<键>)
//删
localStorage.removeItem(key<键>)
//改
localStorage.setItem(键,值)
```

## sessionStorage

```
与localStorage操作相似，只是sessionStorage浏览器关闭后会消失
```

## 存储复杂数据类型

```js
"存数据"
解决:需要将复杂数据类型转换成JSON字符串，在存储本地
语法:JSON.stringify(复杂数据类型)
JSON对象 属性和值有引号，而引号统一时双引号
"读数据"
将JSON转换成对象
JSON.parse(json数据类型)d
```

# 正则表达式

```js
用于匹配字符串中字符符合的模式
通常用来查找，替换那些符合正则表达式的文本，许多语言都支持正则表达式
匹配，替换，提取
```

## 语法

```js
//定义规则
const 变量名=/表达式/
//是否匹配
test()方法 用来查看正则表达式与指定的字符串是否匹配
regObj.test(被检测的字符串)	regObj是规则名称
//检索(查找)符合规则的字符串
exce()方法 在一个指定字符串中执行一个搜索匹配
regObj.exec(被检测字符串)
返回一个数组
```

## 元字符

```js
具有一些特殊含义的字符，可以极大提高了灵活性和强大的匹配功能
参考文档
MDN:https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Regular_Expressions
正则测试工具:http://tool.oschina.net/regex

//边界符(表示位置，开头和结尾，必须用什么开头，用什么结尾)
^表示匹配行首的文本(以谁开始)
$表示匹配行尾的文本(以谁结束)
"精确查找"	^<内容>$匹配每一个字

//量词(表示重复次数)
设定某个模式出现次数
*重复0次或者更多次
+重复1次或者更多次
?重复零次或一次
{n}重复n次
{n,}重复n次或更多次
{n,m}重复n到m次

//字符类(比如\d表示0~9)
[]匹配字符集合
[a-z][A-Z]表示26个字母
在[]中加"^"表示取反
"."匹配除换行符之外的任何单个字符
///预定义
\d	-->	[0-9]
\D	-->	[^0-9]所有0-9以外的字符
\w	-->任意字母数字和下划线
\W	-->"除"所有字母数字和下划线
\s	-->匹配空格(包括换行符，制表符，空格符等)相当于[\t\r\n\v\f]
\S	-->"除"空格(包括换行符，制表符，空格符等)相当于[^\t\r\n\v\f]
```

## 修饰符

```js
/表达式/修饰符
i	-->正则匹配时不区分大小写
g	-->匹配所有满足正则表达式的结果
```

## 替换

```js
字符串.replace(/正则表达式/,'替换文本')
```

