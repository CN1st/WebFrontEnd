本文目录

- 排序算法
  - 冒泡
  - 选择
  - 插入
  - 希尔
  - 递归
  - 堆栈
  - 归并
  - 堆
  - 桶
  - 快速
- 判断题
- 去重题
- 统计题
- 交换题
- 随机生成指定长度的字符串

### 排序算法 - 使用Js - 详解


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

    ```javascript
     function quickSort(arr) {
     
         if(arr.length<=1) {
             return arr;
         }
     
         let leftArr = [];
         let rightArr = [];
         let q = arr[0];
         for(let i = 1,l=arr.length; i<l; i++) {
             if(arr[i]>q) {
                 rightArr.push(arr[i]);
             }else{
                 leftArr.push(arr[i]);
             }
         }
     
         return [].concat(quickSort(leftArr),[q],quickSort(rightArr));
     }
     ```
3. 判断题

   1. 判断回文

      ```javascript
      function isPalindrome(str){
      	str += "";  //如果输入的是数字型，要将其先转换为字符串
      	for(var i=0,j=str.length-1;i<j;i++,j--){  
              if(str.charAt(i) !== str.charAt(j)){  
                  return false;  
              }  
          }  
          return true;  
      }
      ```

4. 去重题

5. 统计题

6. 交换题

   1. 不借助临时变量，进行两个整数的交换

      ```javascript
      function swap(a , b) {  
        b = b - a;
        a = a + b;
        b = a - b;
        return [a,b];
      }
      
      ```

7. 随机生成指定长度的字符串

    ```javascript
        function randomString(n) {  
        let str = 'abcdefghijklmnopqrstuvwxyz9876543210';
        let tmp = '',
            i = 0,
            l = str.length;
        for (i = 0; i < n; i++) {
            tmp += str.charAt(Math.floor(Math.random() * l));
        }
        return tmp;
        }
    ```


   

