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
      
####3.3 CSS3图片边框属性 [CSS3 Border-image](http://www.w3cplus.com/content/css3-border-image)
    
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
    
1. border-image-source    
>语法：    
>border-image-source:url(image url);/*image url可以是相对地址也可以是绝对地址*/    
          
    border-image-source跟CSS2中background-image属性相似，也是通过url()调用背景图片，图片的路径可以是相对地址也可以是
    绝对地址，当然你不想使用背景图片你也可以把值设置为none，即：border-image:none；其默认值就是none。
2. border-image-slice   
>语法：    
>border-image-slice: [ <number> | <percentage>]{1,4}&& fill?

    border-image的剪切和绘制原理，1、2、3、4四条蓝色切割线分别在距边框背景图四边的27px地方切了四刀，刚好将border-image
    分成了九部分：border-top-image,border-right-image,border-bottom-image,border-left-image,border-top-right-image,
    border-bottom-right-image,border-bottom-left-image,border-top-left-image八个边块和最中间的内容区域，
3. border-image-width   
 >语法：    
 >border-image-width: [ <length> | <percentage> | <number> | auto ]{1,4} 
    
    border-image-width就是border-width，用来设置边框的宽度
4. border-image-repeat   
 >语法：    
 >border-image-repeat: [ stretch | repeat | round ]{1,2}  
 
    border-image-repeat是用来指定border-image的排列方式，这个属性设置参数和其他的不一样，border-image-repeat
    不遵循top,right,bottom,left的方位原则，他只接受两个（或一个）参数值，第一个表示水平方向，第二个表示垂直方向；
    当取值为一个值时，表示水平和垂直方向的排列方式相同。同时其默认值是stretch，如果你省略不取值时，那么水平和垂直
    方向都是以stretch排列。
  
  最终语法
  border-image:<‘border-image-source’> || <‘border-image-slice’> [ / <‘border-image-width’>] || <‘border-image-repeat’>
  
    
####3.4 CSS3圆角边框属性[Border-radius](http://www.w3cplus.com/css3/border-radius)

#####3.4.1 Border-radius属性的语法及参数
    border-radius ： none | <length>{1,4} [/ <length>{1,4} ]?
    取值: 由浮点数字和单位标识符组成的长度值。不可为负值
 1. border-radius: [ <length>{1,4} ]; //这里只有一个值，那么top-left、top-right、bottom-right、bottom-left四个值相等。
 2. border-radius:[ <length>{1,4} ] [ <length>{1,4} ] ; //这里设置两个值，那么top-left等于bottom-right，并且取第一个值；top-right等于bottom-left，并且取第二个值
 3. border-radius:[ <length>{1,4} ] [ <length>{1,4} ] [ <length>{1,4} ];//如果有三个值，其中第一个值是设置top-left;而第二个值是top-right和bottom-left并且他们会相等,第三个值是设置bottom-right
 4. border-radius:[ <length>{1,4} ] [ <length>{1,4} ] [ <length>{1,4} ] [ <length>{1,4} ];//如果有四个值，其中第一个值是设置top-left;而第二个值是top-right,第三个值bottom-right,第四个值是设置bottom-left。

        border-radius的属性参数非常简单，主要包含两个值
        none：默认值，表示元素没有圆角
        <length>：由浮点数字和单位标识符组成的长度值，不可为负值
       border-radius 和border属性一样，可以将各个角拆分出来，这样就派生出另外4个子属性，而且它们都是先Y轴在X轴
       border-top-left-radius:<length>/<length>,定义元素左上角圆角
       border-top-right-radius:<length>/<length>,定义元素右上角圆角
       border-bottom-right-radius:<length>/<length>,定义元素右下角圆角
       border-bottom-left-radius:<length>/<length>,定义元素左下角圆角
