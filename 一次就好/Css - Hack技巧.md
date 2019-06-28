[参考文章：史上最全的CSS hack方式一览](https://blog.csdn.net/freshlover/article/details/12132801)
### 什么是CSS - HACK
    由于不同厂商的流览器或某浏览器的不同版本（如IE6-IE11,Firefox/Safari/Opera/Chrome等），对CSS的支持、解析不一样，导致在不同浏览器的环境中呈现出不一致的页面展现效果。这时，我们为了获得统一的页面效果，就需要针对不同的浏览器或不同版本写特定的CSS样式，我们把这个针对不同的浏览器/不同版本写相应的CSS code的过程，叫做CSS hack!
### CSS HACK 原理
    由于不同的浏览器和浏览器各版本对CSS的支持及解析结果不一样，以及CSS优先级对浏览器展现效果的影响，我们可以据此针对不同的浏览器情景来应用不同的CSS。
### CSS HACK 方法
1. `属性前缀法(即类内部Hack)：例如 IE6能识别下划线"_"和星号" * "，IE7能识别星号" * "，但不能识别下划线"_"，IE6~IE10都认识"\9"，但firefox前述三个都不能认识。`
2. `选择器前缀法(即选择器Hack)：例如 IE6能识别*html .class{}，IE7能识别*+html .class{}或者*:first-child+html .class{}。`
3. `IE条件注释法(即HTML条件注释Hack)：针对所有IE(注：IE10+已经不再支持条件注释)： <!--[if IE]>IE浏览器显示的内容 <![endif]-->，针对IE6及以下版本： <!--[if lt IE 6]>只在IE6-显示的内容 <![endif]-->。这类Hack不仅对CSS生效，对写在判断语句里面的所有代码都会生效。`
   ```
   这种方式是IE浏览器专有的Hack方式，微软官方推荐使用的hack方式。举例如下

                只在IE下生效
                <!--[if IE]>
                这段文字只在IE浏览器显示
                <![endif]-->
                
                只在IE6下生效
                <!--[if IE 6]>
                这段文字只在IE6浏览器显示
                <![endif]-->
                
                只在IE6以上版本生效
                <!--[if gte IE 6]>
                这段文字只在IE6以上(包括)版本IE浏览器显示
                <![endif]-->
                
                只在IE8上不生效
                <!--[if ! IE 8]>
                这段文字在非IE8浏览器显示
                <![endif]-->
                
                非IE浏览器生效
                <!--[if !IE]>
                这段文字只在非IE浏览器显示
                <![endif]-->
   ```