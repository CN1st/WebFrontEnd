1. JavaScript语法
2. JavaScript的流程控制语句
3. JavaScript函数
4. JavaScript的内置对象
5. 错误调试与处理
6. JavaScriptDOM操作
7. JavaScriptDOM属性
8. JavaScriptDOM事件
9. JavaScript事件
10. JavaScriptBOM基础
    - BOM（browser object model）浏览器对象模型
    1.  windows对象
        > window是浏览器的一个实例，在浏览器中，window对象有双重角色
            - 它既是通过js访问浏览器窗口的一个接口
            - 又是一个ECMAScript规定的Global对象
        > 全局对象的两种声明方式：window声明 | 关键字声明 

        > 所有的全局变量和全局方法都被归在window上
        1. window对象的方法
           1. alert
           2. confirm`确定 =>return true 取消 =>return false`
           3. prompt("text,defalutText") `确定 =>return text 取消 =>return null`
           4. open(pageURL,name,parameters)
              - parameter的值（是否：yes|no）
                - width
                - height
                - left：x
                - top：y
                - toolbar：浏览器工具栏
                - menubar：菜单栏
                - scrollbars：是否显示滚动条
                - location：是否显示地址栏
                - status：是否显示状态栏
            5.  setTimeout|setInterval(code,millisec)
                > JavaScript是单线程语言单线程就是所有代码必须按照顺序执行

                > 通过给变量赋值null释放内存
                - 清除倒计时|定时器clearTimeout|clearInterval(对应的setTimeout|setInterval方法返回一个id值)
    2.  location对象
        > location对象提供了与当前窗口中加载的文档有关的信息，还提供了导航的功能，它既是window对象的属性也是document对象的属性
        - location对象的常用属性
          - href`location.href===window.location.href`
          - hash`#后面跟零或者多个字符串 如果不包含则返回空的字符串 可用作读取链接中的锚点或者通过赋值#id的方式跳转到锚点位置`
          - host
          - hostname
          - pathname
          - port
          - protocal
          - search
        - location对象的方法
          - replace()`相较于href不会再历史记录中生成记录`
          - reload()`true从服务器加载 空可能从缓存中加载`
    3.  history对象
        > history对象保存了用户在浏览器页面中访问的历史记录
        - back()`等价于history.go(-1)`
        - forward()`等价于history.go(1)`
    4.  screen对象
        > screen对象包含客户端显示屏幕的信息
        - screen对象的属性
          - screen.availWidth`可用屏幕的宽度 也就是整个屏幕能够用来显示网页内容的宽度`
          - screen.availHeith `可用屏幕的高度`
          > 获取当前窗口文档县市区的高度和宽度可以使用window.innweHeight|innerWidth`控制台会占用此块儿内容`
    5.  navigator对象
        > indexOf()方法返回某个字符串的值在字符串中首次出现的位置，如果没有出现过则返回-1
        - navigator对象的属性
          - userAgent
            - msie
            - chrome
            - opera
            - safari
          - appCodeName
          - appName  
    6.  document对象
    7.  event对象