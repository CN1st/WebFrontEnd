### 排序算法 - 使用Js - 详解

### 常见排序算法的时间复杂度,空间复杂度

![img](https://upload-images.jianshu.io/upload_images/1726554-156436f8dda59bf9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/966/format/webp)

1. 冒泡排序

   ```javascript
   	    var arr = [5, 4, 3, 2, 1];
               var count = 0;
               function sort(arr) {
                   for (var i = 0; i < arr.length - 1; i++) {
                       var done = true;
                       //外层 for 循环控制循环次数
                       for (var j = 0; j < arr.length - i - 1; j++) {
                           count++;
                           //内层 for 循环进行两数交换
                           if (arr[j] > arr[j + 1]) {
                               [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
                               done = false;
                           }
                       }
                       if (done) {
                           break;
                       }
                   }
                   return arr;
               }
               sort(arr);
               console.log(count);
               console.log(arr);
                function sort(arr) {
                   for (var i = 0; i < arr.length - 1; i++) {
                       var done = true;
                       //外层 for 循环控制循环次数
                       for (var j = 0; j < arr.length - i - 1; j++) {
                           count++;
                           //内层 for 循环进行两数交换
                           if (arr[j] > arr[j + 1]) {
                               [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
                               done = false;
                           }
                       }
                       if (done) {
                           break;
                       }
                   }
                   return arr;
               }
   ```

   > 冒泡排序实现原理：
   >
   > 数组中有 `n` 个数，比较每相邻两个数，如果前者大于后者，就把两个数交换位置；这样一来，第一轮就可以选出一个最大的数放在最后面；那么经过 `n-1`（数组的 length - 1） 轮，就完成了所有数的排序。
   >
   > 实现技巧：
   >
   > 代名词：重排（外层循环）
   >
   > 1.内层循环中`arr.length-i-1` `-i`的作用：
   >
   > 第一次 重排（外层循环），因为arr[0]需要与后边的四个数相比较之后最大的数已经排到了最后的位置，所以第二次 重排时arr[j]就无需与最后一个数相比较了
   >
   > 2.var done = boolean的作用：
   >
   > 由于在内部循环中如果发生了数据交换代表排序没有完成，反之，当一次完整的重排都没有发生数据交换即可代表排序完成，后续冒泡可以不再进行。

2. 快排（冒泡的改进）

   ```javascript
   			var arr = [5, 4, 3, 2, 1];
               var quickSort = function(arr) {
                   if (arr.length <= 1) {
                       return arr;
                   }
                   var pivotIndex = Math.floor(arr.length / 2);
                   var pivot = arr.splice(pivotIndex, 1)[0];
                   var left = [];
                   var right = [];
                   for (var i = 0; i < arr.length; i++) {
                       if (arr[i] < pivot) {
                           left.push(arr[i]);
                       } else {
                           right.push(arr[i]);
                       }
                   }
                   return quickSort(left).concat([pivot], quickSort(right));
               };
               console.log(quickSort(arr));
   ```

   

