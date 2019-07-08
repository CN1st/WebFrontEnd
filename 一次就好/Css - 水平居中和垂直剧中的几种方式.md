### 张口就来
- 水平居中：
  - 修改显示方式：
    - 在`div`中居中一个`span`可以给`div`设置`text-align:center`
    - 在`div`中居中一个`div`可以给内部`div`设置`margin:auto`或者使用flex布局：为外部div设置：display:flex;justify:center;
    - 把div变成一个span的方法
      - display:inline
    - 把span变成一个div的方法
      - display:block|inline-block|table
      - span：float:left;position:absolute[使用定位居中span可用];
  - 定位：
    - div中居中一个div
      - 为内部div设置：position: relative;left: 50%;transform: translateX(-50%);
  - 通用：
    - `.outer {
    position: relative;
    }
    .outer .inner {
        position: absolute;
        left: 50%;
        margin-left: -25px;
    }`
>  注意：inline元素不能设置宽高
- 垂直居中：
  - 行内元素居中
    - 外部元素设置line-height==本身高度
  - 块级元素居中