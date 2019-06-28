### 计算js代码执行所需时间

1. 使用console.time()在函数执行前开始计时

   使用console.timeEnd()在函数执行后停止计时

   两个方法通过传入相同的参数来确定所需计时的代码段的头末位置。

   例如：

   ```
   console.time("Array initialize");
   var arr = new Array(1000000),
       len = arr.length,
       i;
   
   for (i = 0; i < len; i++) {
       arr[i] = new Object();
   };
   console.timeEnd("Array initialize"); // 输出: Array initialize: 266.000ms
   ```

2. 使用new Date().getTime()分别记录开始时间和停止时间 取两个时间戳之差计算函数执行时间

   ```javascript
   var start = new Date().getTime(); // 开始时间
   var i;
   var a = [1,2,3,4,5,6,7,8,9,0]; 
   
    // 必有的for循环，只能是将循环体的运算计算足够多的次数（比如100万次），才能在毫秒级别看出运行时间差
   for (i = 0; i < 1000000; i++) {
       a.map(function(x) { return x * 3}); // 这行代码是随意写的范例
   }
   
   var end = new Date().getTime(); // 结束时间
   
   console.log(end - start);
   ```

   