#####3.4.2 Border-radius属性的使用方法
    border-radius属性包含两个参数值，第一个是水平圆角半径值，第二个是垂直圆角半径值，而且两个参数值使用“/”分开
  1. border-radius只设置一个值,元素的四个角具有圆角，而且圆半径值一样，
  2. border-radius设置两个值,top-left等于bottom-right并且它们取一个值为10px，top-right等于bottom-left并且它们取一个值为30px，
  3. border-radius设置三个值,top-left取第一个值为10px，top-right等于bottom-left并且它们第二个值为50px，bottom-right取第三个值30px
  4. border-radius设置四个值,top-left取第一个值为10px，top-right取第二个值为20px，bottom-right取第三个值30px,bottom-left取第四个值40px
  
#####单独设置水平和垂直半径值
    border-radius设置圆角时， 可以把圆角的水平和垂直半径值单独设置，此时就需要使用以“/”来区别。“/”前面的表示圆角的
    的水平半径，而“/”后面的值表示圆角的垂直半径。但分开设置各个顶角的圆角的水平和垂直半径的圆角效果，不需要“/”.
    border-top-left-radius:10 20px;
    border-top-right-radius:10 20px;
    border-bottom-left-radius:10 20px;
    border-bottom-right-radius:10 20px;
#####特殊应用
  * 对于border-radius还有一个内半径和外半径的区别，它主要是元素 边框值较大时，效果就很明显，当我们border-radius半径值小于或等于border的厚度时，我们边框内部就不具有圆角效果
  * 如果角的两个相邻边有不同的宽度，那么这个角将会从宽的边平滑过度到窄的边。其中一条边甚至可以是0。相邻转角是由大向小转。
  
#####图片应用圆角
border-radius能应用在各种元素中，但在img和table应用时会有点差别的，首先先来看图片上应用border-radius时的情况。
在img上应用border-radius到目前浏览器都能对图片进行剪切

#####表格应用圆角
另外table的样式属性border-collapse是collapse时,border-radius不能正常显示,只有border-collapse: separate;时才能正常显示。

####3.5 CSS3盒子阴影属性[box-shadow](http://www.w3cplus.com/css3/border-radius)
#####3.5.1 box-shadow属性的语法及参数
    E {box-shadow: <length> <length> <length>?<length>?||<color>}
    也就是：
    E {box-shadow:inset x-offset y-offset blur-radius spread-radius color}
    换句说：
    对象选择器 {box-shadow:投影方式 X轴偏移量 Y轴偏移量 阴影模糊半径 阴影扩展半径 阴影颜色}    
    box-shadow和text-shadow一样可以使用一个或多个投影，如果使用多个投影时必须需要用逗号“，”分开。

    取值：
    box-shadow属性至多有6个参数设置，他们分别取值：
    阴影类型：此参数是一个可选值，如果不设值，其默认的投影方式是外阴影；如果取其唯一值“inset”,就是将外阴影变成内阴影，
    也就是说设置阴影类型为“inset”时，其投影就是内阴影；
    X-offset:是指阴影水平偏移量其值可以是正负值可以取正负值，如果值为正值，则阴影在对象的右边，反之其值为负值时，
    阴影在对象的左边；
    Y-offset:是指阴影的垂直偏移量，其值也可以是正负值，如果为正值，阴影在对象的底部，反之其值为负值时，阴影在对象的顶部；
    
    阴影模糊半径：此参数是可选，但其值只能是为正值，如果其值为0时，表示阴影不具有模糊效果，其值越大阴影的边缘就越模糊；
    阴影扩展半径：此参数可选，其值可以是正负值，如果值为正，则整个阴影都延展扩大，反之值为负值是，则缩小
    阴影颜色：此参数可选，如果不设定任何颜色时，浏览器会取默认色，但各浏览器默认色不一样，特别是在webkit内核下的
    safari和chrome浏览器将无色，也就是透明，建议不要省略此参数

#####3.5.2 box-shadow属性的使用方法
    ![box-shadow工作方式](box-shadow-work.png "box-shadow工作方式")
