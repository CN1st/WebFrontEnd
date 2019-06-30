### 张口就来
    cookie：一般由服务器生成 轻量存储大小限制4kb左右 主要用来保存登录信息 辨别用户身份 保存用户习惯配置信息
    localStorage：本地存储 每个域名5M key：value 只要能序列化成字符串都可以保存 永久存储 永不失效 直至手动删除
    sessionStorage：会话存储 使用方法与localstorage相同 会话（页面）关闭后失效
    indexDB：索引数据库
    WebSQL：关系数据库，通过SQL语句访问
    UserData：IE6起，用于本地存储
### 前端存储数据的几种方式




1. cookie
2. localstorage
3. sessionStorage
4. indexedDB
5. WebSQL
6. UserData
   

以上几项的异同从以下几个方面来分析
1. 是什么
2. 特点
3. 数据生命周期
4. 大小限制
5. 是否与服务器端进行通信
6. 易用性
7. 安全性