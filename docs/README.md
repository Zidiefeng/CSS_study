# CSS3

狂神说Java系列-个人学习笔记


## CSS简介

- [ ]  [P11、CSS的简单介绍09:06](https://www.bilibili.com/video/BV1YJ411a7dy?p=1)

### 前端3大部分

- Html - 结构
- CSS - 表现，表皮
- JavaScript - 动态交互

### 如何学习

- CSS是什么
- CSS怎么用-快速入门
- CSS选择器（如何定位，重难点）
- 美化网页（文字，阴影，超链接，列表，渐变）
- 盒子模型
- 浮动
- 定位
- 网页动画（特效,这里不是重点）

### 学习资源

- 菜鸟CSS3： [https://www.runoob.com/css3/css3-tutorial.html](https://www.runoob.com/css3/css3-tutorial.html)
- w3c school:
[https://www.w3cschool.cn/css/](https://www.w3cschool.cn/css/)
[https://www.w3schools.com/css/default.asp](https://www.w3schools.com/css/default.asp)

### 前端

- 即使会了CSS，还是不行，差美工，大量练习（仿网站）

- [ ]  [P22、什么是CSS和发展史08:53](https://www.bilibili.com/video/BV1YJ411a7dy?p=2)

### 什么是CSS

- CSS: Cascading style sheet: 层叠样式表
- 表现层：美化网页
- 包括：字体，颜色，边距，高度，宽度，背景图片，网页浮动，网页定位
- Inspect

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled.png)

### CSS发展史

- CSS 1.0: 基本
- CSS 2.0：DIV（自定义块） + CSS，HTML与CSS结构分离的思想，网页变得简单，便于SEO
- CSS 2.1：浮动，定位
- CSS 3.0：最新，圆角边框，动画，浏览器兼容性，阴影...

- [ ]  [P33、CSS的快速入门及优势10:01](https://www.bilibili.com/video/BV1YJ411a7dy?p=3)

### 快速入门

- style
- 格式
    - 项目css
    - 不需要src
    - 每一个子dir中，有css, index.html

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%201.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%201.png)

### 内部样式标-html与css不分离的例子

- 在header后面定义css
- 但是在这里写，html与css没有分离
- 每一个声明使用`;`结尾
- css语法：
`选择器{
            声明1；
            声明2；
            声明3；
        }`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--规范,在这里编写css代码，
    但是在这里写，html与css没有分离
    每一个声明使用;结尾

    语法：
        选择器{
            声明1；
            声明2；
            声明3；
        }
    -->
    <style>
        h1{
           color: red;
        }
    </style>

</head>
<body>

<h1>我是标题</h1>

</body>
</html>
```

### 外部样式标-分离style

- 将上面的style抽离成一个单独的`style.css` 文件，这样就不用写style标签了
- 在html中相应位置，放一个`<link rel="stylesheet" href="css/style.css">` 链到`style.css`文件
    - `css/style.css` 文件

        ```css
        h1{
           color: red;
        }
        ```

    - `index.html`文件

        ```html
        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <title>Title</title>

            <link rel="stylesheet" href="css/style.css">

        </head>
        <body>

        <h1>我是标题</h1>

        </body>
        </html>
        ```

### css优势

1. 内容和 样式style分离
2. 网页结构表现同意，可以实现复用（比如apply到h1上，格式都统一）
3. 样式十分丰富
4. 建议使用独立于html的css文件
5. 利用SEO，容易被搜索引擎收录
    - VUE似乎不是很容易SEO

## CSS的导入方式

- [ ]  [P44、四种css导入方式11:03](https://www.bilibili.com/video/BV1YJ411a7dy?p=4)

### css的3中导入方式

1. 行内标签，直接写在标签中,如`<h1 style="color:red"></h1>`

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
    </head>
    <body>

    <!--行内样式，在标签中，编写一个style属性，即可-->
    <h1 style="color:red"></h1>

    </body>
    </html>
    ```

2. 内部样式: 在header 后面插入style
    - 注意，style标签中的不再是html语法，而是css 语法

    ```html
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <!--内部样式-->
        <style>
            h1{
                color:green;
            }
        </style>

    </head>
    ```

3. 外部样式
    - 用外部抽离的style.css文件，然后在html中链接过去

    ```html
    <!--html-->
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <link rel="stylesheet" href="css/style.css">

    </head>
    ```

    ```css
    /*外部样式*/
    h1 {
        color:yellow;
    }
    ```

### 三种导入方式的优先级

- 行内最优先
- 内部，外部，看谁写在下面了，写在下面的会更新style （就近原则）
- 比如，如下，内部写在下面，以内部为准

    ```html
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <link rel="stylesheet" href="css/style.css">

        <!--内部样式-->
        <style>
            h1{
                color:green;
            }
        </style>

    </head>
    ```

### 外部style的两种方式

- 链接式
    - CSS3，推荐！
    - 属于html标签

    ```html
    <!--html-->
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <link rel="stylesheet" href="css/style.css">

    </head>
    ```

- 导入式
    - CSS2中的，不推荐
    - 有弊端（可能要先出html结构，然后再渲染变好看，视觉效果差）

    ```html
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <style>
            @import url("css/style.css");
        </style>

    </head>
    ```

## 选择器

- [ ]  [P55、三种基本选择器-重要19:49](https://www.bilibili.com/video/BV1YJ411a7dy?p=5)

### 选择器-作用

- 选择页面上的某一个or某一类 元素

### 基本选择器

- 标签选择器
    - apply到某一类的标签，比如h1
    - 但是不能 灵活的让第一个h1变色，第二个h2不变色

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <!--标签选择器-->
        <style>
            h1{
                color: #FF6F62; /*control shift A*/
                background: #3cbda6;
                border-radius: 24px;
            }
            p{
                font-size:80px;
            }
        </style>
    </head>
    <body>

    <h1>学Java</h1>
    <h1>学Java</h1>
    <p>听狂神说</p>

    </body>
    </html>
    ```

- 类选择器 class
    - 用class修饰标签
    - 选择所有class属性一致的标签
    - 然后再css中，可以对一类class名字，做同样处理
    - 非常灵活，可以复用
    - 还可以跨类使用，如下，p，h1同时处理

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <!--类选择器：
            .class名称{}-->
        <style>
            .qin{
                color:purple;
            }
        </style>
    </head>
    <body>

    <h1 class="qin">学Java</h1>
    <h1>学Java</h1>
    <h1 class="qin">学Java</h1>
    <p class="qin">this is paragraph</p>

    </body>
    </html>
    ```

- id选择器
    - id全局唯一
    - 语法是
    `#id名称{
            }`

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <!--id选择器：
            #id名称{
            }
            -->
        <style>
            #woya{
                color:red;
            }
        </style>
    </head>
    <body>

    <h1 id="woya">标题1</h1>
    <h1>标题2</h1>
    <h1>标题3</h1>
    <h1>标题4</h1>
    <h1>标题5</h1>

    </body>
    </html>
    ```

### 基本选择器优先级

- id选择器 > class选择器 > 标签选择器

![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%202.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%202.png)

### 直接在broswer上调试（暂时）

- 在左边html结构中选择某一个element
- 然后在右边对应的style中的element.style中可以自己去写css的style格式
- 效果暂时，刷新就没了
- 一般可以先去browser中调试，看完效果，然后再写入css代码

![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%203.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%203.png)

## 层次选择器

- [ ]  [P66、层次选择器14:11](https://www.bilibili.com/video/BV1YJ411a7dy?p=6)

### 1-后代选择器

- 在某个element 的后面：**祖爷爷** 爷爷 爸爸 你
- 所有后代都被选中了

    ```css
    /*后代选择器
            body后面的p都变颜色*/
            body p{
                background:red;
            }
    ```

### 2-子选择器

- 只有直属后代（儿子一代）：**祖爷爷** 爷爷 爸爸 你

    ```css
    /*子选择器
            body后面的直属p变颜色*/
            body>p{
                background: purple;
            }
    ```

### 3-相邻兄弟选择器

- 后面相邻的一个

    ```css
    /*相邻兄弟选择器
            active类的后面相邻的一个p标签*/
            .active+p{
                background: yellow;
            }
    ```

### 4-通用选择器

- 后面的同级所有

    ```css
    /*通用选择器
            active类的后面相邻的每一个同级p标签*/
            .active~p{
                background:blue;
            }
    ```

## 结构伪类选择器

- [ ]  [P77、结构伪类选择器14:32](https://www.bilibili.com/video/BV1YJ411a7dy?p=7)

### 结构伪类选择器

- 伪类选择器，带`：`，后有修饰
- 伪类: 加了条件判断

### 例子

- ul中的li`：`哪一个（修饰）
- nth代表：前面的那类的父类，type是按前面的类型数，child是纯按顺序不安类型（但只应用于跟前面类型一样的元素）

    ```css
    /*ul的第一个子元素li*/
    ul li:first-child{
      background:blue;
    }

    /*ul的最后一个子元素li*/
    ul li:last-child{
      background:red;
    }

    /*选中 p1,定位到父元素，选择当前第一个元素
    选中当前p元素的父级元素，选中父级元素的第一个，而且是当前元素类型才生效
    这里h1为第一个，p1为第二个（按顺序）*/
    p:nth-child(2){
      background:yellow
    }

    /*选中p的父元素中，第二个p类型的元素（按类型）*/
    p:nth-of-type(2){
      background:green;
    }

    a:hover{
      background:purple;
    }
    ```

- 总code

    ```css
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <!--避免使用.class, id选择器-->
        <style>
            /*ul的第一个子元素li*/
            ul li:first-child{
                background:blue;
            }

            /*ul的最后一个子元素li*/
            ul li:last-child{
                background:red;
            }

            /*选中 p1,定位到父元素，选择当前第一个元素
            选中当前p元素的父级元素，选中父级元素的第一个，而且是当前元素类型才生效
            这里h1为第一个，p1为第二个（按顺序）*/
            p:nth-child(2){
                background:yellow
            }

            /*选中p的父元素中，第二个p类型的元素（按类型）*/
            p:nth-of-type(2){
                background:green;
            }

            a:hover{
                background:purple;
            }
        </style>
    </head>
    <body>

    <a href="">a</a>
        <h1>h1</h1>
        <p>p1</p>
        <p>p2</p>
        <p>p3</p>
        <ul>
            <li>li1
            </li>
            <li>li2
            </li>
            <li>li3
            </li>
        </ul>

    </body>
    </html>
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%204.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%204.png)

## 属性选择器

- [ ]  [P88、属性选择器-重要20:24](https://www.bilibili.com/video/BV1YJ411a7dy?p=8)

### 属性选择器基础

- 格式：`标签[属性]{}`
- 属性选择：
    - [属性]
    - [属性=属性名]
    - [属性=属性名-正则]
- 等于
    - =：绝对等于
    - *=: 含有
    - ^=: 以什么什么开头
    - $=: 以什么什么结尾
- 非常常用：CSS, JS, JQeury, VUE
- 常见例子

    ```css
    /*带有id属性的a标签*/
    a[id]{
        background:yellow;
    }

    /*属性class为”links item last“的a标签*/
    a[class="links item last"]{
        background:green;
    }

    /*class里面有links元素的a标签,正则*=是包含pattern的意思*/
    a[class*="links"]{
        background:blue;
    }

    /*选择href中以http开头的元素*/
    a[href^=http]{
        background:white
    }

    /*选择href中以http开头的元素*/
    a[href$=pdf]{
        background:brown;
    }
    ```

### 例子

```css
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        .demo a{
            float: left;
            display:block;
            height: 50px;
            width: 50px;
            border-radius:30px;
            background: red;
            text-align:center;
            color:gainsboro;
            text-decoration: none;
            margin-right:6px;
            font: bold 20px/50px Arial;
        }

        /*带有id属性的a标签*/
        a[id]{
            background:yellow;
        }

        /*属性class为”links item last“的a标签*/
        a[class="links item last"]{
            background:green;
        }

        /*class里面有links元素的a标签,正则*=是包含pattern的意思*/
        a[class*="links"]{
            background:blue;
        }

        /*选择href中以http开头的元素*/
        a[href^=http]{
            background:white
        }

        /*选择href中以http开头的元素*/
        a[href$=pdf]{
            background:brown;
        }
    </style>

</head>
<body>

<p class="demo">
    <a href="http://www.baidu.com" class="links item first" id="first">1</a>
    <a href="" class="links item active" target="_blank" title="test">2</a>
    <a href="images/123.html" class="links item">3</a>
    <a href="images/123.png" class="links item">4</a>
    <a href="images/123.jpg" class="links item">5</a>
    <a href="/a.pdf">6</a>
    <a href="/abc.pdf"  class="links item">7</a>
    <a href="abc">8</a>
    <a href="abc.doc">9</a>
    <a href="abcd.doc" class="links item last">10</a>
</p>

</body>
</html>
```

![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%205.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%205.png)

## 美化网页元素

- [ ]  [P99、CSS的作用及字体样式14:59](https://www.bilibili.com/video/BV1YJ411a7dy?p=9)

### 为什么要美化网站

- 有效传递页面信息
- 美画网页
- 提高用户体验
- 凸显页面主题

### span标签

- 重点突出的字，用stan标签
    - 重点内容，约定俗成用Stan来框起来

    ```css
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <style>
            #hl1{
                font-size:50px;
            }
        </style>

    </head>
    <body>

    欢迎学习 <span id="hl1">Java</span>

    </body>
    </html>
    ```

### 字体样式

- 常用字体

    ```css
    <!--字体
      font-family:字体
      font-size:字体大小
      font-weight:字体粗细
      color: 字体颜色

    -->
    <style>
      body{
          font-family: 楷体,"Arial Black";
      }
      h1{
          font-size: 50px;
          font-weight:lighter;
      }
      .p1{
          font-weight:bold;
          color:red;
      }
    </style>
    ```

- 可以写成一行

    ```css
    p{
      font: oblique lighter 30px "楷体"
    }
    ```

## 文本样式

- [ ]  [P1010、文本样式19:53](https://www.bilibili.com/video/BV1YJ411a7dy?p=10)

### 文本样式

- 颜色
    - 可以拼单词red
    - 也可以RGB，各两位: #0000FF (16进制，0-9ABCDEF)
    - RGBA,即加上alpha, `rgb(0,255,255)` ,`rgba(0,255,255,0.4)`
        - alpha: 0~1

        ```css
        h1{
            color:rgba(0,255,255,0.4) ;
        }
        ```

- 对齐方式
    - text-align: center/ right/ left
    - em: 单词字长，px: 像素

    ```css
    h1{
        color:rgba(0,255,255,0.4) ;
        text-align:center;
    }
    ```

- 首行缩进
    - text-indent

    ```css
    p{
        text-indent: 2em
    }
    ```

- 行高
    - line-height:字体所占高度 （字体在格子里）

        height：格子所占高度

        ```css
        p{
            text-indent: 4em;
            background: purple;
            height: 50px;
            line-height:50px;
        }
        ```

    - 高度居中：如果想要文字在color box中间，可以强行让一行的height等于color box的height

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%206.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%206.png)

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%207.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%207.png)

- 下划线（装饰）
    - 注意，a标签自动有下划线，要去掉下划线：

        ```css
        a{
        	text-decoration:none;
        }
        ```

    - 上划线，中划线，下划线

        ```css
        .l1{
            text-decoration:underline;
        }
        .l2{
            text-decoration:line-through;
        }
        .l3{
            text-decoration:overline;
        }
        ```

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%208.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%208.png)

- 两物体对齐

    ```css
    img, span{
        vertical-align:middle;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%209.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%209.png)

---

## 阴影+实用

- [ ]  [P1111、文本阴影和超链接伪类13:53](https://www.bilibili.com/video/BV1YJ411a7dy?p=11)

### 阴影

- 在一个标签上增加阴影

    ```css
    #price{
        text-shadow:5px 5px 10px #FF0000; /*水平往右偏移，高度往下，半径大小，颜色*/
    }
    ```

- 各种状态的实用
    - hover 悬浮
    - active鼠标点住 未松开时
    - 还有link, visited可以了解一下

    ```css
    a:hover{
        color:orange;
        font-size:20px;
    }
    /*鼠标按住 没有松开的状态 设定*/
    a:active{
        color: yellow;
    }
    ```

- 综合例子

    ```css
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>

        <style>

            a{
                text-decoration:none;
                color:purple;
            }
            a:hover{
                color:orange;
                font-size:20px;
            }
            /*鼠标按住 没有松开的状态 设定*/
            a:active{
                color: yellow;
            }
            /*
            a:link{
                color:brown;
            }
            a:visited{
                color:red;
            }
            */
            #price{
                text-shadow:5px 5px 10px #FF0000; /*水平往右偏移，高度往下，半径大小，颜色*/
            }
        </style>
    </head>
    <body>

    <!--#是默认当前页面-->
    <a href="#">
        <img src="images/lulu.jpg" width="250" alt="lulu">
    </a>
    <p>
        <a href="">叛逆的鲁鲁修</a>
    </p>
    <p>
        <a href="">作者</a>
    </p>
    <p id="price">$10,000</p>

    </body>
    </html>
    ```

## 列表

- [ ]  [P1212、列表样式练习11:51](https://www.bilibili.com/video/BV1YJ411a7dy?p=12)

- 可以框成一个没有意义的div,一般配合id或属性使用
- 一般div写在css style最上面，一层一层往下写
- 列表

    ```css
    /*ul li*/
    ul{/*apply to the whole list*/
        background-color: lightgray;
    }
    ul li{
        line-height:2;
        list-style:none; /*no bullet points*/
        list-style:circle: /*空心圆*/
        list-style:decimal; /*有序列表*/
        list-style:square; /*正方形*/
        text-indent: 1em
    }
    ```

- css例子

    ```css
    /*从外网里写，div是parent集，所以写在最上面*/
    #nav{
        background-color:pink;
        width:200px;

    }

    .title{
        /*title == header2??*/
        font-size:18px;
        font-weight:bold;
        text-indent: 1em;
        line-height:3;
        background-color:pink;
    }
    /*ul li*/
    ul{/*apply to the whole list*/
        background-color: lightgray;
    }
    ul li{
        line-height:2;
        list-style:none; /*no bullet points*/
        list-style:circle: /*空心圆*/
        list-style:decimal; /*有序列表*/
        list-style:square; /*正方形*/
        text-indent: 1em
    }

    a{
        text-decoration:none;
        font-size:14px;
        color:purple;

    }
    a:hover{
        color:orange;
        text-decoration:underline;
    }
    ```

- html例子

    ```css
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
        <link rel="stylesheet" href="css/style.css" >
    </head>
    <body>

    <!--div没有意义，希望缩小一点儿-->

    <div id = "nav">
        <h2 class="title">主题市场</h2>
        <ul>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
            <li><a href="">女装</a>/<a href="">内衣</a>/<a href="">家居</a></li>
        </ul>
    </div>

    </body>
    </html>
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2010.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2010.png)

