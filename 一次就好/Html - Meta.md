[MDN文档关于Meta](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta)
### meta标签是一个在html文档head标签里定义的一个对文档进行描述的功能的标签
1. meta标签有以下作用
   1. 搜索引擎优化
   2. 自定义页面使用语言
   3. 自动刷新并指向指定页面
   4. 实现网页转换的动态效果
   5. 控制页面缓冲
   6. 网页定级评价
2. meta标签的组成（两个属性name和http-equiv，content属性包含http-equiv 或name 属性的值，具体取决于所使用的值。）
   1. name属性
        1. 主要用来描述网页与之配套使用的属性为 `content`中的内容主要是便于搜索引擎爬虫查找页面分类信息
        ```
        <meta name="参数"content="具体的参数值">
        ``` 
        1. name属性的参数
         
             1. keyword
             2. description
             3. robots
             4. author
             5. render
             6. viewport
             7. 等
            
    1. http-equiv属性
        - 相当于http文件头的作用，他可以为浏览器提供传回一些有用的信息，以帮助正确的准确的显示渲染网页内容
        ```
        <meta http-equiv="参数"content="参数变量值">
        ```
        
        1. http-equiv属性的参数
         
             1. expires
             2. pragma
             3. refresh
             4. set-cookie
             5. window-target
             6. content-type
             7. content-language
             8. cache-control
             9. 等