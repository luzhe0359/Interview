# html篇

> <font size=6>html - 面试知识点</font>

## HTML5语义化

即合理、正确的标签来展示内容，比如h1~h6定义标题，header、footer定义页面头部、底部。

**优点**

- 易于用户阅读，样式丢失的时候能让页面呈现清晰的结构。

- 有利于SEO，搜索引擎根据标签来确定上下文和各个关键字的权重。

- 方便其他设备解析，如盲人阅读器根据语义渲染网页

- 有利于开发和维护，语义化更具可读性，代码更好维护，与CSS3关系更和谐。



## 什么是置换元素和非置换元素？

**置换元素** 

> 浏览器根据元素的标签和属性，来决定元素的具体显示内容。这些置换元素往往没有实际内容，即是一个空元素。例如：浏览器根据<img>标签的`src`属性显示图片，根据`<input>`标签的`type`属性决定显示输入框还是按钮。

img、input、textarea、select>、object

**非置换元素**

> 浏览器中的大多数元素都是不可置换元素，即其内容直接展示给浏览器。

label、p



## 块级元素和行内元素分别有哪些？ 空（void）元素有那些？

**块级元素**

header、footer、ul、ol、div、p、table、hr、h1-h5

**行内元素**

a、b、i、span、sub、sup、button、input、label、select、textarea

**空元素**（即系没有内容的HTML元素）

br、hr、link、input、img、meta

## 块级元素和行内元素有什么区别？

**块级元素**

- 独占一行

- 可以设置宽度和高度，如果没有设置宽度，那么默认和父元素一样宽
- 可以设置`padding`、`margin`

**行内元素**

- 不会独占一行，水平方向排列

- 不可以设置宽度和高度，默认和内容一样宽
- `padding`上下、`margin`上下无效



## img中alt和title的区别

- alt 	如果浏览器无法显示图像、浏览器将显示alt指定的内容
- title   在鼠标移到元素上时显示title的内容



## href与src的区别

href

> Hypertext Reference 的缩写，超文本引用，它指向一些网络资源，建立和当前元素或者说是本文档的链接关系。常用在a、link等标签。

src

> source 的缩写，表示的是对资源的引用，它指向的内容会嵌入到当前标签所在的位置。常用在script、img、iframe标签中。

- href用于建立当前页面与引用资源之间的关系（链接），而src则会替换当前标签。
- 遇到href，页面会并行加载后续内容；而src则不同，浏览器需要加载完毕src的内容才会继续往下走。



# CSS篇

> <font size=6>css - 面试知识点</font>

## CSS单位、区别

- %  百分比 

- px  像素。计算机屏幕上的一个点为1px。

- em  相对单位。相对于父元素font-size计算

- rem  相对单位。相对于根元素html的font-size

- rpx  微信小程序相对单位。1rpx = 屏幕宽度 / 750 px。在750px的设计稿上，1rpx = 1px。 

  

## 选择器优先级

!important  >  行内样式  >  #id >  .class  >  tag（标签）  >  *（通配符）>  继承  >  默认 

依次从右往左解析

## 优先级是如何计算的？

即不同类别样式的权重比较。择器的权值加到一起，大的优先展示；如果权值相同，后定义的优先展示。

权重：

- !important   			10000
- 内联样式表               1000
- ID 选择器                  100
- Class 类选择器         10
- HTML 标签选择器    1
- *通配符                     0



## CSS 加载方式有几种？

1. 行内样式：`<p style="color: #fff; backgournd: deepskyblue;"></p>`
2. 内嵌样式：`<style> p { color: #fff; background: deepskyblue; } </style>`
3. 链接样式：`<link href="reset.css" type="text/css" rel="stylesheet">`
4. 导入样式：`<style> @import url(reset.css); </style>`


**优先级**

行内样式  >  内嵌样式  >  链接样式  >  导入样式



## 什么是CSS继承？CSS哪些属性能继承，哪些不能?

> CSS继承可定义为特定的css属性向下传递到子孙元素，即内部的标签将拥有外部标签的样式，即子元素可以继承父元素的属性。

可以继承的样式：font-size、font-family、color、list-style、cursor

不可继承的样式：width、height、border、padding、margin、background



## link 与 @import 的区别

- `link`功能较多，可以定义RSS，定义Rel等作用，而`@import`只能用于加载 css

- 当解析到link时，页面会同步加载所引的css，而`@import`所引用的css会等到页面加载完才被加载

- `@import`需要IE5以上才能使用

- `link`可以使用js动态引入，`@import`不行，`link`方式样式的权重高于`@import`的。



## display有哪些值？说明他们的作用

