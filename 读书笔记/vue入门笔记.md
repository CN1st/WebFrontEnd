# Vue Notes

## 介绍
### vue是什么
vue是一套用于构建用户界面的渐进式框架 vue的核心库只关注视图层
### 指令
v-bind:元素属性="data.item"：绑定元素特性
v-if="data.item"：true|false
v-for="item in data.items"：
v-on:事件=""：添加事件监听器
v-model:表单输入和应用状态之间双向绑定
### 组件化应用构建
注册组件
应用组件
props
## Vue实例
###创建实例
当创建一个 Vue 实例时，你可以传入一个选项对象。
```
var vm = new Vue({
    //选项
})
```
值得注意的是只有当实例被创建时 data 中存在的属性才是响应式的。也就是说如果你添加一个新的属性，如果你知道你会在晚些时候需要一个属性，但是一开始它为空或不存在，那么你仅需要设置一些初始值。

> 这里唯一的例外是使用 Object.freeze()，这会阻止修改现有的属性，也意味着响应系统无法再追踪变化。

除了数据属性，Vue 实例还暴露了一些有用的实例属性与方法。它们都有前缀 $，以便与用户定义的属性区分开来。[例如](https://cn.vuejs.org/v2/api/#%E5%AE%9E%E4%BE%8B%E5%B1%9E%E6%80%A7)：
```
var data = { a: 1 }
var vm = new Vue({
  el: '#example',
  data: data
})

vm.$data === data // => true
vm.$el === document.getElementById('example') // => true

// $watch 是一个实例方法
vm.$watch('a', function (newValue, oldValue) {
  // 这个回调将在 `vm.a` 改变后调用
})
```
实例生命周期：

![](https://cn.vuejs.org/images/lifecycle.png)
> 不要在选项属性或回调上使用箭头函数 因为箭头函数没有this
## Vue模板语法
### 插值
{{}}:文本插值
> v-once执行一次性插值

> 为了输出真正的 HTML，你需要使用 v-html 指令：

> Mustache 语法不能作用在 HTML 特性上，遇到这种情况应该使用 v-bind 指令：

> 对于布尔特性 (它们只要存在就意味着值为 true)，v-bind 工作起来略有不同，在这个例子中：
> 
```
<button v-bind:disabled="isButtonDisabled">Button</button>
```
如果 isButtonDisabled 的值是 null、undefined 或 false，则 disabled 特性甚至不会被包含在渲染出来的 `<button>` 元素中。

使用 JavaScript 表达式
> 每个绑定都只能包含单个表达式

> 流控制也不会生效，请使用三元表达式

## 计算属性和侦听器
`computed:{functionname:function(){}}`
> 计算属性是基于它们的响应式依赖进行缓存的。只在相关响应式依赖发生改变时它们才会重新求值。
### 计算属性的setter
```javascript
// ...
computed: {
  fullName: {
    // getter
    get: function () {
      return this.firstName + ' ' + this.lastName
    },
    // setter
    set: function (newValue) {
      var names = newValue.split(' ')
      this.firstName = names[0]
      this.lastName = names[names.length - 1]
    }
  }
}
// ...
```
### 侦听器
> 虽然计算属性在大多数情况下更合适，但有时也需要一个自定义的侦听器。这就是为什么 Vue 通过 watch 选项提供了一个更通用的方法，来响应数据的变化。当需要在数据变化时执行异步或开销较大的操作时，这个方式是最有用的。

## class与style绑定
### 绑定HTML Class
- 对象语法
- 数组语法
- 用在组件上
### 绑定内联样式
- 对象语法
- 数组语法
- 自动添加前缀
- 多重值