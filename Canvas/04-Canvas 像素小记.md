## 1.获取图像像素

`getImageData( x , y , w , h)`

*   x,y起始坐标
*   w,h宽高
属性：

1.  width 一行的像素个数
2.  height 一列的像素个数
3.  data 一个，包含数组每个像素的rgba四个值，每个值都是0~255，前三个255代表黑色到白色，最后一个255代表透明到不透明，**以下是设置获取到的图像的颜色，利用循环对data属性中的每一个像素点循环设置**

    for( var i = 0 ; i &amp;amp;lt; oImg.width * oImg.height ; i++ ){
         oImg.data[ 4 _ i ] = 255;
         oImg.data[ 4 _ i + 1 ] = 255;
         oImg.data[ 4 _ i + 2 ] = 255;
         oImg.data[ 4 _ i + 3 ] = 255;    }

## 2.设置新的图像像素

`putImageData( 获取图像 , x , y)`

*   获取到的图像数据对象
*   x , y代表起始坐标
*   **需要获取像素才能设置**

## 3.创建新的图像像素

`createImageData ( w , h )`

*   w , h宽高
*   生成一个新的像素矩阵，初始值是全透明的黑色，即rgba ( 0 , 0 , 0 , 0 )