- `block` 转换成块状元素。
- `inline` 转换成⾏内元素。
- `none` 设置元素不可⻅。
- `inline-block` 行内块元素。
- `list-item` 此元素会作为列表显示。
- `table` 此元素会作为块级表格来显示
- `inherit` 规定应该从⽗元素继承 `display` 属性的值

## 让一个元素隐藏有几种方式？区别？

1. `opacity:0`  

   将元素本身及其子元素都置为不可见，元素本身依然占据它自己的位置并对网页的布局起作用，它会响应用户交互

2. `visibility:hidden`  

   将元素本身及其子元素都置为不可见，元素本身依然占据它自己的位置并对网页的布局起作用，它不会响应用户交互。如果想让子元素显示，需设置子元素的属性`visibility：visible`;

3. `display:none`

   元素被隐藏，对网页的布局不起作用，且不会与用户产生交互。此外，读屏软件也不会读到元素的内容。这种方式产生的效果就像元素完全不存在。通过DOM依然可以访问到这个元素。因此你可以通过DOM来操作它。

4. `position:absolute`

   将`top`和`left`设置成足够大的负数，相当于把元素放到可视区域外，它不会影响布局，能够让元素保持可操作性，在读屏软件上可以被识别。

**区别**

opacity、visibility 影响布局，前者不影响交互，后者影响交互；

display 不影响布局，影响交互；

position 不影响布局，不影响交互；  



## 伪类、伪元素和的区别

**伪元素**

`::before`、`::after`、`::first-letter`、`::selection`、`::placeholder`

**伪类**

`:link`、`:visited`、`:hover`、`:active`、`:focus`、`:first-child`、`:not`

**区别**

1. 伪类的操作对象是文档树中已有的元素，而伪元素则创建了一个文档树外的元素；
2. CSS3规范中要求使用双冒号(::)表示伪元素，以此来区分伪元素和伪类。



## 盒模型

> 页面渲染时，dom元素所采用的布局模型，用于计算元素的宽度和高度。

box-sizing：属性取值

- content-box  默认，W3C标准盒模型。元素宽高只包含内容content，不包含border、padding

- border-box  IE盒模型。元素宽高包含内容content、border、paddingz

  

## BFC—块级格式化上下文



## 单行文本溢出加 ... 如何实现？

```css
overflow: hidden;  /* 溢出文本隐藏 */
text-overflow: ellipsis; /* 溢出文本省略 */
white-space: nowrap; /* 文本不换行 */
```



## 如何清除浮动？

- 在高度塌陷的父div末尾加一个div（<font color=red>不推荐</font>，代码不简练，不利于后期维护）	
  - `<div style="clear: both;"><div>`

- 通过增加伪元素清除浮动（<font color=red>推荐</font>，符合闭合浮动思想，结构语义化正确）
  - `::after{ display: block; content: ''; clear: both;}`

- 创建父级 BFC
  - `overflow: hidden; zoom:1;`

- 父级设置高度
  - 高度确定时可以使用



## 有几种定位方式？分别是如何实现定位的？参考点是什么？使用场景是什么？

> **定位** 即通过设置 position 属性的值是使元素**脱离正常的文档流**。定位元素经常与z-index属性进行层次分级

**默认值 static**

没有定位，元素出现在正常的流中（忽略 top， bottom， left， right 及 z-index 声明）

场景：默认布局

**相对定位 relative**

相对于其正常位置进行定位，元素<font color=red>不会脱离文档流</font>。元素在文档流中仍占据原来空间，只是表现出来的位置会相对原来的位置偏移

场景：适用于层叠效果

**绝对定位 absolute**

相对于 static 定位以外的第一个父元素进行定位，元素<font color=red>会脱离文档流</font>。如果绝对定位元素的父辈元素中没有采用定位的，那么此绝对定位元素的参考对象是`html`

适用于小区块的布局、使用频繁

**固对定位 fixed**

相对于浏览器窗口进行定位，元素<font color=red>会脱离文档流</font>。

场景：适用于广告等意图一直出现在用户眼前的信息

**粘性定位 sticky**

该定位基于用户滚动的位置。它的行为就像 `position:relative`; 而当页面滚动超出目标区域时，它的表现就像 `position:fixed`;它会固定在目标位置。可以理解为二者的结合体。



## z-index 有什么作用？ 如何使用？

控制非文档流元素的叠放顺序，该属性值越高，元素位置越靠上。

当元素设置为relative、absolute或fixed时，通过设置z-index：number； 决定叠放顺序，属性值越高，元素位置越靠上。



## 如何让块级元素水平居中？行内元素水平居中？水平垂直居中方法有哪些？

