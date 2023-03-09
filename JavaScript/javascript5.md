# 五、对象

## 1. 什么是对象

~~~text
 对象：JavaScript里的一种数据类型      字典
~~~

### 1.1 特点

~~~text
无序的数据的集合
可以详细的描述某个事物
~~~

## 2.  对象的使用

### 2.1 声明语法

~~~JavaScript
let 对象名 = {}
let 对象名 = new Object()

let object = {
	属性名:属性值,
	方法名:函数
}
~~~

### 2.2 对象组成

~~~javascript
属性：信息或叫特征（名字） 例如 手机尺寸 颜色 重量 等
方法：功能或叫行为（动词） 例如 手机打电话 发短信 玩游戏
/*
let object = {
	属性名:属性值,
	方法名:函数
}
*/

➢属性都是成对出现的，包括属性名和值，它们之间使用英文:分隔
➢多个属性之间使用英文,分隔
➢属性就是依附在对象上的变量(外面是变量,对象内是属性)
➢属性名可以使用”或"，一般情况下省略，除非名称遇到特殊符号如空格、中横线等

检测类型  typeOf
~~~

### 2.3 对象的增   删    改   查

~~~JavaScript
/*
查：对象名.属性
改：对象.属性 = 值
增：对象名.新属性名 = 值
删：delete 对象名.属性名
*/
~~~

### 2.4 例子

~~~JavaScript
let goods = {
        name : '小米10 青春版',
        num:100012816024,
        weight:'0.55kg',
        address:'中国大陆'
    }
//查
console.log(goods.name);
console.log(goods['name']);
//改
goods.name = '红米k40s'
console.log(goods);
//删
delete goods.weight
console.log(goods);
//增
goods.price = 2399
console.log(goods);



/*
查的两种用法的区别：
1.方式：
点形式		对象.属性
[]形式	 对象['属性']
2.区别：
点后面的属性名一定不要假双引号
[]里面的属性名一定假双引号
后期不同使用场景会用不同的写法
~~~

### 2.5 对象中的方法

~~~JavaScript
let object = {
    uname:'pink',
    //方法    与函数类似
    song:function(){
	 console.log(666)
    }
}
~~~

## 3.  遍历对象

###  3.1 对象的使用方法

~~~JavaScript
let goods = {
    name : '小米10 青春版',
    num:100012816024,
    weight:'0.55kg',
    address:'中国大陆'
}
for(let k in goods){
    console.log(k);  //打印属性名
    console.log(goods[k]);  //取值
}
~~~

### 3.2 学生管理系统案例

~~~JavaScript
let students = [
    {
        name: '小明',
        age: 18,
        sex: '男',
        address: '河北'
    },
    {
        name: '小红',
        age: 19,
        sex: '女',
        address: '河男'
    },
    {
        name: '小刚',
        age: 20,
        sex: '男',
        address: '山西'
    },
    {
        name: '小水',
        age: 21,
        sex: '男',
        address: '广西'
    }
]
for(let i = 0; i<students.lenght; i++){
	//打印索引号
    console.log(i)
   	//每个对象
    console.log(students[i])
    //打印对象的值
    console.log(students[i].name)
    console.log(students[i]['name'])
    
}
~~~

### 3.3 渲染页面

样式

~~~css
table {
    width: 600px;
    text-align: center0;
}

table,
th,
td {
    border: 1px solid #ccc;
    border-collapse: collapse;
}

caption {
    font-size: 18px;
    margin-botton: 10px;
    font-weight: 700;
}

tr {
    height: 40px;
    /* 光标的类型 */
    cursor: pointer;
}

table tr:nth-child(1) {
    background-color: #ddd;
}

table tr:not(:first-child):hover {
    background-color: #ddd;
}
~~~

html标签

~~~html
<table>
    <caption>学生列表</caption>
    <tr>
        <th>序号</th>
        <th>姓名</th>
        <th>年龄</th>
        <th>性别</th>
        <th>家乡</th>
    </tr>
