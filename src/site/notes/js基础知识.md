---
{"dg-publish":true,"dg-js":true,"permalink":"/js基础知识/","dgPassFrontmatter":true}
---


## 函数基础


函数基础是  可以直接理解为 变量 =  值
```js

  
// 函数声明      foo是函数的预编译(运行)   {是代码块} 
function foo(){  
    // 标识语句体  
	console.log("foo功能")  
}  
//函数调用 
foo()   // 输出:foo功能

function add(x,y){  
    console.log(x+y)}  
add(1,2)  
add(1,2,3)  
// add(1,)  //  NaN
```
![NaNnan](https://gitlab.com/minika1/Pic/-/raw/main/pictures/2024/04/16_15_42_3_NaN.png)NaN可以理解为变量没有存储它吗
```js
function add2(x,y,z){  
    console.log(x+y+z)}  
add2(1,2,)  //  NaN

// arguments 是为了解决变量没有值   只有变量没有赋值
function add2(){  
    // 函数中 arguments 是代表函数实参传进过来所组成的一个数组  
    // console.log(arguments)  
    let ret = 0  
    for(let i = 0;i<arguments.length;i++){  
       ret += arguments[i]  
    }  
    return ret  
}  
  
console.log(add2(1,2,3,4,5,6,7,1000))



```
## 函数作于域

函数的作用域是指函数可以访问的变量和函数的范围。 

在通俗一点，函数的作用域可以理解为函数可以管得着的地方。
[[函数作于域\|函数作于域]]

>函数本身就是一个变量赋值的问题

x =1   ,跟python一样就是把一存起来  

1. Local Scope（局部作用域）：这是在函数内部声明的变量和函数的作用域。局部作用域内的变量和函数只能在声明它们的函数内被访问。例如：

```js
# 什么是作用域：变量的生命周期(存活阶段)
# python中函数、类可以独立划分作用域
# 作用域：L(local) E(enclosing) G (global) B (built-in)
L:本作用域 E：循环嵌套的外部作用域 G：全局域
 

 
```





## 函数闭包

### [闭包](https://kaxiu808.github.io/#/js/base/3.%20js%E4%BD%9C%E4%BA%8E%E5%9F%9F?id=%e9%97%ad%e5%8c%85)

闭包是指有权访问另一个函数作用域中变量的函数。创建闭包的常见方式，就是在一个函数内部创建另一个函数，并通过后者。访问 在计算机科学中，闭包（英语：Closure），又称词法闭包（Lexical Closure）或函数闭包（function closures），是引用了自由变量（外部非全局）的函数

简单来说就是一个函数定义中引用了函数外定义的变量，并且该函数可以在其定义环境外被执行。这样的一个函数我们称之为闭包函数。

```html
<script>
let count = 0
 function counter(){
	 count++ // count=count+1
	 return count
	 }

	counter()
</script>
```

```html
<!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <title>Title</title>  
</head>  
<body>  
<script>  
    function getCounter(){  
  
        // 计数器  
        var aaa = "123"  
        var count =0  
        function counter(){  
        count++  
        console.log(count)  
        return count  
    }  
  
    // counter()  
    // counter()   
    // counter()   
    // counter()        
		    // 如果要外部进行调用counter,需要return  
        return counter  //把局部变量，交给外部全局去使用  
    }  
   counter= getCounter()  
    // counter()  
  
</script>  
<script>  
    var count = 1000  
  
    // js代码2  
</script>  
<script>  
    // js代码3  
</script>  
  
</body>  
<button onclick="counter()">click</button>  
</html>
```



## ES6中的箭头函数

```js
//es6允许使用"箭头"（=>）定义函数。
var f = v => v*y
//等同于
var f =function(v){
 return v
}
//如果箭头函数不需要参数或需要多个参数，就使用一个圆括号代表参数部分。
var f =()=>5
//等同于
var f= functipn(
	return 5
)

var sum =(num1，num2) => num1+num2
//等同于
var sum=function(num1，num2){
	return num1+num2
}

//如果箭头函数的代码块部分多于一条语句，就要使用大括号将它们括起来，并且使用return语句返回。
var sum=(num1,num2)=>{return num1+num2}
//由于大括号被解释为代码块，所以如果箭头函数直接返回一个对象，必须在对象外面加上括号，否则会报错。 
//报错
let getUser=id=>{id:id,name:yuan"}
//不报错
let getUser=id=>{{id:id,name:"yuan"}}

//箭头函数的一个用处是简化回调函数。
//正常函数写法
[1,2,3].map(function(x){
returnx*x
})
//箭头函数写法
[1,2,3].map(x=>×*x)
```


## exports

```js
//functions.js

//加法函数
function add(a,b){
	return a +b;
}
//乘法函数
function multiply(a,b){
	return a *b;
}
//导出函数
exports.add=add;
exports.multiply = multiply;
// exports :func
```

```js
//main.js

//导入functions模块
const functions=require('./functions');
//使用导入的函数
console.log(functions.add(2，3));//输出：5
console.log(functions.multiply(4，5));//输出：20
```


## window对象

### 全局作于域

window对象定义了3个人机交互的方法，主要方便对JavaScript代码进行调试。

- alert()：确定提示框。由浏览器向用户弹出提示性信息。该方法包含一个可选的提示信息参数。如果没有指定参数，则弹出一个空的对话框。

- confirm()：选择提示框。。由浏览器向用户弹出提示性信息，弹出的对话框中包含两个按钮，分别表示“确定”和“取消"按钮。如果点击“确定”按钮，则该方法将返回true；单击"取消"按钮，则返回false。confirm()方法也包含一个可选的提示信息参数，如果没有指定参数，则弹出一个空的对话框。
 
- prompt()：输入提示框。可以接收用户输入的信息，并返回输入的信息。prompt()方法也包含一个可选的提示信息参数，如果没有指定参数，则弹出一个没有提示信息的输入文本对话框。


### 访问客户端对象

便用window对象可以访问客户端其他对象，这种关系构成浏览器对象模型，window对象代表根节点，浏览器对象关系的关系如图所示，每个对象说明如下。 
 
 - window：客户端JavaScript顶层对象。每当<body>或<frameset>标签出现时， window对象就会被自动创建。
-   navigator：包含客户端有关浏览器信息。
- screen：包含客户端屏幕的信息。
-  history：包含浏览器窗口访问过的URL信息。
- location：包含当前网页文档的URL信息，
-  document：包含整个HTML文档，可被用来访问文档内容及其所有页面元素。