## 背景

- [ ]  [P1313、背景图像应用及渐变16:22](https://www.bilibili.com/video/BV1YJ411a7dy?p=13)

### 填充背景的图片

- background-image 默认：全部平铺
- background-repeat:
    - repeat-x：平铺一行
    - repeat-y：平铺一列
    - no-repeat: 显示原本图片
    - 默认：全部平铺

    ```css
    div{
        width=1000px;
        height:700px;
        border: 1px solid red;
        background-image: url("images/lulu.jpg")
    }
    .div1{
        background-repeat:repeat-x;
    }
    .div2{
        background-repeat:repeat-y;
    }
    .div3{
        background-repeat:no-repeat;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2011.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2011.png)

### 区域边框border:

1. 粗细
2. 样式（solid：实线）
3. 颜色：red

```css
div{
    width=1000px;
    height:700px;
    border: 1px solid red;
}
```

### 例子

- 平铺

    ```css
    background: red url("../images/right.png")
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2012.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2012.png)

- 只留一个

    ```css
    background: red url("../images/right.png") no-repeat;
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2013.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2013.png)

- 调整位置细节：
    - 颜色 图片 位置 水平 垂直 平铺方式
    - background-size 调整图片尺寸

    ```css
    background: red url("../images/down.png") 160px 19px no-repeat;
    ```

- 分步加下面的 箭头
    - 效果跟上面写进一行的一样

    ```css
    ul li{
        line-height:2;
        list-style:none; /*no bullet points*/
        list-style:circle: /*空心圆*/
        list-style:decimal; /*有序列表*/
        list-style:square; /*正方形*/
        text-indent: 1em;
        background-image: url("../images/right.png");
        background-repeat: no-repeat;
        background-position: 123px 8px;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2014.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2014.png)

