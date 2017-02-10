####二、简介
selectivizr是一个JavaScript工具，使IE浏览器也可以支持CSS3伪类以及属性选择器，使用很简单，只要把js include到页面上，
然后你就可以(～ o ～)~zZ补觉了。

优点在于：
1. 让老的IE浏览器支持19个CSS3伪类，2个伪元素，以及所有的属性选择器。
2. 即使你完全不懂JavaScript，也没有关系，因为你只要链接这个文件就ok了。
3. 可以与现存的JavaScript库协调工作。

####三、使用
直接调用JavaScript文件就可以了：

<script type="text/javascript" src="[JS library]"></script>
<!- -[if (gte IE 6)&(lte IE 8)]>
      <script type="text/javascript" src="selectivizr.js"></script>
      <noscript><link rel="stylesheet" href="[fallback css]" /></noscript>
<![endif]- ->
//zxx:由于某些原因，我把上面连续的两个短连线给分开了
上面的noscript的内容，我个人觉得是可有可无的。按照原作者的说法，
JavaScript文件要放在页面的<head>标签里，而且需要使用一种下图所示的JavaScript库。

####四、必须知道的一些注意事项
1. Selectivizr自动检测最佳的JavaScript库，如果你一个JavaScript库都没有调用，则IE下的伪类是不起作用的。
2. 样式属性必须使用<link>标签，但是你可以使用@import在你的样式表里面，以<style>标签定义的CSS样式是不会被解析的。
3. 由于安全原因，样式文件需以域的形式调用，像是file:是不起作用的。
4. 此效果非动态的。一旦样式被应用就被固定了，DOM改变时不会映射过去的。
5. 如果JavaScript不可以，你可以使用<noscript>标签调用一个用以反馈提示的样式文件。
6. Selectivizr要想在IE下起作用，需要时标准模式，请检查您的页面头部是否有DTD 。