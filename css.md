# 视频内容

## HTML 基本属性

### 表格属性

1. table  行列属性 

   - tr 行
   - td 列
   - th 标题，包含在tr标签中

2. form  target 表单提交到哪里，method 用get 或post 提交 ，   enc-type 是en code type ???讲的什么狗屁听不懂

   - target 规定在哪里打开url

   - method: get  会让 url 和数据以？分开 例如

     ```html
     http://www.example.com/example/program?x=28&y=66
     ```

   - method: post 浏览器会先跟指定的表单处理服务器建立联系，再分段发送给服务器

3. input  name 单选框 复选框

   id 最好不要包含下划线，css不兼容

   type 规定文本复选密码按钮等

   只有设置了 name 属性的表单元素才能在提交表单时传递它们的值

4. button

5. select 下拉框跟option selected 选中

   value 是提交给服务器的值

6. label 跟表单项相关联 for 

7. submit 和reset 都是在表单中才有意义

### 如何理解HTML

h5o chrome 插件

### HTML版本

- HTML 4/ 基于标记语言 SGML 写的 浏览器需要作非常多容错
- HTML 5 不要求所有属性都有值 属性不用带引号，属性可以大写
- HTML 4  XHTML 所有页面都需要验证

#### HTML 新增内容

- 新区块标签
  - section
  - article
  - nav
  - aside

- 表单增强
  - 日期、时间、搜索
  - 表单验证
  - placeholder自动聚焦

- 新增语义
  - header/footer 一个完整的页面或者article中可以用
  - section /article 区域 article更完整一些
  - nav 导航
  - aside 不重要的内容（友情链接）
  - em/strong 强调 斜体/粗体
  - i icon 做图标，曾经有斜体的意思？

HTML 元素分类

- 按默认样式分
  - 块级元素 block 一整行 不给其他元素留空间
  - 行内元素 inline 未必有规则形状
  - inline-block  例如表单元素 select

- 按内容分？？？

### HTML元素嵌套关系

- 块级元素可以包含行内元素
- 块级元素不一定能包含块级元素
- 行内元素一般不一定能包含块级元素
- a>div 是合法的 a是一个transparent元素，即相当于body里是一个div元素

HTML 元素默认样式的意义

- 默认样式 （不只是从body开始的）
- CSS Reset 

HTML 面试真题

- doctype的意义 知道元素的合法性 让浏览器以标准模式渲染 让浏览器
- HTML XHTML HTML5的关系
  - HTML属于SGML
  - XHTML属于XML，是HTML进行XML严格化的结果
  - HTML5 不属于SGML　或XML，比XHTML宽松

- HTML5有什么变化
  	- 新的语义化元素
  	- 表单增强
  	- 新的API（离线、音视频、图形、实时通信、本地存储、设备能力）
  	- 分类和嵌套变更

- em和i有什么区别
- 语义化的意义是什么
  	- 开发者容易理解
  	- 机器容易理解结构（搜索、读屏软件）
  	- 有助于SEO
  	- semantic microdata

- 哪些元素可以自闭合
  - 表单元素input
  - 图片img
  -  br hr
  - meta link

- HTML 和DOM的关系
  	- HTML是‘死’的
  	- DOM由HTML解析而来，是活的
  	- JS可以维护DOM

- property 和attribute的区别(是不同步的，互不影响)
  	- attribute 是死的
  	- property 是活的

- form 的作用有哪些
  	- 直接提交表单
  	- 使用submit/reset按钮
  	- 便于浏览器保存表单
  	- 第三方库可以整体提取值
  	- 第三方库可以进行表单验证

## CSS基础（层叠样式表）

​	权重 id>class>div

### 选择器

浏览器的解析方式从右往左，往左是验证过程，是出于性能的考虑

- 元素选择器 
- 类选择器.link{}
- 属性选择器[type=radio]{}

- 伪元素选择器（真实存在的元素）：：before{}
- 伪类选择器（伪类 是一个元素的状态）：hover{}
- 组合选择器
- 。。。

### 选择器权重（权重不进位）

id+100    类 伪类 属性 +10 元素 伪元素 +1 其他选择器+0

- ！important 优先级最高
- 元素属性比写到外部样式表高
- 相同权重 后写的生效

### 非布局样式