### 指定查看某一element

1. 先点击 1）
2. 然后鼠标 选中要看大的element （标签）
3. 然后就导到

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2015.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2015.png)

4. 直接调整位置

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2016.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2016.png)

### 推荐的 渐变网站

- 开源的

    [Grab yourself a gradient](https://www.grabient.com/)

- 可以自己调整颜色，然后复制css代码

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2017.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2017.png)

    ```css
    background-color: #5497c5;
    background-image: linear-gradient(300deg, #5497c5 3%, #3e72c5 9%, #ae7faa 36%, #d1ffd9 100%);
    ```

- linear-gradient(颜色，颜色，颜色)
- 直接放进背景（一般用于图片，如果加字的画，一格一格的不太好）

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2018.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2018.png)

## 盒子模型

- [ ]  [P1414、盒子模型及边框使用15:32](https://www.bilibili.com/video/BV1YJ411a7dy?p=14)

### 盒子模型

- margin 外边距
- border 边框，或者盒子自身
- padding 内边距
- 最里面：内容，文字？

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2019.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2019.png)

- 可以直接在上面调整上下左右的

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2020.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2020.png)

### 边框

- 格式：粗细，样式，颜色
- 例1
    - div：id为app（书写习惯）
    - 注意，默认是有外边距margin的，发现是body的，（body里面有个div的app框），如果没有把body调成0，都会问有margin

        ```css
        /*border: 粗细，样式，颜色*/
        #app{
            width: 300px;
            border: 1px solid red;
        }
        ```

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2021.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2021.png)

    - body-margin调成0就没有了

        ```css
        body{
            /*body总有一个默认的不为零margin*/
            margin: 0;
        }
        /*border: 粗细，样式，颜色*/
        #app{
            width: 300px;
            border: 1px solid red;
        }
        ```

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2022.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2022.png)

    - 开发规范：最开始写一个初设设定框（见 《码出高效》）

        ```css
        h1, ul,li,a,body{
          margin: 0;
          padding: 0;
          text-decoration:none;
        }
        ```

