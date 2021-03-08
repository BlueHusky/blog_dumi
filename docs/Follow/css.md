---
nav:
  title: css
group:
  title: css
---

1、标准盒模型与 ie 盒子模型

- 标准盒子模型：宽度=内容的宽度（content）+ border + padding + margin
- 低版本 IE 盒子模型：宽度=内容宽度（content+border+padding）+ margin

2、box-sizing 属性

- context-box ：W3C 的标准盒子模型，设置元素的 height/width 属性指的是 content 部分的高/宽
- border-box ： IE 传统盒子模型。设置元素的 height/width 属性指的是 border + padding + content 部分的高/宽

3、CSS 选择器及优先级

- ID 选择器、类选择器、标签（类型）选择器、属性选择器、伪类伪元素选择器、通配符选择器、运算符
- 优先级：内联：1000，ID 选择器：100，class 选择符：10，元素选择符：1，!important 声明的样式优先级最高，如果优先级相同，则选择最后出现的样式
