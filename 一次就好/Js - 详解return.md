
1. `return` 的作用
    1. 控制元素的默认行为
    2. 函数内返回任何类型的变量数据|表达式
    3. 终止函数的执行（实际为：return null）
2. `rerurn` 可以出现在哪儿？
   1. 网页元素的事件属性中
   2. js函数内
3. 有无return
   1. 事件属性中有无return
   - 有
       - 事件属性中return true|return false | return function
         - true
           执行函数后，执行元素默认行为
         - false
           取消元素默认行为
         - function(先执行函数内容)
           - return true 执行函数默认行为
           - return false 取消函数默认行为
           - return value|* 返回任何类型的变量数据|表达式
   - 无
       - 先执行函数 后执行元素默认行为
    
       例如：`onclick=“return click1（）”|onclick=“click1（）”`
       - 直接执行（不使用return）将不会对window.envent.returnvalue进行设置，所以会默认继续执行原本操作
       - 不直接执行（使用return）将对WER进行设置并对true or false进行判断

       例如：`<a href="https://baidu.com" onlick="return click1()">打开</a>`
       - 如果函数返回true，会执行click1()之后，打开百度
       如果函数返回false，那么界面就不会跳转，只会执行click1()函数里的内容（函数内跳转界面除外）

       例如：`<a href="https://baidu.com" onlick="click1()">打开</a>`
       - 无论click1()返回什么，都会在执行click1()函数后打开百度。
       onclick事件本就相当于return true|false ，返回true时才会执行元素默认行为例如：表单的提交、a标签的跳转
    1. js函数内有无return
       > js中在事件调用函数时用return返回值实际上是对window.event.returnvalue进行设置，该值决定了当前操作是否继续。返回true将继续操作，返回是false将中断操作。