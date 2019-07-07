### 张口就来

    cookie：一般由服务器生成 轻量存储大小限制4kb左右 主要用来保存登录信息 辨别用户身份 保存用户习惯配置信息

    localStorage：本地存储 每个域名5M key：value 只要能序列化成字符串都可以保存 永久存储 永不失效 直至手动删除

    sessionStorage：会话存储 使用方法与localstorage相同 会话（页面）关闭后失效

    其他存储方式：
        indexDB：索引数据库
        WebSQL：关系数据库，通过SQL语句访问
        UserData：IE6起，用于本地存储
### 参考链接：
1. https://juejin.im/entry/5a41b7f4f265da43152427b6
2. https://blog.csdn.net/think2me/article/details/38726429

以上几项的异同从以下几个方面来分析

1. 为了解决什么问题
2. 是什么
3. 有什么用
4. 如何工作
5. 如何操作
6. 优缺点
   1. 数据生命周期
   2. 大小限制
   3. 是否与服务器端进行通信
   4. 易用性
   5. 安全性
   
### 前端存储数据的几种方式

1. cookie
   1. 为了解决早起浏览器无法管理管理用户状态的问题
   2. cookie是纯文本方式的数据存储方式
   3. 辨别用户身份 [session](https://blog.csdn.net/think2me/article/details/38726429)跟踪保存用户登录状态
   4. 
2. localstorage
3. sessionStorage
4. indexedDB
5. WebSQL
6. UserData
   