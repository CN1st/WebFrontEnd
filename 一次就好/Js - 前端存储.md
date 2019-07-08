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

- cookie
   1. 为了解决什么问题？
      - 为了解决早起浏览器无法管理管理用户状态的问题
   2. cookie是什么
      - cookie是纯文本方式的数据存储方式
   3. cookie有什么用
      - 辨别用户身份 [session](https://blog.csdn.net/think2me/article/details/38726429)
      - 跟踪保存用户登录状态
   4. cookie如何工作及注意事项
      - 每个http请求都会request header 的cookie字段中添加本地cookie 此特点关系到适合存储的数据类型 
      - 多浏览器cookie存储位置并不相同 不通用
      - cookie的存储是以域名的形式区分的
      - 我们能操作的域是当前域和当前域下的子域
      - 每个域名下的cookie存储数量是有限制的 不用浏览器有不同的限制 一般为20个
      - 每个cookie大小不同浏览器之间有不同的限制 一般限制为4kb
      - cookie的过期时间一般为会话结束时自动销毁 可以自主设定
   5. cookie的增删改查
      - 设置
        - 客户端设置
            ```
            document.cookie = '名字=值';
            document.cookie = 'username=cfangxu;domain=baike.baidu.com'    并且设置了生效域
            ``` 
            > 注意： 客户端可以设置cookie 的下列选项：expires、domain、path、secure（有条件：只有在https协议的网页中，客户端设置secure类型的 cookie 才能成功），但无法设置HttpOnly选项。
        - 服务器端设置
        - 
      - 删
      - 改
      - 查
1. localstorage
2. sessionStorage
3. indexedDB
4. WebSQL
5. UserData
   