# JavaScript语言学习心得

> JavaScript（简称“JS”） 是一种具有函数优先的轻量级，解释型或即时编译型的[编程语言](https://baike.baidu.com/item/编程语言/9845131)。虽然它是作为开发[Web](https://baike.baidu.com/item/Web/150564)页面的[脚本语言](https://baike.baidu.com/item/脚本语言/1379708)而出名，但是它也被用到了很多非[浏览器](https://baike.baidu.com/item/浏览器/213911)环境中，JavaScript 基于原型编程、多范式的动态脚本语言，并且支持[面向对象](https://baike.baidu.com/item/面向对象/2262089)、命令式、声明式、[函数](https://baike.baidu.com/item/函数/301912)式编程范式。 [1] 
>
> JavaScript在1995年由[Netscape](https://baike.baidu.com/item/Netscape/2778944)公司的Brendan Eich，在网景导航者浏览器上首次设计实现而成。因为Netscape与[Sun](https://baike.baidu.com/item/Sun/69463)合作，Netscape管理层希望它外观看起来像Java，因此取名为JavaScript。但实际上它的语法风格与[Self](https://baike.baidu.com/item/Self/4959923)及[Scheme](https://baike.baidu.com/item/Scheme/8379129)较为接近。
>
> 

## 学习难度

在有c语言基础上学习 我认为可以它的大体风格和c语言有相似的地方，因此在学习js时我更加的游刃有余 相比较于c语言，js作为脚本语言更加的方便，比如在定义变量时，js而可以通过你的值 自动转换数据类型，这一点我觉得很方便。只要举一反三 在js的学习上难度不太大 。

## 语言特点

(1)[脚本语言](https://baike.baidu.com/item/脚本语言)。JavaScript是一种解释型的脚本语言，C、[C++](https://baike.baidu.com/item/C%2B%2B)等语言先[编译](https://baike.baidu.com/item/编译)后执行，而JavaScript是在程序的运行过程中逐行进行解释。

(2)基于对象。JavaScript是一种基于对象的脚本语言，它不仅可以创建对象，也能使用现有的对象。

(3)简单。JavaScript语言中采用的是弱类型的变量类型，对使用的数据类型未做出严格的要求，是基于Java基本语句和控制的脚本语言，其设计简单紧凑。

(4)动态性。JavaScript是一种采用事件驱动的脚本语言，它不需要经过Web服务器就可以对用户的输入做出响应。在访问一个网页时，鼠标在网页中进行鼠标点击或上下移、窗口移动等操作JavaScript都可直接对这些事件给出相应的响应。

(5)跨平台性。JavaScript脚本语言不依赖于操作系统，仅需要浏览器的支持

<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
<script>
function displayDate(){
	document.getElementById("demo").innerHTML=Date();
}
</script>
</head>
<body>
制作一个js小程序

<button type="button" onclick="displayDate()">显示日期</button>

## 对象

基于对象 是js的一个语言特点，在 JavaScript中，几乎所有的事物都是对象。

## 创建对象

在javascript中，创建对象有两种方式，一种是使用 new 操作符后跟 Object 构造函数:

```text
let ob = new Object();
ob.name = 'object';
```

另一种是直接使用对象字面值:

```text
let ob = {
      name: 'object'
    };
```

在对象这一部分我不太理解  之后会专门学习一下

## css HTML javascript之间的关系

**“HTML是网页的结构，CSS是网页的外观，而JavaScript是页面的行为。”**

**在网中html定义网页的结构       相当于人的骨骼与器官**

​      **css描述网页的样子       相当于人的皮肤**

   **html+css即（骨骼、器官）+（皮肤）=植物人**

   **html+css+js，人！可以对外界刺激做出响应，可以思考，可以运动，可以化妆（改变css）**

```html

```

