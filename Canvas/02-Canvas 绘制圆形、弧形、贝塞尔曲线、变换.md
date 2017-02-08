## 1. 绘制圆形

`arc ( x . y , 半径 , 起始弧度 ，结束弧度 ，旋转方向 )`

*   x , y 代表圆心坐标，控制圆的位置
*   半径控制圆的大小
*   起始弧度和结束弧度转化为度数的公式：`弧度 = 度数 * Math.PI / 180`
*   旋转方向有两个值，true代表逆时针，不填或false时为顺时针
*   设置为顺时针时，起始弧度为0时，起始点位于圆的3点钟方向，起始弧度为-90为12点钟方向，90度时为6点钟方向，正负180度为9点钟方向

## 2.绘制弧形

`arcTo ( x1 , y1 , x2 , y2 , r )` 实现效果图

![图1](https://www.ylzzxt.cn/wp/wp-content/uploads/2017/01/QQ20170125-111418-300x91.png)
<pre>      var oC = document.getElementById('canvas');
      //兼容Canvas
      if(oC.getContext){
          var oGC = oC.getContext('2d');  //获取Canvas画笔对象
          oGC.moveTo(50,50); //创建起始点
          oGC.arcTo(200,50,200,100,50); //端点1，端点2，半径
          oGC.stroke();//绘制线条
      }
</pre>

*   ** 绘制弧形必须首先要预先绘制一个起始点 **
*   arcTo用来在画布上创建介于两个切线之间的弧形
*   x1,y1为端点1
*   x2,y2为端点2
*   r为弧线的半径
*   **图中的圆弧起点并未创建，而是根据端点1和端点2的距离，构建相同的距离，并在与起始点连接的线上产生的点，并根据半径的长度到端点1、端点2以及圆弧起点构成的线段相同距离的位置确定圆弧中心点**

## 3.绘制贝塞尔曲线

### 3.1单点控制的贝塞尔曲线

`guadraticCurveTo ( x1 , y1 , x2 , y2 )`

![quadraticcurve](https://www.ylzzxt.cn/wp/wp-content/uploads/2017/01/quadraticcurve.gif)
<pre>var oC = document.getElementById('canvas');
//兼容Canvas
 if(oC.getContext){
          var oGC = oC.getContext('2d');//获取Canvas画笔对象
          oGC.beginPath();//开始路径
          oGC.moveTo(20,20);//绘制开始点
          oGC.quadraticCurveTo(20,100,200,20);//控制点，结束点
          oGC.stroke();//绘制线条
          oGC.closePath();//结束路径
}</pre>

*   x1,y1 控制点
*   x2,y2 结束点
*   利用控制点控制开始点到结束点曲线的弯曲形状和程度，类似于Photoshop中的钢笔工具

### 3.2 两点控制的贝塞尔曲线

`bezierCurveTo ( x1 , y1 , x2 , y2 , x3 , y3 )`

![beziercurve](https://www.ylzzxt.cn/wp/wp-content/uploads/2017/01/beziercurve.gif)
<pre>var oC = document.getElementById('canvas');
//兼容Canvas
 if(oC.getContext){
          var oGC = oC.getContext('2d');//获取Canvas画笔对象
          oGC.beginPath();//开始路径
          oGC.moveTo(20,20);//绘制开始点
          oGC.bezierCurveTo(20,100,200,100,200,20);// 控制点1 , 控制点2 , 结束点
          oGC.stroke();//绘制线条
          oGC.closePath();//结束路径
}</pre>

*   形式与 `guadraticCurveTo ( )` 相似，与其区别是 `bezierCurveTo ( )` 是由两个点来控制

## 4.变换

### 4.1偏移位置

`translate( x , y )`

*   根据移动目标的初始位置，移动到设置的x,y坐标上

### 4.2旋转

`rotate( 弧度 )`

*   根据给定的弧度，以目标的初始点为中心旋转
*   多个旋转方法可以累加

### 4.3缩放

`scale( x倍数 ，y倍数)`

*   倍数：1=100%, 0.5=50%, 2=200%, 依次类推