</table>
~~~

JavaScript数据

~~~JavaScript
let students = [
    {
        name: '小明',
        age: 18,
        sex: '男',
        address: '河北'
    },
    {
        name: '小红',
        age: 19,
        sex: '女',
        address: '河男'
    },
    {
        name: '小刚',
        age: 20,
        sex: '男',
        address: '山西'
    },
    {
        name: '小水',
        age: 21,
        sex: '男',
        address: '广西'
    }
]
//渲染页面
for (let i = 0; i < students.length; i++) {
    document.write(`
    <tr>
        <th>${i+1}</th>
        <th>${students[i].name}</th>
        <th>${students[i].age}</th>
        <th>${students[i].sex}</th>
        <th>${students[i].address}</th>
    </tr>
    `)
}
~~~

## 4. 内置对象

### 4.1  math数学对象

~~~JavaScript
介绍：Math对象是JavaScript提供的一个“数学”对象
作用：提供一系列做数学运算的方法
Math对象包含的方法：
/*
random：生成0-1之间的随机数（包括0不包括1）
ceil:向上取整
floor：向下取整
max：找最大值
min：找最想值
pow:幂运算
ads:绝对值 
round：四舍五入
~~~

### 4.2 例子

~~~JavaScript
// ceil向上取整
console.log(Math.ceil(1.1)); //2
console.log(Math.ceil(1.5)); //2
console.log(Math.ceil(1.9)); //2
// floor 向下取整  
console.log(Math.floor(1.1)); //1
console.log(Math.floor(1.5)); //1
console.log(Math.floor(1.9)); //1
//round 四舍五入
console.log(Math.round(1.1)); //1
console.log(Math.round(1.5)); //2
console.log(Math.round(1.9)); //2
console.log(Math.round(-1.1));//-1
console.log(Math.round(-1.51));//-2
//取整函数
console.log(parseInt('12px'));//12
//最大，最小值
console.log(Math.max(1,2,3,4,5,6));//6
console.log(Math.min(1,2,3,4,5,6));//1
~~~

### 4.3  生成任意范围随机数

  ~~~JavaScript
  //Math.random()随机数函数，返回一个0- 1之间，并且包括0不包括1的随机小数[0, 1)
  随机列表取值
  let arr = ['red','green','blue']
  let random_1 = Math.floor(Math.random()*arr.lenght)
  console.log(random_1)
  ~~~

### 4.4 经典随机数写法

~~~JavaScript
//1.如何生成0-10的随机数
Math.random()*(10+1)
//2.如何生成5-10的随机数
Math.random()*(5+1)+5
//3.如何生成N-M的随机数
Math.random()*(M-N+1)+N
~~~

## 5 随机点名案例

~~~JavaScript
//请把['赵云'，'黄忠'，'关羽'，'马超'，'张飞'，'刘备'，'曹操']
//1.得到一个随机数，并作为索引号，这个随机数0~6
let arr = ['赵云', '黄忠', '关羽', '马超', '张飞', '刘备', '曹操']
let random3 = Math.floor(Math.random() * arr.length)
document.write(arr[random3])
// splice(起始位置(下标), 删除几个元素)
arr.splice(random3,1)
document.write(arr)
~~~

## 6.猜数字游戏

~~~JavaScript
/*程序随机生成1-10之间的一个数字，用户输入一个数字
1.如果大叔该数字，就提示，数字猜大了，继续猜
2.如果大叔该数字，就提示，数字猜小了，继续猜
3.如果猜对了，就提示猜对了，程序结束
*/
function getRandom(N, M) {
    return Math.floor(Math.random() * (M - N + 1)) + N
}
let random = getRandom(1, 10)
document.write(random)
while (true) {
    
    let num = +prompt('请输入你猜的数字：')
    if (num > random) {
        alert('你猜大了')
    }
    else if (num < random) {
        alert('你猜小了')
    }
    else {
        alert('你猜对了')
        break
    }
}
~~~

