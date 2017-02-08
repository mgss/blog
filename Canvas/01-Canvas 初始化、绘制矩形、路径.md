## 1. Canvas绘制环境

要想使用Canvas实现想要的效果，需要HTML和JavaScript的协调使用，html是纸，js自然就是画笔

### 1.1 HTML初始化

*   Canvas画布的默认大小是width 300px、height 150px
*   可以是用CSS样式来控制Canvas画布的大小，但是这样只会让Canvas画布等比例的缩放
*   尽量使用标签属性的宽高来控制Canvas画布大小
*   部分属性可以在Canvas标签上作用，但是`magin：0 auto`居中失效，需要用父级标签来控制
*   关于这个可能会有别的坑，待后续遇到后更新

### 1.2 JavaScript初始化

`getContext(2d)`

*   目前HTML5版本尚未实现3D环境的创建，只能创建2D环境
*   3D环境可以利用WebGL实现

## 2.绘制矩形

绘制矩形有两种形式，一种是以绘制颜色填充的矩形，另一种是以边框表示的空心矩阵

### 2.1 颜色填充矩形

`fillRect(L,T,W,H);`

*   L代表矩形的left值，即矩形到画布左边的距离
*   T代表矩形的top值，即矩形到画布上边的距离
*   W代表矩形的width值，即矩形的宽度
*   H代表矩形的height值，即矩形的高度

### 2.2 边框空心矩形

`strokeRect(L,T,W,H);`

*   LTWH同上

### 2.3 设置矩形属性

*   填充颜色`fillStyle`
*   线的宽度 `lineWidth`
*   填充颜色 `strokeStyle`

### 2.4 边界绘制

*   边界连接点样式`lineJoin = "miter(默认) | round(圆角) | bevel(斜角)"`
*   线段端点样式 `linecap = "butt(默认) | round(圆角) | square(高多出宽的一半)"`

## 3.路径绘制

### 3.1 路径绘制

1.  路径绘制开始 `beginPath()`
2.  创建新节点 `moveTo()`
3.  创建下一个节点 `lineTo()`
4.  结束路径绘制 `closePath()`

### 3.2 路径设置

*   画线 `stroke()`
*   填充颜色 `fill()`
*   绘制矩形区域`rect(L,T,W,H)`
*   清楚画布上区域内的内容`clearRect(x,y,W,H)`
*   保存路径`save()`
*   恢复路径`restore()`
