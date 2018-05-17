#### 变量
- 普通变量
```
$fontSize: 10px;
```
- 默认变量
```
$fontSize: 10px !default;
```
- 修改默认
> 在默认变量之前重新声明变量
```
$fontSize: 15px;
$fontSize: 10px !default;
```
- 局部变量
- 全局变量
> 定义在元素外面的变量；可以使用!global
- 全局变量的影子
> 在局部范围声明一个已经存在于全局范围内的变量；局部变量只会在局部范围内覆盖全局变量。
#### 插值
```
#{}
```
#### 嵌套
- 选择器嵌套
- 属性嵌套
- 伪类嵌套
#### 语句
- @if @else if @else
- @for
```
@for $i from <start> through <end>
@for $i from <start> to <end>
```
> through表示包括end这个数，而to则不包括end这个数
- @while
- @each
```
@each $var in <list>
```
#### 占位符
```
%placeholder
```
#### 使用
> 如果代码块中涉及到变量，建议使用混合宏创建相同的代码块
> 如果代码块不需要变量，而且有一个基类已在文件中存在，那么建议使用Sass的继承
> 占位符是独立定义，不调用是不会在CSS中产生代码
#### 混合宏
- 声明
```
@mixin
```
> 带有多个参数，可以使用“…”来替代
- 调用
```
@include
```
#### 函数
- 字符串函数
```
quote($string)：字符串添加引号
unquote($string)：字符串删除引号
to-upper-case():将字符串小写字母转换成大写字母
to-lower-case():将字符串转换成小写字母
```
- 数字函数
```
percentage($value)：将一个不带单位的数转换成百分比值
round($value)：将数值四舍五入，转换成一个最接近的整数
ceil($value)：将大于自己的小数转换成下一位整数
floor($value)：将一个数去除他的小数部分
abs($value)：返回一个数的绝对值
min($numbers…)：找出几个数值之间的最小值
max($numbers…)：找出几个数值之间的最大值
random(): 获取随机数
```
- 列表函数
```
length($list)：返回一个列表的长度值
nth($list, $n)：返回一个列表中指定的某个标签值
join($list1, $list2, [$separator])：将两个列给连接在一起，变成一个列表
append($list1, $val, [$separator])：将某个值放在列表的最后
zip($lists…)：将几个列表结合成一个多维的列表
index($list, $value)：返回一个值在列表中的位置值
```
- 颜色函数
- Introspection函数
```
type-of($value)：返回一个值的类型
unit($number)：返回一个值的单位
unitless($number)：判断一个值是否带有带位
comparable($number-1, $number-2)：判断两个值是否可以做加、减和合并
```
- 三元函数
```
if($condition,$if-true,$if-false)
```
- map
```
$map:()
```
- Maps
```
map-get($map,$key)：根据给定的 key 值，返回 map 中相关的值
map-merge($map1,$map2)：将两个 map 合并成一个新的 map
map-remove($map,$key)：从 map 中删除一个 key，返回一个新 map
map-keys($map)：返回 map 中所有的 key
map-values($map)：返回 map 中所有的 value
map-has-key($map,$key)：根据给定的 key 值判断 map 是否有对应的 value 值，如果有返回 true，否则返回 false
```
- 自定义函数
```
@function
keywords($args)：返回一个函数的参数，这个参数可以动态的设置 key 和 value
```
#### 规则
- @import
> 引入文件；避免编译：文件名前添加下划线
- @media
> 嵌套css规则
- @extend
> 扩展选择器或占位符
- @at-root
> 跳出根元素
- @debug
> 调试
- @warn
- @error