**水平居中**

- 行内元素: text-align: center

- 块级元素: margin: 0 auto

- absolute + transform
- absolute + 负margin

- flex + justify-content: center

**垂直居中**

- line-height: height

- absolute + transform
- absolute + 负margin

- flex + align-items: center

**水平垂直居中**

- absolute + transform

- flex + justify-content + align-items

- absolute + top:0 bottom:0 left:0 right:0 + margin:auto

- grid + align-self: center + justify-self: center （最强大的css布局方案，兼容性不如flex，不推荐使用

  [Grid 网格布局](http://www.ruanyifeng.com/blog/2019/03/grid-layout-tutorial.html )）

- table + table-cell + vertical-align + text-align （不推荐，会增加很多冗余代码）

# 中级

## 重绘、回流

**回流必将引起重绘，重绘不一定会引起回流**

**回流**

> 当页面中部分或全部元素的尺寸、结构、或某些属性发生改变时，浏览器重新渲染部分或全部文档的过程称为回流。

+ 下面内容会导致回流:
  + 页面首次渲染
  + 浏览器窗口大小发生改变
  + 元素尺寸或位置发生改变
  + 元素内容变化（文字数量或图片大小等等）
  + 元素字体大小变化
  + 添加或者删除可见的DOM元素
  + 激活`CSS`伪类（例如：`:hover`）
  + 查询某些属性或调用某些方法

- 一些常用的导致回流的属性和方法：
  - `clientWidth`、`clientHeight`、`clientTop`、`clientLeft`
  - `offsetWidth`、`offsetHeight`、`offsetTop`、`offsetLeft`
  - `scrollWidth`、`scrollHeight`、`scrollTop`、`scrollLeft`
  - `scrollIntoView()`、`scrollIntoViewIfNeeded()`
  - `getComputedStyle()`
  - `getBoundingClientRect()`
  - `scrollTo()`

**重绘**

> 当页面中元素样式的改变并不影响它在文档流中的位置时（例如：color、background-color、visibility等），浏览器会将新样式赋予给元素并重新绘制它，这个过程称为重绘。

**性能对比**

回流比重绘的<font color=red>代价</font>要更高。

**如何减少重绘、回流次数**

- css
  - 避免使用`table`布局
  - 尽可能在`DOM`树的最末端改变`class`
  - 避免设置多层内联样式
  - 动画效果应用到`position`属性为`absolute`或`fixed`的元素上
  - 避免使用`css`表达式

- JavaScript
  - 避免频繁操作样式，最好一次性重写`style`样式，或者将样式列表定义为`class`并一次性更改
  - 避免频繁操作DOM，使用文档片段创建一个子树，然后再拷贝到文档中
  - 先隐藏元素，进行修改后再显示该元素，因为display:none上的DOM操作不会引发回流和重绘
  - 避免循环读取会引发回流/重绘的属性，在循环之前把它们存起来
  - 对于复杂动画效果，使用绝对定位让其脱离文档流，否则会引起父元素及后续元素大量的回流

## V8垃圾回收机制

**原理**

> 找出那些不再继续使用的变量，然后释放其占用的内存，垃圾收集器会按照固定的时间间隔周期性地执行这一操作。

**回收策略**

V8 的垃圾回收策略主要基于分代式垃圾回收机制，在 V8 中，将内存分为新生代和老生代，新生代的对象为存活时间较短的对象，老生代的对象为存活事件较长或常驻内存的对象。

## 从输入URL到页面加载完成期间经历了什么？

- 输入网址

- 发送到DNS服务器，并获取域名对应的web服务器对应的ip地址

- 与web服务器建立TCP连接

- 浏览器向web服务器发送http请求

- web服务器响应请求，并返回指定url的数据（或错误信息，或重定向的新的url地址）

- 浏览器下载web服务器返回的数据及解析html源文件

- 生成DOM树，解析css和js，渲染页面，直至显示完成



# Vue

## 讲一讲MVVM？

MVVM是`Model-View-ViewModel`缩写，也就是把`MVC`中的`Controller`演变成`ViewModel`。Model层代表数据模型，View代表UI组件，ViewModel是View和Model层的桥梁，数据会绑定到viewModel层并自动将数据渲染到页面中，视图变化的时候会通知viewModel层更新数据。







## 生命周期

`beforeCreate`是new Vue()之后触发的第一个钩子，在当前阶段data、methods、computed以及watch上的数据和方法都不能被访问。

`created`在实例创建完成后发生，当前阶段已经完成了数据观测，也就是可以使用数据，更改数据，在这里更改数据不会触发updated函数。可以做一些初始数据的获取，在当前阶段无法与Dom进行交互，如果非要想，可以通过vm.$nextTick来访问Dom。

`beforeMount`发生在挂载之前，在这之前template模板已导入渲染函数编译。而当前阶段虚拟Dom已经创建完成，即将开始渲染。在此时也可以对数据进行更改，不会触发updated。

`mounted`在挂载完成后发生，在当前阶段，真实的Dom挂载完毕，数据完成双向绑定，可以访问到Dom节点，使用$refs属性对Dom进行操作。

`beforeUpdate`发生在更新之前，也就是响应式数据发生更新，虚拟dom重新渲染之前被触发，你可以在当前阶段进行更改数据，不会造成重渲染。

`updated`发生在更新完成之后，当前阶段组件Dom已完成更新。要注意的是避免在此期间更改数据，因为这可能会导致无限循环的更新。

`beforeDestroy`发生在实例销毁之前，在当前阶段实例完全可以被使用，我们可以在这时进行善后收尾工作，比如清除计时器。

`destroyed`发生在实例销毁之后，这个时候只剩下了dom空壳。组件已被拆解，数据绑定被卸除，监听被移出，子实例也统统被销毁。

![生命周期](D:\Users\lenovo\Desktop\lifecycle.png)

## Vue2.x响应式数据原理

Vue在初始化数据时，会使用`Object.defineProperty`重新定义data中的所有属性，当页面使用对应属性时，首先会进行依赖收集(收集当前组件的`watcher`)如果属性发生变化会通知相关依赖进行更新操作(`发布订阅`)。



## Vue3.x响应式数据原理

Vue3.x改用`Proxy`替代Object.defineProperty。因为Proxy可以直接监听对象和数组的变化，并且有多达13种拦截方法。并且作为新标准将受到浏览器厂商重点持续的性能优化。

以上vue面试题出自 https://juejin.im/post/5e649e3e5188252c06113021#heading-15



## vue有哪些常见的指令？

v-html、v-text、v-show、v-if、v-on、v-for、v-bind   ...



## v-if 和 v-show 区别

**v-show** 

仅仅控制元素的显示方式，将 display 属性在 block 和 none 来回切换

场景：当我们需要经常切换某个元素的显示/隐藏时，使用v-show会更加节省性能上的开销；

**v-if**

会控制这个 DOM 节点的存在与否。

场景：当只需要一次显示或隐藏时，使用v-if更加合理。



## Vue组件如何通信？

- `props/$emit+v-on`

  通过`props`将数据自上而下传递，而通过`$emit`和`v-on`来向上传递信息。

- EventBus

  通过`EventBus`进行信息的发布与订阅

- vuex

  是全局数据管理库，可以通过vuex管理全局的数据流

- `$attrs/$listeners`:

  Vue2.4中加入的`$attrs/$listeners`可以进行跨级的组件通信

- provide/inject

  以允许一个祖先组件向其所有子孙后代注入一个依赖，不论组件层次有多深，并在起上下游关系成立的时间里始终生效，这成为了跨组件通信的基础



## computed和watch有什么区别?

**computed**

1. `computed`是计算属性，也就是计算值，它更多用于计算值的场景
2. `computed`具有缓存性，computed的值在getter执行后是会缓存的，只有在它依赖的属性值改变之后，下一次获取computed的值时才会重新调用对应的getter来计算
3. `computed`适用于计算比较消耗性能的计算场景

**watch**

1. 更多的是「观察」的作用，类似于某些数据的监听回调，用于观察`props` `$emit`或者本组件的值，当数据变化时来执行回调进行后续操作
2. 无缓存性，页面重新渲染时值不变化也会执行



## Vue是如何实现双向绑定的?

采用数据劫持结合发布者-订阅者模式的方式，通过`Object.defineProperty()`来劫持各个属性的setter，getter，在数据变动时发布消息给订阅者，触发相应的监听回调。



## Vue路由传参

- Vuex

- params传参（url中显示参数）

  定义路由：`{path: "/one/login/:num"} `

  传参方式：`<router-link to="/one/login/001">`

  获取方法：`this.$route.params.num`

- params传参（url中不显示参数）

  定义路由： `{path:'/one/home/'，name:'home'}`

  传参方式：`<router-link :to="{name:'home',params:{id:001}}>`  

  获取方法：`this.$route.params.id`

- 使用query实现路由传参

  传参方式：`<router-link :to="{name:'home',query:{id:001}}`>

  获取方法：` this.$route.query.id`

- js中使用query传参

  `this.$router.push({path: '/backend/order', query: {selected: "2"}});`