- 例2
    - `nth-of-type(n)` selector matches every element that is the nth child, of a particular type, of its parent.

    ```css
    div:nth-of-type(2){
        border: 3px solid gray;
    }
    ```

    - 选 div 的 parent的 第2个 同类（div）的框
        - 选中的是所有div标签
        - div parent是form
        - form的 第二个div子标签是password

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2023.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2023.png)

```html
<body>
<div id="app">
    <h2>Log In</h2>
    <form action="#">
        <div>
            <span>username：</span>
            <input type="text"></input>
        </div>
        <div>
            <span>password：</span>
            <input type="text"></input>
        </div>
        <div>
            <span>email：</span>
            <input type="text"></input>
        </div>
    </form>
</div>
</body>
```

- 例3
    - 选中指定的password input

        ```css
        div:nth-of-type(2)>input{
            border: 3px solid gray;
        }
        ```

![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2024.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2024.png)

- 例4
    - 错误例子：如果不加>，选的是所有后代input的

        ```css
        div:nth-of-type(1) input{
            border: 3px solid gray;
        }
        ```

![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2025.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2025.png)

- 例5
    - 之前

        ```css
        h2{
           font-size: 16px;
           background-color: lightyellow;
        }
        ```

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2026.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2026.png)

- 之后

    ```css
    h2{
       font-size: 16px;
       background-color: lightyellow;
       line-height:30px;
       margin :0;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2027.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2027.png)

- border一行书写，等价于 border-width, style, color

    边框还可以分 bottom, right, left, top

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2028.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2028.png)

## padding, margin, div居中

- [ ]  [P1515、内外边距及div居中08:57](https://www.bilibili.com/video/BV1YJ411a7dy?p=15)

### margin外边距

- 上下左右padding设置在一行：

    ```css
    h1, ul,li,a,body{
      margin: 0 0 0 0 ;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2029.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2029.png)

