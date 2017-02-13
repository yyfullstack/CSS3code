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
|属性值|功能描述|示例代码|效果|
|---|---|---|---|
|none|定义无边框|.elm{border:none}|<span class="elm">none</span>|   
 
    
    



