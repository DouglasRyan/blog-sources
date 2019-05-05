---
title: flex布局
date: 2019-05-05 20:35:20
tags: Summary CSS
---
##  Flex模型
[![A6jWHs.png](https://s2.ax1x.com/2019/04/02/A6jWHs.png)](https://imgchr.com/i/A6jWHs)
元素表现为 flex 框时，它们沿着两个轴来布局：
- **主轴（main axis）**是沿着 flex 元素放置的方向延伸的轴（比如页面上的横向的行、纵向的列）。该轴的开始和结束被称为 main start 和 main end。
- **交叉轴（cross axis）**是垂直于 flex 元素放置方向的轴。该轴的开始和结束被称为 cross start 和 cross end。
- 设置了 display: flex 的父元素被称之为 **flex 容器（flex container）**。`.container`
- 在 flex 容器中的弹性盒子元素被称之为 **flex 项（flex item）**。`.item`

### 一、flex container属性

1. **display**
	给flex容器设置display属性
	
```
.container{
	display:flex	|	inline-flex
}
```

2. **flex-direction**
设置主轴的方位和方向。

```
.container {
    flex-direction: row(default) | row-reverse | column | column-reverse;
}
```

3. **flex-wrap**
设置换行

```
.container {
    flex-wrap: nowrap(default) | wrap | wrap-reverse;
}
```

4. **flex-flow**
集合属性，同时定义flex-direction和flex-wrap。

```
.container {
    flex-flow: row-reverse wrap-reverse;
}
```

5. **justify-content**
设置行内的项目如何水平对齐

```
.container {
    justify-content: flex-start(default) | flex-end | center | space-between | space-around | space-evenly;
}
```

6. **align-items**
设置行内的项目如何垂直对齐。

```
.container {
    align-items: stretch(default) | flex-start | flex-end | center | baseline;
}
```

7. **align-content**
如果容器的交叉轴方向有富余空间，设置每行应该如何垂直对齐。

```
.container {
    align-content: stretch(default) | flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

### 二、flex item属性
1. **order**
设置弹性项目在布局时的顺序。

```
.item {
    order: <integer>;
}
```

- 默认值是0
- order 值大的 flex 项比 order 值小的在显示顺序中更靠后。

3. **flex-grow**
设置flex项怎么瓜分行内的富余空间。定义flex项（flex item）的拉伸因子。

```
.item {
    flex-grow: <number>; 
}
```

- 默认值是0。
- 按照总份数瓜分富余空间。

4. **flex-shrink**
设置flex项怎么承担行内的负债空间。定义flex项（flex item）的收缩规则。

```
.item {
    flex-shrink: <number>; 
}
```

- 默认值是1。
- 按照总份数承担行内的负债空间。

5. **flex-basis**
设置了 flex 元素在主轴方向上的初始大小。它是width属性的替代品，优先级比width高。

```
.item {
    flex-basis: <'width'>;
}
```

- 默认值是auto
- 依赖flex项目的content

6. **flex**
一个集合属性，可以同时设置flex-grow、flex-shrink和flex-basis。

```
.item {
    flex: <'flex-grow'> | <'flex-grow'> <'flex-shrink'> <'flex-basis'>;
}
```

7. **align-self**
设置弹性项目自身在行内的垂直对齐方式。

```
.item {
    align-self: auto(default) | stretch | flex-start | flex-end | center | baseline;
}
```

- 默认值是auto。