- 外边距妙用：居中
    - `margin: 0`(上下) `auto`（左右，auto是自动对齐）

    ```css
    #app{
        width: 300px;
        border: 1px solid purple;
        margin: 0 auto;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2030.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2030.png)

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2031.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2031.png)

- margin上下改成0

    ```css
    margin-bottom:0 ; /*下：0*/
    margin: 0; /*上下左右都是0*/
    margin:0 15px; /*上下:0 左右15*/
    margin:0 0 0 0 /*上 右 下 左*/ 
    ```

### padding

- 外边距

    ```css
    h1, ul,li,a,body{
      padding: 0 0 0 0 ;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2032.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2032.png)

- settings

    ```css
    padding-bottom:0 ; /*下：0*/
    padding: 0; /*上下左右都是0*/
    padding:0 15px; /*上下:0 左右15*/
    padding:0 0 0 0 /*上 右 下 左*/ 
    ```

### 一个元素多大？

- 一个元素的大小，是所有的元素之和：margin + border + padding + 内容大小

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2031.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2031.png)

- 是把整体 的 大小 跟美工对接
    - 产品经理-要让大家互相了解价值：设计，工程，产品
    - 设计师要把理念 告诉内部团队
    - 亚洲人-比较精致，日本包装
    - 好的用户体验师
        - 要有同理心，了解 使用场景
        - 想要改变好一点

