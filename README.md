
#详解CSS中的长度单位

- CSS上的测量单位繁多,有至少10种不同的测量单位。
但是每种单位却又各司其职，所以我们不得不深入了解他们。

##绝对长度单位

- 绝对单位在物理世界真实测量的数字表示。这些单位跟设备分辨率无关，所以在不同分辨率上的设备应用效果较差。通常用于印刷业。绝对长度单位包括

    - cm(厘米)

    - mm(毫米)

    - in(英寸)

    - pc(派卡)

    - pt(点)

    - px(像素)

- 绝对单位里像素（px）使用最为广泛。一像素点通常被理解为在屏幕上的一个点，但实际情况比这个复杂得多.它是最小的测量单位，通常作为其它单位的基准。
其它单位，像英寸，毫米，厘米，表示得是物理尺寸。
点（pt），表示1/72英寸
派卡（pc）,球1/6英寸。
下面一段CSS，使用了6种不同的绝对长度单位：

```javascript
p {
border-top: 0.5in solid blue;
border-bottom: 18mm solid green;
border-left: 1cm solid red;
border-right: 40px solid black;
letter-spacing: 0.4pc;
font-size: 20pt;
}
```


##相对长度单位
- 故名思意，没有固定的值。它们的值都是相对于其它预定值或特征。相对单位，可以根据其它一些基本参数，为元素的提供合适的值，这些属性如width,height,font-size等。
这些单位推荐在两种场景下使用。


- ex（x的高度）

- ch（字符）

- em（因打印em而得名，但不同）

- rem（根字体）


X-height(ex) 和 字符（ch）单位

- 单位ex，很少用于开发。 1ex等于使用字体中小写字母 ' x ' 的大小。在英文中，大多数情况1ex差不多等于0.5em。但当你改变了字体，如下设置字体的高度可以相当于em：

```javascript
p {
font-size: 2ex;
}
```
- 单位ch，是根据‘o’字符的来定义的。1ch是通过测量字体中字符'o'来定义 是根据‘0’字符的来定义的。1ch是通过测量字体中字符'0'来定义

```javascript
p {
margin: 2ch;
}
Em
```

- 单位em，等于父元素字体大小或基础字体大小。如果你的父元素字体大小为20px，那么在所有子元素中，1em=20px（译者注：这里元素本身不能设置字体大小）。子元素字体大小可以根据基础字体大小来调整，值可以为小数。
下面是演示：


```javascript
body {
text-align: center;
}
.parent {
font-size: 20px;
}
.child {
font-size: 1.5em;
}
.p {
font-size: 14px;
padding-top: 130px;
}
```

##视口相对长度单位
- 视口相对长度是根据视图窗口或视口的宽和高来确定的。
视图窗口或视口是屏幕可见区域或屏幕上的框架空间区域。
视口相对单位包括：

    - vw:视口宽度(viewport width)

    - vh:视口高度(viewport height)

    - vmin:视口宽度或高度，选择小的那个

    - vmax:视口宽度或高度，选择大的那个

    - vh和vw

- vh主要取决于视口的高度，1vh等于视口高度的1%，这主要用在元素要根据视口高度进行缩放时。例如：如果视口高度为400px，1vh=400/100=4px，如果视口高为800px，1vh=8px

- vw和vh相同，不过它是依赖于视口宽度的。

- vmin和vmax

- vmin和vmax是差不多的两个单位，都是取决于视口宽度和高度的情况。vmin选取小的那个，vmax选取大的那个。对于1vmin,1vmax的值的计算和vw,vh相同。

##浏览器支持情况

- em,ex,px,cm,mm,in,pt,pc
- 所有浏览器都支持，包括旧的IE
    - ch
    - Firefox, Chrome 27+, IE 9+, Safari 7+, and Opera 20+.
    - rem
    - 所有现在浏览器，及IE9+。需要兼容小于IE9的情况，可以使用REM-- - - - unit-polyfill
    - vw,wh,vmin
    - Chrome 20+, IE 9+, Firefox 19+, Safari 6+, Opera 20+. IE中支持的vmin不是标准语法。可以使用 vminpoly 或 use -prefix-free插件。
vmax
Chrome 20+, Firefox 19+, and Opera 20+, and Safari 6.1+.IE不兼容，可以使用viewport-units-buggyfill进行兼容。

##英文原文

- [A Look at Length Units in CSS](https://www.sitepoint.com/look-at-length-units-in-css/)
