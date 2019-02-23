## 使用``CSS``绘制的基本图形

+  正方形 (square)
```CSS
#square {
  width: 100px;
  height: 100px;
  background: red;
}
```
实现效果如下图：

![现代Javascript教程 ](https://raw.githubusercontent.com/youling4438/develope-websites/master/images/jsinfo.png "现代Javascript教程")

+ 长方形 (rectangle)
```CSS
#rectangle {
  width: 200px;
  height: 100px;
  background: red;
}
```
实现效果如下图：

![现代Javascript教程 ](https://raw.githubusercontent.com/youling4438/develope-websites/master/images/jsinfo.png "现代Javascript教程")

+ 正圆 (circle)
```CSS
#circle {
  width: 100px;
  height: 100px;
  background: red;
  border-radius: 50%
}
```
实现效果如下图：

+ 椭圆 (oval)
```CSS
#oval {
  width: 200px;
  height: 100px;
  background: red;
  border-radius: 100px / 50px;
}
```
实现效果如下图：

+ 向上三角 (triangle-up)
```CSS
#triangle-up {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 100px solid red;
}
```
实现效果如下图：

+ 向下三角 (triangle-down)
```CSS
#triangle-down {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-top: 100px solid red;
}
```
实现效果如下图：

+ 方向朝左的三角 (triangle-left)
```CSS
#triangle-left {
  width: 0;
  height: 0;
  border-top: 50px solid transparent;
  border-right: 100px solid red;
  border-bottom: 50px solid transparent;
}
```
实现效果如下图：

+ 方向朝右的三角 (triangle-right)
```CSS
#triangle-right {
  width: 0;
  height: 0;
  border-top: 50px solid transparent;
  border-left: 100px solid red;
  border-bottom: 50px solid transparent;
}
```
实现效果如下图：

+ 左上三角 (triangle-topleft)
```CSS
#triangle-topleft {
  width: 0;
  height: 0;
  border-top: 100px solid red;
  border-right: 100px solid transparent;
}
```
实现效果如下图：

+ 右上三角 (triangle-topright)
```CSS
#triangle-topright {
  width: 0;
  height: 0;
  border-top: 100px solid red;
  border-left: 100px solid transparent;
}
```
实现效果如下图：

+ 左下角三角图形 (triangle-bottomleft)
```CSS
#triangle-bottomleft {
  width: 0;
  height: 0;
  border-bottom: 100px solid red;
  border-right: 100px solid transparent;
}
```
实现效果如下图：


+ 右下角三角图形 (triangle-bottomright)
```CSS
#triangle-bottomright {
  width: 0;
  height: 0;
  border-bottom: 100px solid red;
  border-left: 100px solid transparent;
}
```
实现效果如下图：

+ 弧形尾箭头 (curvedarrow)
```CSS
#curvedarrow {
  position: relative;
  width: 0;
  border-top: 90px solid transparent;
  border-right: 90px solid red;
  transform: rotate(10deg) translateX(100%);
}
#curvedarrow:after {
  content: "";
  position: absolute;
  border: 0 solid transparent;
  border-top: 30px solid red;
  border-radius: 200px 0 0 0;
  top: -120px;
  left: -90px;
  width: 120px;
  height: 120px;
  transform: rotate(45deg);
}
```
实现效果如下图：


+ 梯形 (trapezoid)
```CSS
#trapezoid {
  border-bottom: 100px solid red;
  border-left: 25px solid transparent;
  border-right: 25px solid transparent;
  height: 0;
  width: 100px;
}
```
实现效果如下图：


+ 等边四边形 (parallelogram)
```CSS
#parallelogram {
  width: 150px;
  height: 100px;
  transform: skew(20deg);
  background: red;
}
```
实现效果如下图：


+ 六角星 (star-six)
```CSS
#star-six {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 100px solid red;
  position: relative;
}
#star-six:after {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-top: 100px solid red;
  position: absolute;
  content: "";
  top: 30px;
  left: -50px;
}
```
实现效果如下图：


+ 五角星 (star-five)
```CSS
#star-five {
  margin: 50px 0;
  position: relative;
  display: block;
  color: red;
  width: 0px;
  height: 0px;
  border-right: 100px solid transparent;
  border-bottom: 70px solid red;
  border-left: 100px solid transparent;
  transform: rotate(35deg);
}
#star-five:before {
  border-bottom: 80px solid red;
  border-left: 30px solid transparent;
  border-right: 30px solid transparent;
  position: absolute;
  height: 0;
  width: 0;
  top: -45px;
  left: -65px;
  display: block;
  content: '';
  transform: rotate(-35deg);
}
#star-five:after {
  position: absolute;
  display: block;
  color: red;
  top: 3px;
  left: -105px;
  width: 0px;
  height: 0px;
  border-right: 100px solid transparent;
  border-bottom: 70px solid red;
  border-left: 100px solid transparent;
  transform: rotate(-70deg);
  content: '';
}
```
实现效果如下图：


+ 多边形-五边形 (pentagon)
```CSS
#pentagon {
  position: relative;
  width: 54px;
  box-sizing: content-box;
  border-width: 50px 18px 0;
  border-style: solid;
  border-color: red transparent;
}
#pentagon:before {
  content: "";
  position: absolute;
  height: 0;
  width: 0;
  top: -85px;
  left: -18px;
  border-width: 0 45px 35px;
  border-style: solid;
  border-color: transparent transparent red;
}
```
实现效果如下图：


+ 多边形-六边形 (hexagon)
```CSS
#hexagon {
  width: 100px;
  height: 55px;
  background: red;
  position: relative;
}
#hexagon:before {
  content: "";
  position: absolute;
  top: -25px;
  left: 0;
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 25px solid red;
}
#hexagon:after {
  content: "";
  position: absolute;
  bottom: -25px;
  left: 0;
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-top: 25px solid red;
}
```
实现效果如下图：


+ 多边形-八边形 (octagon)
```CSS
#octagon {
  width: 100px;
  height: 100px;
  background: red;
  position: relative;
}
#octagon:before {
  content: "";
  width: 100px;
  height: 0;
  position: absolute;
  top: 0;
  left: 0;
  border-bottom: 29px solid red;
  border-left: 29px solid #fff;
  border-right: 29px solid #fff;
  box-sizing: border-box;
}
#octagon:after {
  content: "";
  width: 100px;
  height: 0;
  position: absolute;
  bottom: 0;
  left: 0;
  border-top: 29px solid red;
  border-left: 29px solid #fff;
  border-right: 29px solid #fff;
  box-sizing: border-box;
}
```
实现效果如下图：