## 圆角边框

- [ ]  [P1616、圆角边框及阴影和经验分享40:46](https://www.bilibili.com/video/BV1YJ411a7dy?p=16)

### 四个角

- 4个input左上 右上 右下 左下（顺时针）

    ```css
    div{
        width:100px;
        height:100px;
        border:10px solid gray;
        border-radius:50px 20px 10px 0px;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2033.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2033.png)

- 2个input: 左上右下，右上左下

    ```css
    div{
        width:100px;
        height:100px;
        border:10px solid gray;
        border-radius:50px 20px;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2034.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2034.png)

- 圆圈
    - border-radius： 以图形中心为圆心，半径为border radius画圆

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2035.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2035.png)

- 扇形

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2036.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2036.png)

- 图片圆角

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2037.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2037.png)

## 阴影

### 阴影

- 向右 向下 大小 颜色

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2038.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2038.png)

- 图片加阴影
    - margin:0 auto没有用的原因：

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2039.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2039.png)

        - 没有用div套用
        - 前提条件：外面必须是块元素，而且要有宽度
    - 正解：
        1. 方法一：把img换成块

            ```html
            <img src="images/lulu.jpg" alt="" style="display:block">
            ```

        2. 方法二：在div块中，加上`text-align:center`

            ```css
            <div style="text-align:center">
                <img src="images/lulu.jpg" alt="">
            </div>
            ```

            ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2040.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2040.png)

## 模板资源

不要重复造轮子！！！

- 已有的网站：下载html
    - 艾编程: [https://www.icodingedu.com/](https://www.icodingedu.com/)
- 源码之家，搜`登陆页面`
- 模板之家
- 框架：
    - layui ： [https://www.layui.com/](https://www.layui.com/)
    - bootstrapt
    - vue-admin-element (vue, 有新的标签)： [https://panjiachen.github.io/vue-element-admin-site/](https://panjiachen.github.io/vue-element-admin-site/)
    - 飞冰：[https://ice.work/docs/guide/about](https://ice.work/docs/guide/about)

## 浮动

- [ ]  [P1717、display和浮动17:49](https://www.bilibili.com/video/BV1YJ411a7dy?p=17)

### 标准文档流

- 右边就是标准文档，一行行排下来，手机就是这么用，网页一般不这样

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2041.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2041.png)

### 行内元素，块级元素

- 块级元素，独占一行, 比如 h1, p ,div, list
- 行内元素，不独占一行，比如span, a, img, strong
- 行内元素可以放在块级元素中，反之不行
- display
    - `inline` 转成行内元素
    - `block` 块级元素
    - `inline-block`  是块，但可以放在行内
    - `none` 没了，没空间了
- 例1
    - div是块，span是行内

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2042.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2042.png)

    - 在span这个行内元素中增加display:block可以转成块级元素
        - `display: inline-block;` 即是block也是行内元素
        - `display: block;` 块级元素

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2043.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2043.png)

### 重新调整图片大小

- 宽缩为原来的30%，自动调整高度：

    ```css
    img {
        max-width:30%;
        height:auto;
    }
    ```

### 例子

- 不加浮动效果
    - parent：总div
    - layer01~04 分别对应下面四个框

    ```css
    #parent{
        border: 1px #000 solid;
    }
    .layer01{
        border: 1px #F00 dashed;
    }
    .layer02{
        border: 1px #00F dashed;
    }
    .layer03{
        border: 1px #060 dashed;
    }
    .layer04{
        border: 1px #666 dashed;
        font-size: 12px;
        line-height: 24px;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2044.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2044.png)

- 增加浮动效果，变成 inline-block
    - 注意，inline-block,跟`img` 的设定，比如`max-width:30%;` ，会发生冲突（img一设定，就会默认占一整行，即使后面加了inline-block也没用），所以只能用`paint` 先`resize` 好了图片，再放过来
    - 变成inline-block

        ```css
        .layer01{
            border: 1px #F00 dashed;
            display: inline-block;
        }
        .layer02{
            border: 1px #00F dashed;
            display: inline-block;
        }
        .layer03{
            border: 1px #060 dashed;
            display: inline-block;
        }
        .layer04{
            border: 1px #666 dashed;
            font-size: 12px;
            line-height: 24px;
            display: inline-block;
        }
        ```

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2045.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2045.png)

    - 理解浮动效果 `float: left`
        - 浮动的意思是，不占用高度，但占用宽度，可以直接可以float到左边or右边
        - 未float的东西，自动排列在剩下的空余位置中
        - float不会引起重叠
        - 如果多个东西一起float 到左或右，自动形成排列

        ```css
        .layer01{
            border: 1px #F00 dashed;
            display: inline-block;
            float: left;
        }
        .layer02{
            border: 1px #00F dashed;
            display: inline-block;
            float: right;
        }
        .layer03{
            border: 1px #060 dashed;
            display: inline-block;
            float: right;
        }
        .layer04{
            border: 1px #666 dashed;
            font-size: 12px;
            line-height: 24px;
            display: inline-block;
        }
        ```

        ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2046.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2046.png)

### float引起的问题

- 问题：拉动宽度，floating的东西会自动排版

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2047.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2047.png)

- 配合float，有一个选项叫做`clear:both` ，可以清楚一个item左右两边的floating item

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2048.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2048.png)

- 如果都加了clear both，排不过来的，会自动排在下一行

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2049.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2049.png)

## 父级边框塌陷问题

- [ ]  [P1818、overflow及父级边框塌陷问题20:07](https://www.bilibili.com/video/BV1YJ411a7dy?p=18)

### clear

使用clear来解决floating互相之间影响的问题

- `clear: left;` 左侧不允许有floating item
- `clear: right;` 右侧不允许有floating item
- `clear: both;` 两侧不允许有floating item
- `clear: none;` 允许各种floating item

### 如何解决父级边框 没有套住floating item的问题

- 解决方法1：增加父级框的 高度，使得，不管怎么变，都可以套住这些floating item
    - 弊端（不建议！）：假设 有了固定的高度，就会被限制，比如新的元素超出原本高度，就有问题
- 解决方法2：在框内最后面增加一个空的div

    把这个空的设置为非float而且要求左右both clear，标准设置如下，就可以让父级边框成功套住所有floating啦~

    - 弊端：一般避免空的div
    - 简单

    ```css
    .clear{
        clear: both;
        margin:0;
        padding:0;
    }
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2050.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2050.png)

- 解决方法3：在父级中 添加`overflow:hidden;`
    - 简单
    - 不太适用于下拉的情况
    - 即使超出去被切掉，也不建议增加滚动条，看起来怪

    注意，这里不会切除，因为父级框本身没有长宽限制，设置之后，会自动切除没有内容的部分

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2051.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2051.png)

