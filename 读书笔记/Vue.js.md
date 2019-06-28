[为什么要用VUE](https://blog.csdn.net/liang377122210/article/details/71545459)
### 认识vue文件结构：
1. 样式部分（style）
2. 模版部分（template）
3. 脚本部分（script）
### 插值语法
{{}}
### 指令以及缩写

### 计算属性 侦听器
watch（异步场景）：侦听的为data中的值（new，old）
computed（数据联动）：对象中键的是结果 无需在data中定义，触发键变化的条件是本实例data中的数据发生变化，倘若computed中监听的值并未在其中定义，键则不会发生变化

> 区别：watch只会一个vue实例中一个值的变化，computed会监听所有值变化，watch对象的键是一个实例对象某一个数据的值，而computed的键是一个结果

### 条件渲染、列表渲染、class与style的绑定

style绑定对象的键使用单引号包裹或者使用驼峰写法

### vue-cli工程化工具

创建工程

public src package.json

### 组件化思想
1. 什么是组件化
   1. 独立的
   2. 可复用的
   3. 整体化的
2. 为什么要组件化
   1. 实现功能模块的复用
   2. 高执行效率
   3. 开发单页面复杂应用
3. 如何进行拆分
   1. 300行原则
   2. 复用原则
   3. 业务复杂性原则
4. 组件化带来的问题
   1. 组件状态管理（vuex）
   2. 多组件的混合使用，多页面，复杂业务（vue-router）
   3. 组件间的传参、消息、事件管理（props，emit/on，bus）