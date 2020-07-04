# HTML笔记

## 基本标签

- div:用来布局的，没有具体含义，可以理解为"层"。

- hx:标题，从1级到6级标题（大到小，会自动加粗，有默认字号）
- p:表示段落，相当于一个回车。
- br:换行
- hr:分隔线，主要起装饰作用。
  
  <hr width="80%" align="center" color="red" size="7px">可设置分割线宽度颜色高度等
- a:设置超文本链接
  <a href="链接" target=>这里显示一个提示文本</a>
  - target="_blank"：打开新标签
  - target="_self"：默认项，直接跳转

- img:用来加载外部图像  src:用来加载图片路径 alt:图片加载不成功时的提示文字
- span:作用与div一样，用于布局，不同的是div会单独占一行，而span不会。一般用于行内布局。
- ul/ol:列表，前者无序，后者有序。列表内容都用li标签
    ul>li{li$}*3

## 标签属性
1.通常以属性名等于属性值显示。
2.起附加信息的作用。
3.不是所有标签都有属性，例如br标签

<p title="段落" class="content" id="content">这是一个测试</p>

## 文本格式化标签
通过标签来美化文本
1.b和strong都有加粗的效果，且都是行级标签（不会自动换行），但是strong有强调的作用。
注：强调主要用于seo搜索引擎优化时便于提取关键字。
2.i和em使文字倾斜，em具有强调作用，都是行级标签（不会独占一行，且不识别宽高）。简单的倾斜效果用i，比如添加图标等。
3.pre 预格式化文本，保留换行和空格及宽度。但是文字的字号会小一号。（块级标签（在浏览器中独占一行））
4.small和big 分别让文字小一号或者大一号。big在HTML5中已经淘汰了，并没有删除，在开发中尽量不要使用它。
注：浏览器支持的最小字号为12px字，如果要显示比12px还小的文字效果，需要另作处理。
5.sub和sup，设置文本为上标和下标。用来调整文本正常显示的基线，且文字会自动小一号。
<p>X<sub>1</sub>+X<sub>2</sub>=Y</p>
<p>X<sup>2</sup>+Y<sup>2</sup>=Z</p>

## 单双标签
单标记只有一个标签
双标签是成对出现的

## 实体转义
显示结果	描述	实体名称	实体编号
空格	&nbsp ;	&#160 ;
<	小于号	&lt ;	&#60 ;
>	大于号	&gt ;	&#62 ;
&	和号	&amp ;	&#38 ;
"	引号	&quot ;	&#34 ;
’	撇号	&apos ;(IE不支持)	&#39 ;
￠	分（cent）	&cent ;	&#162 ;
£	镑（pound）	&pound ;	&#163 ;
¥	元（yen）	&yen ;	&#165 ;
€	欧元（euro）	&euro ;	&#8364 ;
§	小节	&sect ;	&#167 ;
©	版权（copyright）	&copy ;	&#169 ;
®	注册商标	&reg ;	&#174 ;
™	商标	&trade ;	&#8482 ;
×	乘号	&times ;	&#215 ;
÷	除号	&divide ;	&#247 ;

## 块级元素和行内元素
块级元素（相当于执行了display:block：）：
- 独占一行
- 宽度和高度是可控的，如果没有设置其宽度，将默认铺满整行。
- 其内可以包含块级和行级元素
行内元素（相当于执行了display:inline：）：
- 不会独占一行，与相邻的行级元素占同一行，直到行占满，会自动掉到下一行。
- 宽度和高度不可控
- 其内只能包含行级元素

块级标签准换为行级标签
style="display:inline;"
行级标签转换为块级标签
style="display:block;"


## W3C
万维网联盟（world wide web）

w3c标准由结构、表现、行为三部分组成。

块级元素不能放在<p>中

有几个特殊的块级元素只能包含行级元素，不能包含块级元素（h1 h2 h3 h4 h5 h6 p dt）

块级元素和块级元素并列，行级元素和行级元素并列。

## 语义化标签
明确每个标签的用途

<q> 引用的文本不需要加双引号，浏览器会自动添加
<adress> 为网站添加地址等信息
<caption>为网站添加标题和摘要