- 解决方案4：在父级中，添加一个伪类 `:after`
    - 最好的方法！！！有一点点复杂，但是没有副作用！
    - 通过下面的，在parent div中，自动在最后面添加那个空div（也就是编程的方法实现 解决方案2）
        - 内容为空-占空间很小
        - 设置为block
        - 要求左右都没有float

    ```css
    #parent:after{
        content: "";
        display: block;
        clear: both;
    }
    ```

### Overflow

- `overflow: hidden;` 超出边界的部分自动消除

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2052.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2052.png)

- `overflow: scroll;` 超出的部分用 自动滚动实现

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2053.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2053.png)

### 对比display, float

- display
    - 不能控制方向
    - 不用管理parent 边框 塌陷的问题
- float
    - 可以控制方向
    - 更加推荐
    - 需要管理parent 边框 塌陷的问题

## 定位

- [ ]  [P1919、相对定位的使用及练习12:54](https://www.bilibili.com/video/BV1YJ411a7dy?p=19)

### 默认

![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2054.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2054.png)

### 相对定位

- 相对于自己原来的位置进行偏移

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2055.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2055.png)

- 设定`position: relative;` 并且配合设定`top`, `bottom`, `right`, `left`

    例如：top，理解为，距离上面（assume 新的在原始位置的下面）

    ```css
    #first{
        background-color:yellow;
        border:1px dashed green;
        position: relative; /*相对定位：上下左右*/
        top: -20px; /*理解为，距离上面，负为向上移动*/
        left: 20px; /*理解为，距离左边,正为向右移动*/
    }
    ```

- 虽然相对原来的位置移动，但是，仍然在标准文档流中，跟floating不同，原来的位置被保留（留出来了）

### 相对定位练习题

