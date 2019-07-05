### 张口就来
```javascript
    一个变量可以存放两种类型的值，基本类型的值（primitive values）和引用类型的值（reference values）。
    基础数据类型(基本数据类型与原始数据类型等意)：Undefined、Null、Boolean、Number、String、Symbol (new in ES 6) ！
    引用类型(统称为 Object 类型)有：Object 类型、Array 类型、Date 类型、RegExp 类型、Function 类型 等。
    常用检测类型的方法：
        typeof：经常用来检测一个变量是不是最基本的数据类型
        instanceof：用来判断某个构造函数的 prototype 属性所指向的对象是否存在于另外一个要检测对象的原型链上
```

### 注意事项
- 基本类型
  - 基本类型的值是不可变的（变量的值可变 值本身不会变）
  - 基本类型的比较是它们的值的比较
  - 基本类型的变量是存放在栈内存（Stack）里的
    ```javascript
    var a,b;
    a = "zyj";
    b = a;
    console.log(a);   // zyj
    console.log(b);   // zyj
    a = "呵呵";       // 改变 a 的值，并不影响 b 的值
    console.log(a);   // 呵呵
    console.log(b);   // zyj
    ```
    ![](https://image-static.segmentfault.com/383/449/3834493100-57c3ff4a5dac7_articlex)
- 引用类型
  - 引用类型的值是可变的
  ```javascript
    var obj = {name:"zyj"};   // 创建一个对象
    obj.name = "percy";       // 改变 name 属性的值
    obj.age = 21;             // 添加 age 属性
    obj.giveMeAll = function(){
    return this.name + " : " + this.age;
    };                        // 添加 giveMeAll 方法
    obj.giveMeAll();
  ```
  - 引用类型的比较是引用的比较
  - 引用类型的值是保存在堆内存（Heap）中的对象（Object）
    与其他编程语言不同，JavaScript 不能直接操作对象的内存空间（堆内存）。
    ```javascript
    var a = {name:"percy"};
    var b;
    b = a;
    a.name = "zyj";
    console.log(b.name);    // zyj
    b.age = 22;
    console.log(a.age);     // 22
    var c = {
        name: "zyj",
        age: 22
    };
    ```
    - 图解如下：
      - 栈内存中保存了变量标识符和指向堆内存中该对象的指针
      - 堆内存中保存了对象的内容
    ![](https://image-static.segmentfault.com/330/969/3309698956-57c41a89cddc7_articlex)