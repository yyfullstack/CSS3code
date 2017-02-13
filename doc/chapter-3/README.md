###CSS3边框
---
####3.1 CSS3边框简介
#####3.1.1 边框的基本属性
    css1和css2中边框属性其实很简单，其主要包括三个类型值，
    border-with：设置元素边框的粗细
    border-color：设置元素边框的颜色
    border-style：设置元素边框的类型
    
    
    div{
         width: 200px;
         height: 100px;
         border: 3px red;
     }
     浏览器解析将“border-style”解析成为“none”
            
    div {
        width: 200px;
        height: 100px;
        border: solid;
    }
    边框border-width的默认值为“medium”(大约3~4px),border-color的默认色为字体的颜色
#####3.1.2 边框的类型
    border-style值列表
|属性值|功能描述|示例代码|
|---|---|---|
|none|定义无边框|.elm{border:none}|  
|hidden|与“none”相同，不过应用于表时除外，对于表，hidden用于解决边框冲突|.elm{border:hidden}|  
|dotted|定义点状边框|.elm{border:3px dotted red;}|  
|dashed|定义虚线边框|.elm{border:3px dashed red}|
|solid|定义实线边框|.elm{border:3px solid red}|  
|double|定义双线，双线的宽度等于border-width的值|.elm{border:3px double red}|  
|groove|定义3D凹槽边框，其效果取决于border-color的值|.elm{border:3px groove red}|
|ridge|定义3D垄状边框。其效果取决于border-color的值|.elm{border:3px ridge red}|
|inset|定义3D inset边框。其效果取决于border-color的值|.elm{border:3px inset red}|
|outset|定义3D outset 边框。其效果取决于border-color的值|.elm{border:3px outset red}|
|inherit|规定应该从父元素继承边框样式。部分浏览器不支持这个属性值||

#####3.1.3 谁在使用CSS3边框
    border-color 还没有成为标准,仅firefox浏览器自己一个扩展性写法，
    border-image 使用很少
    border-radius 使用广泛
    box-shadow 在web页面上css3的盒子阴影特性应用非常广泛
    
####3.2 CSS3边框颜色属性

####3.2.1 CSS3边框颜色属性的语法及参数    
     -moz-border-top-colors: <color> <color> <color>*; /*顶边边框*/
      -moz-border-right-colors:<color> <color> <color>*; /*右边边框*/
      -moz-border-bottom-colors: <color> <color> <color>*; /*底边边框*/
      -moz-border-left-colors: <color> <color> <color>*; /*左边边框*/ 
####3.2.2 兼容性
      目前只有Firefox支持
      
####3.3 CSS3图片边框属性
####3.3.1 CSS3图片边框属性的语法及参数
    border-image ： none | <image> [ <number> | <percentage>]{1,4} [ / <border-width>{1,4} ]? [ stretch | repeat | round ]{0,2}
    
  1. none:是border-image的默认值，如果取值为none时，表示边框无背景图片；
  * <image>：设置border-image的背景图片，这个跟background-image一样，使用绝对或相对的url地址，来指定背景图片；
  * <number>：number是一个数值，用来设置边框的宽度，其单位是px，其实就像border-width一样取值，可以使用1~4个值，其具体表示四个方位的值，大家可以参考border-width的设置方式；
  * <percntage>：percntage也是用来设置边框的宽度，跟number不同之处是，其使用的是百分比值来设置边框宽度；
  * stretch,repeat,round: 他们是用来设置边框背景图片的铺放方式，类似于background-position，其中stretch是拉伸，repeat是重复，round是平铺，stretch为默认值
 
####3.3.2 border-image属性使用方法
    为了更好的理解,先暂时把border-image在语法的表达形式进行属性的分解来阐述（实际应用中是不能分解的），这样就可以把border-image分解为：    
    1、引入图片：border-image-source;    
    2、切割引入的图片：border-image-slice；:    
    3、边框的宽度：border-image-width；    
    4、图片的排列方式：border-image-repeat。
    
*border-image-source    
    >语法：    
      border-image-source:url(image url);/*image url可以是相对地址也可以是绝对地址*/    
          
    border-image-source跟CSS2中background-image属性相似，也是通过url()调用背景图片，图片的路径可以是相对地址也可以是
    绝对地址，当然你不想使用背景图片你也可以把值设置为none，即：border-image:none；其默认值就是none。
    
      
    



