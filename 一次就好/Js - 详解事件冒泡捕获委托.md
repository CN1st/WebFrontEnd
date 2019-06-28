# 张口就来
> 冒泡：处于DOM对象模型底部对象事件被触发时，会依次激活上层直系对象定义的同类事件
>
> 捕获：处于DOM对象模型顶部对象事件被触发时，会依次激活下层直系对象定义的同类事件
> 
> 委托：利用事件冒泡原理，当希望某级DOM对象需要触发同类型事件时，将此事件函数委托到父级或者更外级DOM元素上执行
> 
> DOM事件流添加事件监听[isTriggeredWhenCapturing:是否在捕获阶段触发]：`addEventListener(eventType,function,isTriggeredWhenCapturing)`
> 
> DOM事件流移除事件监听：`removeEventListener(eventType,function,isTriggeredWhenCapturing)`
> 
> IE事件流添加事件监听(IE事件模型没有事件捕获阶段)：`attachEvent("on"+event,function)`
> 
> IE事件流移除事件监听：`detachEvent("on"+event,function)`
### 什么是事件
---

> 事件是可以被JavaScript侦测到的行为，简单来讲就是用户与web页面进行某种交互时，解释器就会创建相应的event对象以描述事件信息

- 常见的事件有
  1. 鼠标点击|经过某元素
  2. 键盘事件
  3. 滚动事件
  4. 窗口大小改变事件
  5. 元素加载状态事件
  6. 等
### 事件周期
---
解释器创建一个event对象后，会按照如下过程在html元素间传播传播过程分为三个阶段
- 第一阶段：事件捕获，事件沿DOM树向下传播
- 第二阶段：目标出发，运行时间监听函数
- 第三阶段：事件冒泡，事件沿DOM树向上传播

### 事件句柄
事件句柄（又称为事件处理函数、时间监听函数），指用于相应某个事件而调用的函数。每一个事件均对应一个事件句柄，在程序执行时，将对应的函数或者语句指定给事件句柄，则在改时间发生时，浏览器便会执行指定的函数或者语句

### 事件定义的三种方式
1. 直接在html中定义元素的事件相关属性的值
   ```
   <button click="alert("alert a alert")">BUTTON</button>
   ```
   > 缺点：内容与行为耦合
2. 事件定义(DOM0级事件)
   在JavaScript中为元素的事件相关属性赋值
   ```
   document.getElementById("btn").onclick=function(){}

   document.body.onload=init:
   function init(){}
   ```
   > 缺点：此语法实现了内容与行为相分离，但是元素只能绑定一个监听函数
3. DOM2级事件
   高级事件处理方式，一个事件可以绑定多个监听函数：
   ```
   btn.addEventListener("click",function(){},false);

   document.body.addEventListener("load",init);
   ```
   > 此语法可以为一个元素绑定多个监听函数，但是需要注意浏览器的兼容性问题
   > DOM0和DOM2的区别
   > 1. DOM2支持同一个dom元素注册多个同种事件。
   > 2. DOM2新增了捕获和冒泡的概念 
### Event对象
1. event对象常用的属性和方法
   1. type`事件类型`
      1. onclick
      2. onfocus
      3. onblur
      4. onmouseover`移到之上`
      5. onmouseout`鼠标移开`
      6. onmousedown
      7. onmousemove`鼠标移动`
      8. onmouseup
      9. onresize`窗口或者框架被重新调整`
      10. onsubmit`表单提交`
      11. onkeydown`键盘按下`
      12. onkeypress`按下并松开`
      13. onkeyup`松开`
      14. touchstart`触摸`
      15. touchmove`手指在屏幕上滑动`
      16. touchend`鼠标从屏幕上离开`
   2. srcElement/target`发生事件的元素`
   3. cancelBubble`布尔属性，在从事件处理程序返回之前将其值设置为true可阻止事件的传播。e.cancelBubble = true;相当于e.stopPropagation()`
   4. returnValue`布尔属性，为false时可以组织浏览器执行默认的事件动作。e.returnValue = false;想当于e.preventDefault();`
   5. clientX/clientY`事件发生时，鼠标相对于浏览器窗口可视文档区域的左上角的位置`
   6. offsetX/offsetY`事件发生时，鼠标相对于事件源元素左上角的位置`