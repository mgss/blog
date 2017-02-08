## 1. 圆角

`border-radius : 20p ;`

常规属性值：

*   边框圆角，一个值为四个角的弧度半径
*   两个值是两对对角（先是左上角右下角，然后是右上角和左下角）
*   三个值是左上角、右上角左下角、右下角
*   四个值是从左上角开始顺时针四个角

圆心坐标属性值：

*   `border-radius : 20px 40px 20px 40px/30px 40px 30px 40px;`，其中斜杠前的值分别是四个角的x轴半径，斜杠后面的值是四个角的y轴半径
*   可以和常规属性值一样控制四个角的弧形程度
*   椭圆的圆角值是width/height的一半，或者用50%来产生同样的效果，百分比代表x轴是width的百分比/y轴是height的百分比

## 2. 边框背景

`border-image : url ( source )  slice width repeat ;`

*   source引入图片的路径
*   slice 切割图片，默认不加效果是将图片缩放展示到四个角，如果加则有两个值，**不加单位**，将边框图片从上和从下切割x距离的平行线，从左‘和从右切割y距离的平行线形成九宫格，默认四个角按照边框粗细显示九宫格的左上右上左下右下四个角区域的图片，除了四个角的部分根据边框粗细默认拉伸（stretch）上下左右四个区域
*   width 图片边框宽度
*   repeat图片边框的排列方式： round平铺、repeat重复（前两者效果相同）、stretch拉伸
*   在webkit内核的浏览器下，可以将九宫格的中间部门平铺到边框矩形的中间

## 3.边框颜色

`-moz-border-colors : yellow red #fff ;`

*   实现多重边框颜色的叠加，除了最上层颜色外，其他颜色只占1px
*   只在火狐下可行

## 4.线性渐变

`background-image : -webkit-linear-gradient( [&amp;amp;lt;起点&amp;amp;gt; || &amp;amp;lt;角度&amp;amp;gt;] ? &amp;amp;lt;颜色点[距离]&amp;amp;gt; &amp;amp;lt;颜色点[距离]&amp;amp;gt;...) ;`

*   只能用于背景
*   起点代表从哪开始，可以为left top，或者用角度值来代替，例如60deg（正值为逆时针旋转）
*   点可以直接加颜色点，可以规定该颜色的结束宽度，可以用px或百分比表示，并可以添加若干个点，例如：`blank 50%`
*   `-webkit-repeating-linear-gradient ;` 在属性里添加`repeating`可以使渐变平铺

IE浏览器兼容：

`filter:progid:DXImageTransform.Microsoft.gradient(startColorstr=&amp;amp;#39;#ffffff&amp;amp;#39;,endColorstr = &amp;amp;#39;#ff0000&amp;amp;#39;,GradientType=&amp;amp;#39;1&amp;amp;#39; ) ;`

*   可以兼容到ie低版本
*   只能有两个颜色的线性渐变，即startColorstr为开始颜色，endColorstr为结束颜色
*   GradientType是线性方向，1是从左到右，0是从上到下

## 5.径向渐变

`background-image : -webkit-radial-gradient( [&amp;amp;lt;起点&amp;amp;gt;] ? [&amp;amp;lt;形状&amp;amp;gt; ,] ? &amp;amp;lt;点&amp;amp;gt;,&amp;amp;lt;点&amp;amp;gt;...) ;`

*   起点：可以是关键字（left,top,right,bottom）,具体数值（xy坐标）或百分比
*   形状：ellipse椭圆、circle圆形
*   大小：具体数值或者百分比，也可以是关键字（closest-side 最近端、closest-corner最近角，farthest-side最远端、farthest-corner最远角、contain or cover包含或覆盖）
*   **火狐浏览器值支持关键字**

## 6.背景

### 6.1 多背景

`background:url(a.jpg) 0 0 , url(b.png) 0 100% ;`

*   多个url即可实现多重背景图片叠加，先写的在最上面

### 6.2 背景尺寸

`background-size : x y ;`

*   `background-size:100% 100%;`可以是像素也可以是百分比
*   值为cover覆盖，使背景图与盒子等高，超出部分隐藏
*   值为contain包含，使背景图与盒子等宽，等比例
*   如果背景有多个图片，则可以写多个尺寸，用逗号分开

### 6.3 背景图的起始点设置

`background-origin : border-box | padding-box | content-box ;`

*   值为 border-box 时，背景图片从边框的左上角开始显示
*   值为 padding-box时，也是**默认效果**，背景图片从padding区域开始显示
*   值为 content-box ，背景图片从内容区域开始显示

### 6.4 背景图的裁切背景

`background-clip : border-box | padding-box | content-box | no-clip ;`

*   border-box裁切边框之外的背景图
*   padding-box裁切内边距之外的背景图
*   content-box裁切内容之外的背景图
*   no-clip裁切border区域外的的背景图
*   `-webkit-background-clip:text ;` webkit内核的浏览器中有独有的属性text，可以让背景图片只在文字中显示，文字全透明可以实现ps中的剪贴蒙版效果

## 7.遮罩

`-webkit-mask: url() position repeat ;`

*   用法和背景图差不多，但是会将内容只在遮罩图像中显示
