# CSS

层叠样式表，又称串样式列表，由w3c定义和维护的标准，一种用来结构化文档添加样式的计算机语言。

css能对网页中元素位置的排版进行像素级精确控制，支持所有字体字号样式，拥有对网页对象和模型样式编辑的能力。

> 使用CSS可以让HTML和CSS分离，方便维护。

### 基本语法

```
选择器 {
	属性: 属性值;
}

selector {property:value}
```

- selector选择器通常是您需要改变样式的HTML元素
- 每条声明由一个属性和一个属性值组成
- 属性是希望设置的样式属性，每个属性都有一个属性值
- 属性和属性值被冒号分开

### css引用方式

> 行间样式、内部样式、外部样式、导入外部样式。

行间样式：直接在标签上书写样式

内部样式：在文件的内部书写样式

```
<style>
	样式内容
</style>
```

外部样式：

1. 先创建一个css文件
2. 用link标签引入这个文件

导入外部样式：

1. 先创建一个css文件
2. 在style标签中用import导入这个样式文件

```
@import "文件"
```

#### 四种css引用方式的区别

行间样式只作用于当前标签，内部标签作用于当前文件，外部样式可以被多个文件引用。

在实际项目开发中，最好使用外部样式。

外部样式分为link引入和import引入。

这两种方式区别：

1. link加载css外还可以定义rss等其他事物，@import属于css范畴，只能加载css。
2. link引用css时，在页面载入同时加载；@import需要页面完全载入后再加载。
3. link是xhtml标签，无兼容问题。@import是在css2.1提出的，低版本的浏览器不支持。
4. link支持使用js控制DOM改变样式，@import不支持。

### CSS选择器

1. “*”：匹配html中所有元素（性能比较差）
2. 标签选择器：用来匹配对应的标签。
3. 类选择器：用来匹配class命名的标签
4. ID选择器：用来选择用id命名的标签
5. 派出选择器：根据上下文选择的标签
6. 伪类选择器

```html
    *{
    }

    span{
    }

    .box{
    }

    #content{
    }

	.box li{
	}
```

### 选择器分组

让多个选择器（元素）具有相同的样式，一般用于设置公共样式。

```
h1,h2,h3{font-size:20px;}
```

### 选择器的继承

子元素可以继承父元素的样式，反之不可以。（子元素可以改写父元素传过来的样式）

### 优先级

外部样式<内部样式<内联样式

## CCS字体

### font-size 字号

- ｛number+px}：固定尺寸像素
- ｛number+%}：其百分比取值基于父对象中字体的尺寸大小

### font-family字体

```
｛font-family:Courier,"Courier New",monospace;｝
字体中有括号用双引号隔开，第一个为字体，后者为备用字体。
```

### font-style样式

- normal：默认值
- italic：斜体。对于没有斜体变量的特殊字符将应用oblique。
- oblique：倾斜的字体

### font-weight加粗

- normal：默认值
- bold:粗体
- bolder：比bold粗
- lighter：比normal粗
- ｛100-900｝：定义由粗到细的字符。normal是400,700是bold。

### line-height行高

- normal：默认
- ｛name+px｝:指定行高为长度像素
- ｛name｝：指定行高为字体大小的倍数

### color文字颜色

- name：指定color
- rgb：指定颜色的RGB值
- ｛颜色16进制｝

### text-decoration文字修饰

- normal：默认值无修饰
- underline：下划线
- libe-through：贯穿线
- overline：上划线

### text-align文本对齐方式

- left：左对齐
- center：居中对齐
- right：右对齐

### text-transform字母大小写

- none：默认值
- capitalize：将每个单词的第一个字母转换成大写
- uppercase：转换成大写
- lowercase：转换成小写

### text-indent文本缩进

- {number+px}：首行缩进number像素
- {number+em}：首行缩进number字符



### TIP

font复合属性：

​	font：font-style font-variant font-weight font-size/line-hight font-family

	1. 注意属性值的位置顺序
 	2. 除了font-size和font-family之外，其它任何一个属性值都可以省略。
 	3. font-variant：normal/small-caps（让大写字母变得小一些）



## CSS背景

- background-color：背景色（transparent/color)

- background-image:背景图（none/url）

- background-repeat：背景图图像的铺排方式（repeat/no-repeat/repeat-x/repeat-y)

- background-position:背景图像位置（{x-number/top/center/bottom} {y-number/left/center/right} ）  *如果只用一个参数，那么另一个参数默认为50%*

- background-attachment:背景图像的滚动位置（scroll/fixed）

- background:设置背景的复合写法

  color image repeat attachment position

## CSS伪类选择器

伪类：专门用来表示元素的一个特殊状态。

常用伪类选择器：

- a标签的伪类：:link/:visited/:hover/:active
- :focus 获得焦点
- :first-child/:last-child/:nth-child(number)

## 属性选择器

[属性名]：包含有指定属性名的元素（常用）

[属性名=值]：属性名的值为指定值的元素（常用）

[属性名~=值]：属性名的值包含指定值的元素

[属性名^=值]：属性名的值以指定值开头元素

[属性名$=值]：属性名的值以指定值结尾元素

## 关系选择器

1. 空格：后代选择器
2. “>”：只选择儿子元素
3. “+”：兄弟选择

## CSS伪元素

伪类和伪元素是用来修饰不在文档树中的部分

:before/:after/:first-letter/:first-line  :前面可以是一个冒号也可以是双冒号

::selection/::placeholder/::backdrop：前面只能是双冒号

 