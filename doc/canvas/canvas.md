### 画布
```
<canvas id="canvas" width="150" height="150"></canvas>
```
### 渲染上下文
```
var canvas = document.getElementById('canvas');
var ctx = canvas.getContext('2d');
```
### 绘制矩形
- 绘制一个填充的矩形
```
fillRect(x, y, width, height)
```
- 绘制一个矩形的边框
```
strokeRect(x, y, width, height)
```
- 清除指定矩形区域，让清除部分完全透明
```
clearRect(x, y, width, height)
```
### 绘制路径
- 新建一条路径，生成之后，图形绘制命令被指向到路径上生成路径
```
beginPath()
```
- 闭合路径之后图形绘制命令又重新指向到上下文中
```
closePath()
```
- 通过线条来绘制图形轮廓
```
stroke()
```
- 通过填充路径的内容区域生成实心的图形
```
fill()
```
- 移动笔触
```
moveTo(x, y)
```
- 线
```
lineTo(x, y)
```
- 圆弧
```
arc(x, y, radius, startAngle, endAngle, anticlockwise)
```
```
arcTo(x1, y1, x2, y2, radius)
```
> radians=(Math.PI/180)*degrees
- 二次贝塞尔曲线
```
quadraticCurveTo(cp1x, cp1y, x, y)
```
- 三次贝塞尔曲线
```
bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)
```
- 矩形
```
rect(x, y, width, height)
```
- Path2D
- SVG paths
### 色彩 Colors
- 设置图形的填充颜色
```
fillStyle = color
```
- 设置图形轮廓的颜色
```
strokeStyle = color
```
### 透明度 Transparency
```
globalAlpha = transparencyValue
```
### 线型 Line styles
- 设置线条宽度
```
lineWidth = value
```
- 设置线条末端样式
```
lineCap = type
butt，round 和 square
```
- 设定线条与线条间接合处的样式
```
lineJoin = type
round, bevel 和 miter
```
- 限制当两条线相交时交接处最大长度
```
miterLimit = value
```
- 返回一个包含当前虚线样式，长度为非负偶数的数组
```
getLineDash()
```
- 设置当前虚线样式
```
setLineDash(segments)
```
- 设置虚线样式的起始偏移量
```
lineDashOffset = value
```
### 渐变 Gradients
```
createLinearGradient(x1, y1, x2, y2)
```
```
createRadialGradient(x1, y1, r1, x2, y2, r2)
```
```
gradient.addColorStop(position, color)
```
### 图案样式 Patterns
```
createPattern(image, type)
repeat，repeat-x，repeat-y 和 no-repeat
```
> 使用 Image 对象的 onload handler 来确保设置图案之前图像已经装载完毕
### 阴影 Shadows
- 设定阴影在 X 轴的延伸距离
```
shadowOffsetX = float
```
- 设定阴影在 Y 轴的延伸距离
```
shadowOffsetY = float
```
- 设定阴影的模糊程度
```
shadowBlur = float
```
- 设定阴影颜色效果
```
shadowColor = color
```
### Canvas 填充规则
```
nonzero 和 evenodd
```
### 绘制文本
- 在指定的(x,y)位置填充指定的文本
```
fillText(text, x, y [, maxWidth])
```
- 在指定的(x,y)位置绘制文本边框
```
strokeText(text, x, y [, maxWidth])
```
### 有样式的文本
```
font = value
```
- 文本对齐选项
```
textAlign = value
start, end, left, right or center
```
- 基线对齐选项
```
textBaseline = value
top, hanging, middle, alphabetic, ideographic, bottom
```
- 文本方向
```
direction = value
ltr, rtl, inherit
```
### 预测量文本宽度
```
measureText()
```
### 绘制图片
```
drawImage(image, x, y)
```
### 缩放 Scaling
```
drawImage(image, x, y, width, height)
```
### 切片 Slicing
```
drawImage(image, sx, sy, sWidth, sHeight, dx, dy, dWidth, dHeight)
```
### 变形 Transformations
- 状态的保存
```
save()
```
- 状态的恢复
```
restore()
```