- 字体族（适应平台）
  - 字体周围有装饰性 没有装饰性（宋体）
  - 等宽字体
  - 花体
- 多字体fallback  ‘陈璐’的璐找不到相应字体，就用别的字体
- 网络字体、自定义字体（url 可以使用远程字体，需要对方服务器允许跨域，也可以通过引用远程css）
- icon font 自定义字体
- 行高的构成(面试常考)

  - baseline 跟底线有距离

  - vertical-align bottom
- 背景
  	- hsl (饱和度)对人眼更友好 rgb(,,,透明度)
  	- 线性渐变（渐变角度）
  	- 可叠加（面试会考）
  	- 背景图片属性（雪碧图减小HTTP请求）
  	- base64 ？？？传输性能优化，用在小图标的传输
  	- 多分辨率适配

	- 边框
	- 三角形边框实现（面试会考）
 - 滚动
   - visible
   - hidden
   - scroll
   - auto
- 文字折行（会考怎么样不换行）
   - overflow-wrap 通用换行控制
     - 是否保留单词
  	- word-break 针对多字节文字，单词可以不是一个单位，设置单位是句子还是单词
   - white-space ：nowrap  不换行
- 装饰性属性
  	- 字重 font-weight 数字表示只能是100的倍数，但是并不一定会支持

### 行高

#### 行高的构成 

由line-box组成

会撑起 inline-box 的高度

垂直居中可以用line-height

vertical-align 顶线对其，并不是文字的顶部

默认baseline对齐，baseline对齐跟底线对齐不一样

#### 行高相关的现象和方案

#### 行高的调整

### 背景

#### 背景颜色

#### 渐变色背景 

line-gradient 线性渐变，可以添加渐变角度，位置颜色，可以画条绿线																																																																																																																																																																																																																																																																																																																																																																																														

#### 多背景叠加

#### 雪碧图（减少http请求）

#### base64性能优化

减少httP请求，增大css文件，增大图片体积。

### 边框

### 常用布局方法

- table表格布局
- float 浮动+ margin
- inline-block 布局
  - inline 元素没有宽高 ，inline-block 可以对齐
  - relative 偏移是相对于元素本身来说，所占空间并不改变计算
  - absolute 是一个独立的存在，不会对其他元素造成影响，相对于最近的absolute父级定位，如果没有找到，就是body
  - z-index 覆盖级别 relative absolute fixed

- 弹性盒子flexbox

- float

  	- 脱离文档流
  	- 不脱离文本流
  	- 对自身的影响（形成“”块，可以设置宽高）
  	- 位置尽量靠左，尽量靠上
   - 对兄弟的影响
     - 上面贴非float元素
     - 旁边贴float元素
     - 不影响其他块级元素位置
     - 影响其他块级元素位置

  - 对父级元素的影响
    - 从布局上消失

  - 清楚浮动的方式

- inline-block
  - 像文本一样
  - 可以想象成文字，所以会有间隙，可以将字体大小设为0

### 响应式设计和布局

- 主要方法：

   - rem/viewport/media query

     ​	width =device-width 适配移动端 可视区域等于。。。。

     ​	固定使用width 可以使得等比例适配

  	- 隐藏+折行+自适应空间

### css效果属性

- box-shadow
- text-shadow
  	
  	- 立体感
  	- 印刷体

- border-radius 

  ### backgroud

  雪碧图

  动态显示

  clip-path 支持动画 对容器进行裁剪 常见几何图形

  svg

### 3D变换

- 变换 transform

  - translateX ,translateY ,translateZ
  - rotate
  - ...

###  css动画

- transition 补间动画 delay  动画延迟 支持多个属性同时变动

  会设计到timing （easing）

- 关键帧动画 要求元素状态变换，关键帧元素本身没有变换，可以直接指定动画
- 逐帧动画 steps

## css预处理器（css嵌套）？怎么编译还没试过

- 基于css的另一种语言
- 通过工具编译成css
- 添加了很多css不具备的特性
- 能提升css的性能
- less基于node写的  编译速度更快 入门更简单
- sass用ruby 写的

### 预处理器

- 嵌套 反映层级和约束
- 变量和计算 减少重复代码
- extend 和mixin代码片段
- 循环 适用于复杂有规律的样式
- import css文件模块化

