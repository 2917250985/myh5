# 四、函数

## 1.为什么需要函数

~~~text
函数是被设计为  执行特定任务的  代码快
函数可以把具有相同或相似逻辑的代码“包裹"起来,通过函数调用执行这些被“包裹"的代码逻辑，这么做的优势是有利于精简代码方便复用。
比如我们前面使用的alert()、prompt() 和console.log()都是一些js函数，只不过已经封装好了，我们直接使用的。
~~~

## 2.函数使用

### 2.1 声明函数

~~~javascript
function 函数名(){
	代码快
}
~~~

~~~javascript
//例子
function sayhi(){
	console.log('hello word!!!')
}
~~~

### 2.2 命名规范

~~~text
函数名命名规范
	和变量命名基本一致
	尽量小驼峰式命名法
	前缀应该为动词
	命名建议：常用动词约定
~~~

### 2.3 常见动词

~~~text
can 判断是否可执行某个动作
has	判断是否汉仪某个值
is	判断是否为某个值
get	获取某个值
set	设置某个值
load	加载某些数据
~~~

### 2.4 函数调用

~~~javascript
函数名()
function sayhi(){
	console.log('hello word!!!')
}
sayhi()
~~~

### 2.5 函数的封装

~~~JavaScript
function getsum(){
    let num1 = +prompt('请输入第一个数：')
    let num2 = +prompt('请输入第二个数：')
    alert(`两个数的和为${num1+num2}`)
}
getsum()
~~~

## 3.函数传参

### 3.1 声明语法

~~~JavaScript
//声明一个传参函数时，形参默认值为0，习惯给默认形参赋值 
function 函数名(参数列表){
	代码快
}

~~~

### 3.2 例子

~~~JavaScript
//声明函数的参数为形参
function getsum(num1,num2){
	alert(`两个数的和为${num1+num2}`)
} 
//调用填的的参数为实参
getsum(8,6)


//数组求和    arr = []增加默认值防止报错
function getArrsun(arr = []) {
    let num = 0
    for (let i = 0; i < arr.length; i++) {
        num += arr[i]
    }
    console.log(num);
}
getArrsun([6,8,7,59,6,1,44,55])

//求n~m的累加和   实参可以是变量
function getsum(n=0,m=0){
    let sum = 0
    for(let i=n;i<=m;i++){
        sum+=i
    }
    console.log(sum);
}
getsum(2,8)
~~~



## 4.函数的返回值

### 4.1 概念

~~~text
当调用某个函数，这个函数会返回一个结果出来
这就是有返回值的函数
~~~

### 4.2 声明语法

~~~JavaScript
return 数据
~~~

### 4.3 例子

~~~JavaScript
function fn(){
	return 20
}
console.log(fn()) 
// 求最大值
function getmax(x=1, y=3) {
    return x > y ? x : y
}
let max = getmax(6,8)
console.log(max);
//求数组的最大值
function getArrsun(arr = []) {
    let max = arr[0]
    for (let i = 1; i < arr.length; i++) {
        if(max<arr[i]){
            max = arr[i]
        }
    }
    return max
}
let max = getArrsun([6,8,7,59,6,1,44,55])
console.log(max);
~~~

### 4.4 注意

~~~text
在函数体中使用return关键字能将内部的执行结果交给外部使用
return后面代码不会在被执行，会立即借宿当前函数，所以return后面的数据不会换行写
return函数可以没有return，这种情况默认返回值为  undefined
undefined和任何数，值相加都得    NaN
出现相同的函数名是  后面的函数名会覆盖前面的函数名
~~~

### 4.5 循环与函数的区别

~~~text
break结束的是循环，return结束的是函数
~~~



## 5.作用域

### 5.1 概念

~~~text
通常来说，一段程序代码中所用到的名字并不总是有效和可用的，而限定这个名字的可用性的代码范围就是这个名字的作用域。
作用域分为   全局作用域和局部作用域
~~~

### 5.2 全局作用域和局部作用域的区别

~~~text
全局作用域：作用于所有代码执行的环境(整个script标签内部)或者一个独立的js文件；没有声明的变量默认全局变量
局部作用域：作用于函数内的代码环境，就是局部作用域。因为跟函数有关系，所以也称为函数作用域。
~~~

### 5.3例子

~~~JavaScript
//全局变量  包括外部js文件
let num = 10
console.log(num)
//局部变量
function fun(){
	let num = 10
    console.log(num)
}
fun()
~~~

### 5.4 访问原则

~~~text
原则：就近原则   在能够访问到的情况下先局部，局部没有在找全局
~~~

## 6.匿名函数

### 6.1  理念

~~~text
将匿名函数赋值给-一个变量,并且通过变量名称进行调用我们将这个称为   函数表达式
立即执行函数
~~~



### 6.2 函数表达式

~~~JavaScript
let fn = function(){
    //函数体
}
//立即执行函数体   必须加分号  防止变量污染
(function(){
   //代码块
})();
(function(){}());
~~~

### 6.3  函数表达式 和具名函数的区别

~~~text
具名函数的调用可以写到任何位置
函数表达式，必须先声明函数表达式，后调用
~~~



### 6.4  例子

~~~JavaScript
let fn = function (x,y){
    console.log(x+y)
}
fn(1,2)
//立即执行函数
(function(x,y){
   console.log(x+y)
})(1,2);
//时钟案例
// 用户输入
let second = +prompt('请输入秒数：')
//封装函数
function getTime(t) {
    //num = num < 10 ?  '0' + num : num
    h = parseInt(t / 60 / 60 % 24)
    m = parseInt(t / 60 % 60)
    s = parseInt(t % 60)
    h = h < 10 ? '0' + h : h
    m = m < 10 ? '0' + m : m
    s = s < 10 ? '0' + s : s
    console.log(h + ':' + m + ':' + s);
}
getTime(second)
~~~

# 7.逻辑中断

~~~text
逻辑运算符的断路
断路：只存在于&&和||中，当满足一定条件啊会让右边代码不执行
&&  左边为FALSE就断路		一假则假	console.log(false && age)  两者后面代码皆不执行
||  左边为TRUE就断路		一真则真	console.log(true || age)
原因:通过左边能得到整个式子的结果,因此没必要再判断右边
运算结果:无论&&还是|，运算结果都是最后被执行的表达式值，-般用在变量赋值


~~~

例子

~~~JavaScript

function fn(x,y){
    x  = x || 0
    y  = y || 0
    console.log(x+y);
}
fn()
0
~~~

# 8.转换布尔型

boolean转换布尔型

~~~text
记忆：0，undefined，null，FALSE，NaN 转换为布尔值后都为FALSE  其余为TRUE
~~~

隐式转换

~~~text
有字符串的加法""+1,结果是"1"    ""-1  NaN
减去-（想大多数数学运算一样）只能用于数字，他会是空字符""转换为0
null经过数字转换之后会变成0
undefined经过数字转换之后会变成NaN
null=undefined   0
~~~



