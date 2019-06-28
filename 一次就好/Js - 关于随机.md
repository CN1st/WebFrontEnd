1. 关于随机的Math API
   1. Math.random()
      > 函数返回一个浮点,  伪随机数在范围[0，1)，也就是说，从0（包括0）往上，但是不包括1（排除1），然后您可以缩放到所需的范围。实现将初始种子选择到随机数生成算法;它不能被用户选择或重置。
   2. Math.floor()
      > Math.floor() === 向下取整(忽略符号)
   3. Math.ceil()
      > Math.ceil() === 向上取整(忽略符号)
   4. Math.round()
      > Math.round() 函数返回一个数字四舍五入后最接近的整数。
   5. Math.abs()
      > Math.abs() 取绝对值
2. 常用随机函数
   1. 得到一个大于等于0，小于1之间的随机数
      > [0，1) === [即从0（包含0）到...1但不包括1（排除1）。
      > [0，1) === 左闭右开区间
        ```javascript
        function getRandom() {
            return Math.random();
        }
        ```
   2. 得到一个两数之间的随机数
      > 这个例子返回了一个在指定值之间的随机数。这个值不小于 min（有可能等于），并且小于（不等于）max。
        ```javascript
        function getRandomArbitrary(min, max) {
            return Math.random() * (max - min) + min; 
        }
        ```
   3. 得到一个两数之间的随机整数
      > 这个例子返回了一个在指定值之间的随机整数。这个值不小于 min （如果 min 不是整数，则不小于 min 的向上取整数），且小于（不等于）max。
        ```javascript
        function getRandomInt(min, max) {
            min = Math.ceil(min);
            max = Math.floor(max);
            return Math.floor(Math.random() * (max - min)) + min; //不含最大值，含最小值
            //return Math.floor(Math.random() * (max - min + 1)) + min; //含最大值，含最小值 
        }
        ```
      > 上一个例子提到的函数 getRandomInt() 结果范围包含了最小值，但不含最大值。如果你的随机结果需要同时包含最小值和最大值，怎么办呢?  getRandomIntInclusive() 函数可以实现。
   4. 随机一个数字加字母的字符串
        ```javascript
        var chars = ['0','1','2','3','4','5','6','7','8','9','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'];
        function generateMixed(n) {
            var res = "";
            for(var i = 0; i < n ; i ++) {
                var id = Math.ceil(Math.random()*35);
                res += chars[id];
            }
            return res;
        }
        ```
      > 参数：需要的字符串长度 返回值：所需字符串
   5. 待编辑标题
        ```javascript
        待编辑代码块儿
        ```
      > 待编辑引用
   6. 待编辑