- [ ]  [P2020、方块定位练习讲解07:08](https://www.bilibili.com/video/BV1YJ411a7dy?p=20)
- 先写一个大盒子：div
- 5个a标签，然后统一 改写为 正方格子的格式
    - 通过id的形式，分别设置位置是relative
    - 注意如果操作相同，可以写在一起，比如`.a2`, `.a4`

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
        <style>
            #box{
                width:300px;
                height:300px;
                padding:10px;
                border:2px solid red;
            }
            a{
                width:100px;
                height:100px;
                text-decoration:none;/*no underline*/
                background-color: pink;
                line-height:100px;
                text-align:center;
                color:white;
                display:block;
                margin:1px;
            }
            a:hover{
                background:lightblue;
            }
            .a2,.a4{
                position:relative;
                left:200px;
                top:-100px
            }
            .a3{
                position:relative;
                left:100px;
                top:-100px
            }
            .a5{
                position:relative;
                bottom:200px
            }
        </style>
    </head>
    <body>

    <div id="box">
        <a href="#" class="a1">link1</a>
        <a href="#" class="a2">link2</a>
        <a href="#" class="a3">link3</a>
        <a href="#" class="a4">link4</a>
        <a href="#" class="a5">link5</a>
    </div>

    </body>
    </html>
    ```

![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2056.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2056.png)

- [ ]  [P2121、绝对定位和固定定位11:44](https://www.bilibili.com/video/BV1YJ411a7dy?p=21)

### 绝对定位

- 相对于parent或者浏览器的位置，进行指定偏移，绝对定位不在标准文档流中，原来位置不会被保留
- 如果parent框没有定位，基于浏览器四个框定位，上下左右

    ```css
    position: absolute;
    right: 30px;
    ```

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2057.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2057.png)

- 如果parent 框有所定位
    - 在这里，parent框 `position: relative` ，相当于没有任何操作，还在原位置
    - 但是因为parent有所定位，这里的框基于这个parent框来定位
    - 如果顶到了parent边框四周，就到头了，超不过去parent边框

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2058.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2058.png)

### 固定定位fixed

- fixed与abosolute
    - div1: aboslute，在窗口内滚动时会动
    - div2: fixed, 固定在窗口，在窗口内滚动时也不会动

```css
body{
    height:1000px;
}
div:nth-of-type(1){
    width:100px;
    height:100px;
    background:red;
    position:absolute;
    right:0;
    bottom:0;
}
div:nth-of-type(2){
    width:50px;
    height:50px;
    background:yellow;
    position:fixed;
    right:10px;
    bottom:50px;
}
```

![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2059.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2059.png)

![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2060.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2060.png)

- [ ]  [P2222、z-index及透明度17:32](https://www.bilibili.com/video/BV1YJ411a7dy?p=22)

## z-index

### 图层

- 最底层0，最高999，代表了层级顺序
- `z-index`就是这个层级

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2061.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2061.png)

### 例子

1. 初始化界面，隐藏bullet point `list-style:none`

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2062.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2062.png)

2.  定义粉色的底要在文字图层下面
    - 解决方法：把文字设在最上层 `z-index:999;`

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2063.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2063.png)

### 设置background color透明度

1. opacity: `opacity:0.5;`

    ![%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2064.png](%E3%80%90%E7%8B%82%E3%80%91CSS3%20657dc38bc9d24fad8f9b13d0a8f9664b/Untitled%2064.png)

2. 早版本：`filter:alpha(opacity=50);`

    可以两个都写上以保证旧版本的也可以用（其实只写opacity就好了）

## 动画

- [ ]  [P2323、动画及视野拓展17:56](https://www.bilibili.com/video/BV1YJ411a7dy?p=23)

### 科普理解

- 可以用css, javascript写动画
- `@keyframes`可以设置关键帧
- 不同浏览器有可能兼容性不同，可能同一段代码要写很多次
- 现在css 用`less`写，可以扩展css语言，用编程，函数还写，最后生成css
- 转换（2d）旋转，一般用过渡,动画或者实现
- JavaScript动画 比较高级 比如 [http://www.topthink.com/topic/9820.html](http://www.topthink.com/topic/9820.html)
- canvas动画: 很多特效都是用javaScript和canvas写的
- 全球卫星的例子：[https://cybermap.kaspersky.com/](https://cybermap.kaspersky.com/)

[CSS3 动画](https://www.runoob.com/css3/css3-animations.html)

- [ ]  [P2424、CSS小结14:00](https://www.bilibili.com/video/BV1YJ411a7dy?p=24)

### CSS总结

- 初识
    - CSS概念
        - CSS在网页中的应用
        - CSS发展史 （1.0， 2.0，3.0）
        - CSS优势
    - CSS语法：`style`
    - 3种引入方式：行内样式，内部样式，外部样式
    - CSS选择器
        - 基本选择器：element, class(`.`), id(`#`)
        - 层次选择器：
            - 层次选择器(后代：空格，下一级`>`, 通用 `~`, 相邻兄弟 `+`)
            - 结构伪类选择器
            - 属性选择器 (标签+属性值) a[`*` `^` `$`]
- 美化网页
    - 字体：`color`, `font-size`
    - 排版网页：`text-align`, `text-indent`, `line-height`, `text-decoration`
    - 超链接伪类：hover
    - 列表：list-style
    - 背景：
        - 背景颜色：background-color
        - 背景图片：repeat，渐变背景 （网站）
- 盒子模型
    - border, padding, margin
    - 盒子模型尺寸计算：border+margin+padding+内容element
    - box-size
    - 圆角边框 border-radius
    - 阴影 box-shadow
- 浮动
    - 网页布局-标准文档流
    - display: block. inline, inline-block
    - 浮动 float：左，右，none
    - 清除浮动：clear (left, right, both, none)
    - 解决父级border塌陷
        - 空div
        - 父级高度固定
        - overflow
        - :after
    - inline-block和float区别
- 定位
    - 默认：静态定位
    - relative定位
    - absolute定位
    - fixed
    - z-index
    - opacity
