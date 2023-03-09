# 三.数组

## 1.创建数组

~~~javascript
let arr_2 = ['red','gree','pink']
~~~

### 1.1 增

~~~javascript
arr_2.push('blue')
~~~

### 1.2 删

~~~javascript
arr_2.pop()  //删除最后面的一个元素
arr_2.shift()	//删除第一个元素
arr_2.splice(起始位置,删除个数元素)	//删除第一个元素
~~~

### 1.3 改

~~~javascript
arr_2[0]="blue2"
~~~

### 1.4 查

~~~javascript
arr_2[下标数]
~~~

## 2.冒泡排序

~~~javascript
let arr = [96,6,89,36,45,85,26]
for(let i=0;i<arr.length-1;i++){
    for(let j=0;j<arr.length-i-1;j++){
       //比较两个数的大小
        if(arr[j]>arr[j+1]){
             // 交换位置
            let temp = arr[j]
            arr[j]=arr[j+1]
            arr[j+1]=temp
        }
    }
}
console.log(arr);
~~~

## 3 for循环

### 3.1 语法

~~~JavaScript
for(初始值;条件;变化量){
	执行的代码块
}
~~~

### 3.2 for循环的基本使用

#### 求奇数、偶数的和

~~~JavaScript
let sum = 0
let sum2 = 0
for (let i = 1; i <= 100; i++) {
    if (i % 2 === 0) {
        sum = sum + i
    } else {
        sum2 = sum2 + i
    }
}
document.write(sum + sum2)
~~~

#### 求最大值、最小值

~~~javascript
// 求数组最大值
let arr_a = [66, 55, 8, 9, 3, 69, 89]
let max = 0
let min = 0
for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr_a.length; j++) {
        if (arr_a[i] < arr_a[j]) {
            max = arr_a[j]
        }
        else {
            min = arr_a[i]
        }
    }

}
document.write(max, '\n', min)
~~~

#### 九九乘法表

~~~JavaScript
// 正排
// 外面控制行
for (let i = 1; i <= 9; i++) {
    // 里面控制列 
    for (let j = 1; j <= i; j++) {

        document.write(j + '*' + i + '=' + i * j, '\n')

    }
    document.write('<br>')
}
document.write('<br>')
// 到排
for (let i = 9; 1 <= i; i--) {
    for (let j = 1; j <= i; j++) {

        document.write(i + '*' + j + '=' + i * j, '\n')

    }
    document.write('<br>')
}
~~~