## 文件命名规范
项目中不能出现汉字和空格之类的其他符号，文件和目录名一般以字母和下划线组成


## HTML标签属性
标签由标签名、标签属性、和文本内容组成。单标签没有文本内容
标签属性是对标签的一种描述方式
标签属性分通用属性，自有属性和自定义属性。

### 通用属性
所有标签都具有的属性
- id：用来给标签取一个唯一的名称.id名称在一个网页上必须是唯一的。
- class：用来给标签取类名
- style：设置当前标签的行列样式
- title：鼠标移到该标签上的提示文本

### 自定义属性
通常用来传值或者图片的懒加载等方面
格式：data-*

## table属性
table主要用于呈现格式化数据。表格是由行和列组成的。
格式：
  <table>
    <tr><!-- 行 --></tr>
      <td><!-- 列 --></td>
  </table>

### 表格属性
- border 设置边框
  - width  设置表格宽度
  - align  设置表格对齐
  - cellpadding  设置单元格间距
  - cellspacing  设置像素间隙

<th>表头，自动加粗和居中

### 跨行和跨列属性
主要用于绘制复杂表格
- rowspan:

    <table>
        <tr>
            <td rowspan="2" valign="middle<!-- 垂直对齐 -->">01</td>
            <td>02</td>
            <td>03</td>
        </tr>
        <tr>
            <td>02</td>
            <td>03</td>
        </tr>
        <tr>
            <td>01</td>
            <td>02</td>
            <td>03</td>
        </tr>
    </table>
- colspan:同上


### table完整表格
完整表格组成：caption标题，thead(表头),tbody(表体),tfoot(表尾)

## form表单属性
是所有标签最核心标签之一，它是用来实现前后端交互的一个重要标签。
常用属性:
- name:表单名
- action:表单数据提交的地方，通常是一个后台文件名（.jsp/.php/.asp/.py/.aspx）或网址。如果是#，表示提交到当前文件下。
- method:前端提交数据到后端的方法，主要有get和post，默认是get。get会让信息暴露在地址栏，一般用post。

### 表单元素
- input:主要用来输入，或发出指令。
  - <input type="text" /> 供文本输入的单行输入字段
    - placehoder(提示)/name(命名)/minlength(最少输入的字符个数)/maxlength(最多输入的字符个数)/disabled(失效)/readonly(只读)/value(初值，会覆盖placehoder)/patten(正则匹配)
  - <input type="password" />  定义密码字段
    - 属性和text一样
  - <input type="submit" />  定义提交表单数据至表单处理程序的按钮
  - <input type="image" />  定义图片提交按钮
    - 用法与button一样，有一个特殊属性src(用于加载提示图片，用它替换value)
  - <input type="radio" />  定义单选按钮
    - name(必须要有)/value/disabled/readonly/checked(默认选择)
  - <input type="checkbox" />  定义复选框
    - name(必须要有)/value/disabled/readonly/checked(默认选择)
  - <input type="button" />  定义普通按钮，通常用它去调用脚本代码
    - value(代码标题)/disabled(失效)/readonly
  - <input type="reset" />  定义重置按钮，将输入的内容表单所有组件全部清空，还原为初始状态。
  - <input type="file" />  定义文件框

- textarea
  文本域，也可以叫做多行文本框，主要用于输入大批量的内容。
  - name/id/cols(列数)/rows(行数)/placehoder/minlength/maxlengtg/required(必须输入)/value
- button
  普通按钮，具有提交功能，可以单独使用。不写在form中；如果写在form中，有提交功能实现跳转(与submit效果一致)，主要用于调用js代码。
- select
  下拉列表框，默认用于单项选择。用option呈现每个选项。
  <lable for="">提示语</lable><!-- 提示用 -->
  - multiple(实现多选)/size(显示项数)

## iframe框架属性
框架集，用来将多个网页文件组成一个文件。
- src:引入的外部html文件
- name:框架名
  - 
- width:宽度
- height:高度
- frameborder：是否有边框(1/0)
- scrolling：滚动条(yes/no/auto)
- marginheight：框架顶部和底端的距离(%/px)
- marginwidth：框架左右的距离(%/px)



