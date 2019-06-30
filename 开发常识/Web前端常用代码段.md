### 通过设置chrome浏览器(谷歌浏览器)解决前端跨域问题

```
"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --args --disable-web-security --user-data-dir=C:\MyChromeDevUserData
```

### 三种注释方法
```
<!--注释内容-->
html注释
//注释内容
js单行注释
/*注释内容*/
css/js多行注释
```

### 禁用客户端console
```JavaScript
(function() {
    try {
        var $_console$$ = console;
        Object.defineProperty(window, "console", {
            get: function() {
                if ($_console$$._commandLineAPI)
                    throw "抱歉, 为了用户安全, 本网站已禁用console脚本功能";
                return $_console$$
            },
            set: function($val$_$) {
                $_console$$ = $val$_$
            }
        })
    } catch ($ignore$$) {
    }
})();
```

### 相对路径
```
    同级目录:
    FileName
    ./
    上级目录:
    ../
    顶级目录/根目录:
    /
    上上级目录:
    ../../
```

### 插入脚本
```javascript
    var hm = document.createElement("script"); 
    hm.type = 'text/javascript';
    hm.src = "http://libs.baidu.com/jquery/1.9.0/jquery.js"; 
    //插入到第一个script标签之前
    var s = document.getElementsByTagName("script")[0]; 
    s.parentNode.insertBefore(hm, s);
    //或者插入到head中
    document.head.appendChild(hm);
```

### 在console中重载layui表格
```javascript
    var reloadObj = window.layui.table.reload("[table 的 id]");
    reloadObj.config.page.limit = [int 页数];
    window.layui.table.reload("test");
```

### 得到location.href中的各个参数的值
```javascript
    function GetQueryString(name) {
        var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)");
        var r = window.location.search.substr(1).match(reg);
        if (r != null) return unescape(r[2]);
        return null;
    }
```

### 对象数组通过对象的属性进行排序
```javascript
var infoObj=[
            {
                name:"张三",
                sex:'female',
                age:30
            },
            {
                name:"李四",
                sex:'male',
                age:20
            },
            {
                name:"王五",
                sex:'female',
                age:40
            }
        ];
        // 指定排序的比较函数
    function compare(property){
         return function(obj1,obj2){
             var value1 = obj1[property];
             var value2 = obj2[property];
             return value1 - value2;     // 升序
         }
    }
    var sortObj = infoObj.sort(compare("age"));
    console.log(sortObj);
```

### 解析对象数组
```javascript
function parseJson(arr){
    if(arr.length!=0){
        function pp(arr){
            for(var i=0;i<arr.length;i++){
                if(arr[i].children && arr[i].children.length!=0){
                    console.log(arr[i].name);//这里可以写菜单的样式结构...
                    pp(arr[i].children);
                }else{
                    console.log(arr[i].name);//这里可以写菜单的样式结构...
                }
            }
        }
        pp(arr);
    }
}
parseJson(arr);
```