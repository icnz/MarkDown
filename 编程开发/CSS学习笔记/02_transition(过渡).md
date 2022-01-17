### transition

> 定义

**检索或设置对象变换时的过渡。**
transition可以为一个元素在不同状态之间切换的时候定义不同的过渡效果，其是 transition-property，transition-duration，transition-timing-function 和 transition-delay 的一个简写属性。
transition适用于所有元素，包含伪对象:after和:before。
可以为同一元素的多个属性定义过渡效果。
对应的脚本特性为**transition**。

> 语法

```css
transition：[ transition-property ] || [ transition-duration ] || [ transition-timing-function ] || [ transition-delay ]

[ transition-property ]：检索或设置对象中的参与过渡的属性
[ transition-duration ]：检索或设置对象过渡的持续时间
[ transition-timing-function ]：检索或设置对象中过渡的动画类型
[ transition-delay ]：检索或设置对象延迟过渡的时间
```

> 示例

```css
缩写方式:
transition:border-color .5s ease-in .1s, background-color .5s ease-in .1s, color .5s ease-in .1s;
拆分方式：
transition-property:border-color, background-color, color;
transition-duration:.5s;
transition-timing-function:ease-in;
transition-delay:.1s;

如果需要定义多个过渡属性且不想指定具体是哪些属性过渡，同时其他属性只有一个参数值，据此可以对上面的例子进行缩写：
缩写方式：
transition:all .5s ease-in .1s;
拆分方式：
transition-property:all;
transition-duration:.5s;
transition-timing-function:ease-in;
transition-delay:.1s;
```



### transition-property属性

> 定义

**检索或设置对象中的参与过渡的属性。**
默认值为：all。默认为所有可以进行过渡的css属性。
如果提供多个属性值，以逗号进行分隔。
对应的脚本特性为**transitionProperty**。

> 语法

```css
transition-property：all | none | <property>[ ,<property> ]*

all：所有可以进行过渡的css属性
none：不指定过渡的css属性
<property>：指定要进行过渡的css属性
```

> 有过渡效果的属性

| 属性名称            | 类型                         |
| :------------------ | :--------------------------- |
| background-color    | color                        |
| background-image    | only gradients               |
| background-position | percentage, length           |
| border-bottom-color | color                        |
| border-bottom-width | length                       |
| border-color        | color                        |
| border-left-color   | color                        |
| border-left-width   | length                       |
| border-right-color  | color                        |
| border-right-width  | length                       |
| border-spacing      | length                       |
| border-top-color    | color                        |
| border-top-width    | length                       |
| border-width        | length                       |
| bottom              | length, percentage           |
| color               | color                        |
| crop                | rectangle                    |
| font-size           | length, percentage           |
| font-weight         | number                       |
| grid-*              | various                      |
| height              | length, percentage           |
| left                | length, percentage           |
| letter-spacing      | length                       |
| line-height         | number, length, percentage   |
| margin-bottom       | length                       |
| margin-left         | length                       |
| margin-right        | length                       |
| margin-top          | length                       |
| max-height          | length, percentage           |
| max-width           | length, percentage           |
| min-height          | length, percentage           |
| min-width           | length, percentage           |
| opacity             | number                       |
| outline-color       | color                        |
| outline-offset      | integer                      |
| outline-width       | length                       |
| padding-bottom      | length                       |
| padding-left        | length                       |
| padding-right       | length                       |
| padding-top         | length                       |
| right               | length, percentage           |
| text-indent         | length, percentage           |
| text-shadow         | shadow                       |
| top                 | length, percentage           |
| vertical-align      | keywords, length, percentage |
| visibility          | visibility                   |
| width               | length, percentage           |
| word-spacing        | length, percentage           |
| z-index             | integer                      |
| zoom                | number                       |



### transition-duration属性

> 定义

**检索或设置对象过渡的持续时间。**
默认值为：0。如果提供多个属性值，以逗号进行分隔。
对应的脚本特性为**transitionDuration**。

> 语法

```css
transition-duration：<time>[ ,<time> ]*

<time>：指定对象过渡的持续时间
```



### transition-timing-function属性

> 定义

**检索或设置对象中过渡的动画类型。**
默认值为：ease。如果提供多个属性值，以逗号进行分隔。
对应的脚本特性为**transitionTimingFunction**。

> 语法

```css
transition-timing-function：linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier(<number>, <number>, <number>, <number>)[ ,linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier(<number>, <number>, <number>, <number>) ]*

linear：线性过渡。等同于贝塞尔曲线(0.0, 0.0, 1.0, 1.0)
ease：平滑过渡。等同于贝塞尔曲线(0.25, 0.1, 0.25, 1.0)
ease-in：由慢到快。等同于贝塞尔曲线(0.42, 0, 1.0, 1.0)
ease-out：由快到慢。等同于贝塞尔曲线(0, 0, 0.58, 1.0)
ease-in-out：由慢到快再到慢。等同于贝塞尔曲线(0.42, 0, 0.58, 1.0)
cubic-bezier(<number>, <number>, <number>, <number>)：特定的贝塞尔曲线类型，4个数值需在[0, 1]区间内
```



### transition-delay属性

> 定义

**检索或设置对象延迟过渡的时间。**
默认值为：0。如果提供多个属性值，以逗号进行分隔。
对应的脚本特性为**transitionDelay**。

> 语法

```css
transition-delay：<time>[ ,<time> ]*

<time>：指定对象过渡的延迟时间
```



