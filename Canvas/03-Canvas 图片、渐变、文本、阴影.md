## 1.插入图片

`drawImage ( oImg , x , y , w , h )`

*   oImg图片对象，x,y代表图片的起始坐标，w,h代表图片的宽高
*   ** 必须要等到图片加载完，再执行Canvas操作**
*   图片预加载可以使用oImg.onload中调用方法

## 2.背景图片

`createPattern( oImg . 平铺方式)`

*   平铺方式：repeat 、repeat-x/-y、no-repeat
*   首先创建背景对象，然后填充背景对象，最后构建

## 3.渐变

### 3.1 线性渐变

`createLinearGradient ( x1 , y1 , x2 , y2 )`

*   x1,y1代表起始点坐标，x2,y2代表结束点坐标
*   `addColorStop ( 位置 , 颜色 )`用来添加渐变点，其中位置用0-1的任意数表示，0为起始点1为结束点

### 3.2 放射性渐变

`createRadialGradient ( x1 , y1 , r1 , x2 , y2 , r2 )`

*   x1 , y1 , r1第一个圆的坐标和半径，x2 , y2 , r2第二个圆的坐标和半径
*   `addColorStop ( 位置 , 颜色 )`用来添加渐变点，其中位置用0-1的任意数表示，0为起始点1为结束点

## 4.文本

### 4.1添加文字

*   添加边框文字 `strokeText( "文本内容" , x , y )`
*   添加填充文字 `fillText( "文本内容" , x , y )`
*   x , y代表文字起始位置，默认以左下角为基准

### 4.2 文字大小

`font( " 文字大小 字体 ")`

*   文字大小：'60px impact'
*   一般字体为impact，字体不能不写

### 4.3文本上下左右对齐方式

`textAlign = end | right | center`

*   文本左右对齐方式，值默认为居左start，可以为居中、居右
`textBaseline = top | middle | bottom`

*   文本上下对齐方式 ，值默认为alphabetic，值可以为上中下

### 4.4文字宽度

`measureText ( str ).width`

*   获取文字的宽度
*   只有width，可以获取宽度，高度可以用文字的大小代替获取
*   实现文字居中：( 画布的宽 - 文字的宽 ) /2

## 5阴影

*   X轴偏移 `shadowOffsetX = N`
*   Y轴偏移 `shadowOffsetY = N`
*   阴影颜色 `shadowColor = color`
*   高斯模糊值 `shadowBlur = N`

*   必须要加偏移和阴影颜色才能显示效果，阴影的默认颜色rgba（0，0，0，0）黑色透明
*   N为像素，color为颜色
