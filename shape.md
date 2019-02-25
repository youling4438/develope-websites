收藏一些有意思的``CSS``代码

## 使用``CSS``绘制的基本图形

+  正方形 (square)
```CSS
#square {
  width: 100px;
  height: 100px;
  background: #f09199;
}
```
实现效果如下图：

![square ](https://raw.githubusercontent.com/youling4438/develope-websites/master/images/square.png "square")

+ 长方形 (rectangle)
```CSS
#rectangle {
  width: 200px;
  height: 100px;
  background: #f09199;
}
```
实现效果如下图：

![rectangle ](https://raw.githubusercontent.com/youling4438/develope-websites/master/images/rectangle.png "rectangle")

+ 正圆 (circle)
```CSS
#circle {
  width: 100px;
  height: 100px;
  background: #f09199;
  border-radius: 50%
}
```
实现效果如下图：

+ 椭圆 (oval)
```CSS
#oval {
  width: 200px;
  height: 100px;
  background: #f09199;
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
  border-bottom: 100px solid #f09199;
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
  border-top: 100px solid #f09199;
}
```
实现效果如下图：

+ 方向朝左的三角 (triangle-left)
```CSS
#triangle-left {
  width: 0;
  height: 0;
  border-top: 50px solid transparent;
  border-right: 100px solid #f09199;
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
  border-left: 100px solid #f09199;
  border-bottom: 50px solid transparent;
}
```
实现效果如下图：

+ 左上三角 (triangle-topleft)
```CSS
#triangle-topleft {
  width: 0;
  height: 0;
  border-top: 100px solid #f09199;
  border-right: 100px solid transparent;
}
```
实现效果如下图：

+ 右上三角 (triangle-topright)
```CSS
#triangle-topright {
  width: 0;
  height: 0;
  border-top: 100px solid #f09199;
  border-left: 100px solid transparent;
}
```
实现效果如下图：

+ 左下角三角图形 (triangle-bottomleft)
```CSS
#triangle-bottomleft {
  width: 0;
  height: 0;
  border-bottom: 100px solid #f09199;
  border-right: 100px solid transparent;
}
```
实现效果如下图：


+ 右下角三角图形 (triangle-bottomright)
```CSS
#triangle-bottomright {
  width: 0;
  height: 0;
  border-bottom: 100px solid #f09199;
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
  border-right: 90px solid #f09199;
  transform: rotate(10deg) translateX(100%);
}
#curvedarrow:after {
  content: "";
  position: absolute;
  border: 0 solid transparent;
  border-top: 30px solid #f09199;
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
  border-bottom: 100px solid #f09199;
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
  background: #f09199;
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
  border-bottom: 100px solid #f09199;
  position: relative;
}
#star-six:after {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-top: 100px solid #f09199;
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
  color: #f09199;
  width: 0px;
  height: 0px;
  border-right: 100px solid transparent;
  border-bottom: 70px solid #f09199;
  border-left: 100px solid transparent;
  transform: rotate(35deg);
}
#star-five:before {
  border-bottom: 80px solid #f09199;
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
  color: #f09199;
  top: 3px;
  left: -105px;
  width: 0px;
  height: 0px;
  border-right: 100px solid transparent;
  border-bottom: 70px solid #f09199;
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
  border-color: #f09199 transparent;
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
  border-color: transparent transparent #f09199;
}
```
实现效果如下图：


+ 多边形-六边形 (hexagon)
```CSS
#hexagon {
  width: 100px;
  height: 55px;
  background: #f09199;
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
  border-bottom: 25px solid #f09199;
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
  border-top: 25px solid #f09199;
}
```
实现效果如下图：


+ 多边形-八边形 (octagon)
```CSS
#octagon {
  width: 100px;
  height: 100px;
  background: #f09199;
  position: relative;
}
#octagon:before {
  content: "";
  width: 100px;
  height: 0;
  position: absolute;
  top: 0;
  left: 0;
  border-bottom: 29px solid #f09199;
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
  border-top: 29px solid #f09199;
  border-left: 29px solid #fff;
  border-right: 29px solid #fff;
  box-sizing: border-box;
}
```
实现效果如下图：


+ 爱心❥ (heart)
```CSS
#heart {
  position: relative;
  width: 100px;
  height: 90px;
}
#heart:before,
#heart:after {
  position: absolute;
  content: "";
  left: 50px;
  top: 0;
  width: 50px;
  height: 80px;
  background: #f09199;
  border-radius: 50px 50px 0 0;
  transform: rotate(-45deg);
  transform-origin: 0 100%;
}
#heart:after {
  left: 0;
  transform: rotate(45deg);
  transform-origin: 100% 100%;
}
```
实现效果如下图：


+ 无限 (infinity)
```CSS
#infinity {
  position: relative;
  width: 212px;
  height: 100px;
  box-sizing: content-box;
}
#infinity:before,
#infinity:after {
  content: "";
  box-sizing: content-box;
  position: absolute;
  top: 0;
  left: 0;
  width: 60px;
  height: 60px;
  border: 20px solid #f09199;
  border-radius: 50px 50px 0 50px;
  transform: rotate(-45deg);
}
#infinity:after {
  left: auto;
  right: 0;
  border-radius: 50px 50px 50px 0;
  transform: rotate(45deg);
}
```
实现效果如下图：


+ 菱形方块 (diamond)
```CSS
#diamond {
  width: 0;
  height: 0;
  border: 50px solid transparent;
  border-bottom-color: #f09199;
  position: relative;
  top: -50px;
}
#diamond:after {
  content: '';
  position: absolute;
  left: -50px;
  top: 50px;
  width: 0;
  height: 0;
  border: 50px solid transparent;
  border-top-color: #f09199;
}
```
实现效果如下图：


+ 菱形盾构 (diamond-shield)
```CSS
#diamond-shield {
  width: 0;
  height: 0;
  border: 50px solid transparent;
  border-bottom: 20px solid #f09199;
  position: relative;
  top: -50px;
}
#diamond-shield:after {
  content: '';
  position: absolute;
  left: -50px;
  top: 20px;
  width: 0;
  height: 0;
  border: 50px solid transparent;
  border-top: 70px solid #f09199;
}
```
实现效果如下图：


+ 方块菱形-窄 (diamond-narrow)
```CSS
#diamond-narrow {
  width: 0;
  height: 0;
  border: 50px solid transparent;
  border-bottom: 70px solid #f09199;
  position: relative;
  top: -50px;
}
#diamond-narrow:after {
  content: '';
  position: absolute;
  left: -50px;
  top: 70px;
  width: 0;
  height: 0;
  border: 50px solid transparent;
  border-top: 70px solid #f09199;
}
```
实现效果如下图：


+ 切割菱形-钻石般 (cut-diamond)
```CSS
#cut-diamond {
  border-style: solid;
  border-color: transparent transparent #f09199 transparent;
  border-width: 0 25px 25px 25px;
  height: 0;
  width: 50px;
  box-sizing: content-box;
  position: relative;
  margin: 20px 0 50px 0;
}
#cut-diamond:after {
  content: "";
  position: absolute;
  top: 25px;
  left: -25px;
  width: 0;
  height: 0;
  border-style: solid;
  border-color: #f09199 transparent transparent transparent;
  border-width: 70px 50px 0 50px;
}
```
实现效果如下图：


+ 鸡蛋形状 (egg)
```CSS
#egg {
  display: block;
  width: 126px;
  height: 180px;
  background-color: #f09199;
  border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
}
```
实现效果如下图：


+ 吃豆人 (pacman)
```CSS
#pacman {
  width: 0px;
  height: 0px;
  border-right: 60px solid transparent;
  border-top: 60px solid #f09199;
  border-left: 60px solid #f09199;
  border-bottom: 60px solid #f09199;
  border-top-left-radius: 60px;
  border-top-right-radius: 60px;
  border-bottom-left-radius: 60px;
  border-bottom-right-radius: 60px;
}
```
实现效果如下图：


+ 带尖角的说话泡泡 (pacman)
```CSS
#talkbubble {
  width: 120px;
  height: 80px;
  background: #f09199;
  position: relative;
  -moz-border-radius: 10px;
  -webkit-border-radius: 10px;
  border-radius: 10px;
}
#talkbubble:before {
  content: "";
  position: absolute;
  right: 100%;
  top: 26px;
  width: 0;
  height: 0;
  border-top: 13px solid transparent;
  border-right: 26px solid #f09199;
  border-bottom: 13px solid transparent;
}
```
实现效果如下图：


+ 十二星 (burst-12)
```CSS
#burst-12 {
  background: #f09199;
  width: 80px;
  height: 80px;
  position: relative;
  text-align: center;
}
#burst-12:before,
#burst-12:after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  height: 80px;
  width: 80px;
  background: #f09199;
}
#burst-12:before {
  transform: rotate(30deg);
}
#burst-12:after {
  transform: rotate(60deg);
}

```
实现效果如下图：


+ 八角形 (burst-8)
```CSS
#burst-8 {
  background: #f09199;
  width: 80px;
  height: 80px;
  position: relative;
  text-align: center;
  transform: rotate(20deg);
}
#burst-8:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  height: 80px;
  width: 80px;
  background: #f09199;
  transform: rotate(135deg);
}
```
实现效果如下图：


+ 阴阳八卦 (yin-yang)
```CSS
#yin-yang {
  width: 96px;
  height: 48px;
  background: #fff;
  border-color: #f09199;
  border-style: solid;
  border-width: 2px 2px 50px 2px;
  border-radius: 100%;
  position: relative;
}
#yin-yang:before {
  content: "";
  position: absolute;
  top: 50%;
  left: 0;
  background: #fff;
  border: 18px solid #f09199;
  border-radius: 100%;
  width: 12px;
  height: 12px;
}
#yin-yang:after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  background: #f09199;
  border: 18px solid #fff;
  border-radius: 100%;
  width: 12px;
  height: 12px;
}
```
实现效果如下图：


+ 徽章缎带 (badge-ribbon)
```CSS
#badge-ribbon {
  position: relative;
  background: #f09199;
  height: 100px;
  width: 100px;
  border-radius: 50px;
}
#badge-ribbon:before,
#badge-ribbon:after {
  content: '';
  position: absolute;
  border-bottom: 70px solid #f09199;
  border-left: 40px solid transparent;
  border-right: 40px solid transparent;
  top: 70px;
  left: -10px;
  transform: rotate(-140deg);
}
#badge-ribbon:after {
  left: auto;
  right: -10px;
  transform: rotate(140deg);
}
```
实现效果如下图：


+ bilibili电视机 (tv)
```CSS
#tv {
  position: relative;
  width: 200px;
  height: 150px;
  margin: 20px 0;
  background: #f09199;
  border-radius: 50% / 10%;
  color: white;
  text-align: center;
  text-indent: .1em;
}
#tv:before {
  content: '';
  position: absolute;
  top: 10%;
  bottom: 10%;
  right: -5%;
  left: -5%;
  background: inherit;
  border-radius: 5% / 50%;
}
```
实现效果如下图：


+ V形线条 (chevron)
```CSS
#chevron {
  position: relative;
  text-align: center;
  padding: 12px;
  margin-bottom: 6px;
  height: 60px;
  width: 200px;
}
#chevron:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 51%;
  background: #f09199;
  transform: skew(0deg, 6deg);
}
#chevron:after {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 50%;
  background: #f09199;
  transform: skew(0deg, -6deg);
}
```
实现效果如下图：


+ 放大镜 (magnifying-glass)
```CSS
#magnifying-glass {
  font-size: 10em;
  display: inline-block;
  width: 0.4em;
  box-sizing: content-box;
  height: 0.4em;
  border: 0.1em solid #f09199;
  position: relative;
  border-radius: 0.35em;
}
#magnifying-glass:before {
  content: "";
  display: inline-block;
  position: absolute;
  right: -0.25em;
  bottom: -0.1em;
  border-width: 0;
  background: #f09199;
  width: 0.35em;
  height: 0.08em;
  transform: rotate(45deg);
}
```
实现效果如下图：


+ 月儿弯弯 (moon)
```CSS
#moon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  box-shadow: 15px 15px 0 0 #f09199;
}
```
实现效果如下图：


+ 旗帜 (flag)
```CSS
#flag {
  width: 110px;
  height: 56px;
  padding-top: 15px;
  position: relative;
  background: #f09199;
}
#flag:after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 0;
  height: 0;
  border-bottom: 13px solid #fff;
  border-left: 55px solid transparent;
  border-right: 55px solid transparent;
}
```
实现效果如下图：


+ 圆锥体 (cone)
```CSS
#cone {
  width: 0;
  height: 0;
  border-left: 70px solid transparent;
  border-right: 70px solid transparent;
  border-top: 100px solid #f09199;
  border-radius: 50%;
}
```
实现效果如下图：


+ 十字架 (cross)
```CSS
#cross {
  background: #f09199;
  height: 100px;
  position: relative;
  width: 20px;
}
#cross:after {
  background: #f09199;
  content: "";
  height: 20px;
  left: -40px;
  position: absolute;
  top: 40px;
  width: 100px;
}
```
实现效果如下图：


+ 棒球踏板形状 (base)
```CSS
#base {
  background: #f09199;
  display: inline-block;
  height: 55px;
  margin-left: 20px;
  margin-top: 55px;
  position: relative;
  width: 100px;
}
#base:before {
  border-bottom: 35px solid #f09199;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  content: "";
  height: 0;
  left: 0;
  position: absolute;
  top: -35px;
  width: 0;
}
```
实现效果如下图：


+ 长长的指向图形 (pointer)
```CSS
#pointer {
  width: 200px;
  height: 40px;
  position: relative;
  background: #f09199;
}
#pointer:after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 0;
  height: 0;
  border-left: 20px solid white;
  border-top: 20px solid transparent;
  border-bottom: 20px solid transparent;
}
#pointer:before {
  content: "";
  position: absolute;
  right: -20px;
  bottom: 0;
  width: 0;
  height: 0;
  border-left: 20px solid #f09199;
  border-top: 20px solid transparent;
  border-bottom: 20px solid transparent;
}
```
实现效果如下图：


+ 锁 (lock)
```CSS
#lock {
  font-size: 8px;
  position: relative;
  width: 18em;
  height: 13em;
  border-radius: 2em;
  top: 10em;
  box-sizing: border-box;
  border: 3.5em solid #f09199;
  border-right-width: 7.5em;
  border-left-width: 7.5em;
  margin: 0 0 6rem 0;
}
#lock:before {
  content: "";
  box-sizing: border-box;
  position: absolute;
  border: 2.5em solid #f09199;
  width: 14em;
  height: 12em;
  left: 50%;
  margin-left: -7em;
  top: -12em;
  border-top-left-radius: 7em;
  border-top-right-radius: 7em;
}
#lock:after {
  content: "";
  box-sizing: border-box;
  position: absolute;
  border: 1em solid #f09199;
  width: 5em;
  height: 8em;
  border-radius: 2.5em;
  left: 50%;
  top: -1em;
  margin-left: -2.5em;
}
```
实现效果如下图：

