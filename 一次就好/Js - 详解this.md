## 张口就来
---
&nbsp;this是一个js中的关键字之一，特殊之处在于随时随地被定义在每一个函数内，this机制通过传递一个隐式的对象引用让代码变得更加简洁，复用性更好。

### this的指向
1. 在全局环境中 this指向全局对象
2. 在函数（运行内）环境中，this的指向取决于函数被调用的方式
   1. 隐式绑定给调用者
   2. 待编辑