1. 双循环去重

    ```javascript
    function unique(arr) {
        if (!Array.isArray(arr)) {
            console.log('type error!')
            return
    }
        let res = [arr[0]]
        for (let i = 1; i < arr.length; i++) {
            let flag = true
            for (let j = 0; j < res.length; j++) {
                if (arr[i] === res[j]) {
                    flag = false;
                    break
                }
            }
            if (flag) {
                res.push(arr[i])
            }
        }
        return res
    }
    ```
2. indexOf去重方法一
3. indexOf去重方法二
4. 相邻对象属性去重
5. set与解构赋值去重
6. Array.from与set去重

https://juejin.im/post/5aed6110518825671b026bed