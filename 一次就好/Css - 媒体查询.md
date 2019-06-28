[MDN：CSS媒体查询](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Media_queries)
### 张口就来
> 为不用的媒体类型编写不同的css样式，在不改变内容本身的请款修改下实现多终端多分辨率兼容

1. 什么是媒体查询

    一个媒体查询由一个可选的媒体类型和零个或多个使用媒体功能的限制了样式表范围的表达式组成，例如宽度、高度和颜色。媒体查询，添加自CSS3，允许内容的呈现针对一个特定范围的输出设备而进行裁剪，而不必改变内容本身。

2. 语法

    媒体查询包含一个可选的媒体类型和媒体特性表达式(0或多个)最终会被解析为true或false。如果媒体查询中指定的媒体类型匹配展示文档所使用的设备类型，并且所有的表达式的值都是true，那么该媒体查询的结果为true。


    ```
        <!-- link元素中的CSS媒体查询 -->
        <link rel="stylesheet" media="(max-width: 800px)" href="example.css" />

        <!-- 样式表中的CSS媒体查询 -->
        <style>
        @media (max-width: 600px) {
        .facet_sidebar {
            display: none;
        }
        }
        </style>
    ```