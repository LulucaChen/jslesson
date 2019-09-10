# 变量类型和计算

## 值类型和引用类型（对象数组和函数）

值类型不会相互干预

### type of  输出类型6种

只区分前四种值类型，引用类型除了function都是object

- undefined
- string
- number
- boolean
- object
- function

### 强制类型转换

1. 字符串拼接

   0==‘’  true

2. if 里面是布尔类型

### 三等=== 与== 的区别（面试会考）

怎么看属性存在

```js
var obj ={}
if(obj.a == null){}
```



### JS 的内置函数

- Object
- Array
- Boolean
- Number
- String
- Function
- Date
- RegExp
- Error
- math(对象)

### js 按照存储方式区分类型

### 如何理解json 是个对象（也是一个数据结构）

if(0),if(false) if(NaN) if('') if(null) if (undefined) 都是false

## 原型和原型链

#### 构造函数

1. 默认return this

   ```js
   var a = new Object()
   ```

2. 构造函数名首字母大写
3. 使用instanceof判断一个函数是否是一个变量的构造函数

#### 原型规则和实例

所有的引用类型，都具有对象特性，即自由扩展属性，函数也有自由扩展属性

所有引用类型，都有_proto_属性，隐式原型

所有函数，都有一个prototype属性，显示原型

所有的引用类型，隐式原型属性值指向构造函数的显示原型？？？

当试图得到一个对象的某个属性是，如果这个对象本身没有这个属性，那么会去他的_proto_ 中寻找

hasOwnProperty属性判断是否来自原型的属性

### 面试题

- 判断一个变量是否是数组
- 写一个原型链继承的例子
- zepto 源码中如何使用原型链
- 阅读源码是高效提高技能的方式

### 函数声明（提前）

函数声明与变量声明是一样的,先声明变量

```js
var h =1
```

var h 此时h = undefined ,然后h =1

```js
var h = function(){}
```

### 变量提升

- 执行上下文
  	- 范围：一段<script>或者一个函数
  	- 全局：变量定义、函数声明
  	- 函数：变量定义、函数声明、this、argument
  	- this 和argument提前声明？？？
- this 要在执行的时候才确认值，定义时无法确认
  - 作为构造函数执行
  - 作为对象属性执行
  - 作为普通函数执行 this === window
  - call apply blind(.blind 必须用函数表达式)
- 作用域
  - 没有块级作用域（var 块里面和外面是一样的）
  - 函数和全局作用域
  - 自由变量（当前作业域没有定义）
- 作用域链（父作用域是定义的时候的作用域，不是执行的时候的作用域）
- 闭包
  	- 函数作为返回值
  	- 函数作为参数传递

## 同步和异步的区别是什么

- 同步和异步的区别？分别举一个例子

- settimeout 的笔试题

- 前端使用异步的场景有哪些？

  #### 知识点

  - 什么是异步
  - 前端使用异步的场景
  - 异步和单线程 

## jswebAPI

- w3c标准并没有规定任何js基础相关的东西

- 不管变量类型、原型、作用域和异步（ecmi管）

- 只管定义用于 浏览器操作页面的 api 和全局变量

- 全面考虑，js内置的全局函数和对象有哪些？

- object array Boolean string math json

- window document

- 未定义的全局变量，navigator.userAgent

  ### 常说的js包含两部分

  - js基础知识（ecma262标准）
  - js-web-api(w3c标准)

  ### Dom操作

  文档 对象 模型 document object model

  - Dom 是哪种基本的数据结构（树）
  - Dom 操作的常用API有哪些
  - Dom 节点的attr 和property 有什么区别

  dom 节点操作

  - 获取dom节点
  - property 有关js的
  - attribute 有关文档的

  ### bom操作

  - 如何检测浏览器的类型
  - 解析url的各部分

  - 知识点：
    - navigator判断浏览器
    - screen
    - location & history
  
  ## 事件
  
  - 通用事件绑定
  -  事件冒泡 会往上触发
  
  ### 面试题
  
  - 编写一个通用的事件监听函数
  - 描述事件冒泡流程
  - 对于一个无线下拉加载图片的页面，如何给每个图片绑定事件（!使用代理）
  - 简述事件冒泡流程
    	- Dom树形结构
    	- 冒泡的应用
    	- 阻止冒泡
  
  - 代理的优点：1.代码简洁 2. 给浏览器压力小
  
  ## Ajax
  
  ### 题目
  
  - 手动编写一个 ajax ，不依赖第三方库
  - 跨域的几种实现方式（不同产品的跨域实现方式不一样、前端的域名和服务端的域名不一样）
  - 跨域的原理是什么
  
  ### 知识点
  
  - XMLHttpRequest
  - 状态码说明
  - 跨域
  
  ### readyState
  
  - 0 -（未初始化）还没有调用send（）方法
  - 1 - (载入) 已调用send（）方法，正在发送请求
  - 2 - （载入完成）send()方法执行完成，已经接受到全部响应内容
  - 3 - （交互）正在解析响应内容
  - 4 - （完成）响应内容解析完成，可以在客户端调用了
  
  ### status
  
  - 2xx - 表示成功处理请求。如200
  - 3xx - 需要重定向，浏览器直接跳转
  - 4xx - 客户端请求错误，如404
  - 5xx - 服务端错误

