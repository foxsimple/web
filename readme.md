web说明文档

链接:

### 一、页面整体结构说明

本网站采用 **HTML5 语义化结构 + CSS 网格布局（Grid Layout）与弹性布局（Flexbox）相结合** 的方式进行设计。页面主要划分为以下五大区域：

1. **页眉区（Header）**
    位于页面顶部，包含网站的 logo 和标题，用于展示网站身份。
2. **导航区（Nav）**
    紧跟页眉区域，使用 Flex 布局将菜单项横向排列，提供页面跳转链接（如：首页、介绍、想要告诉我什么、我的联系方式等）。
3. **主内容区（Main）**
    采用 Grid 网格布局进行区域划分，分为多个内容块（如内容介绍 content1、内容 content2）。内容区域居中展示，样式整洁。
4. **边栏区（Aside）**
    位于页面左侧或下方，显示提示语或补充信息。
5. **页脚区（Footer）**
    固定在页面底部，包含版权声明和网站信息。

------

### 二、布局说明

| 区域   | 使用布局      | 描述                               |
| ------ | ------------- | ---------------------------------- |
| Header | 普通块级布局  | 居中对齐标题 + logo图片            |
| Nav    | Flex 布局     | 横向排列菜单项，支持居中、悬停高亮 |
| Main   | Grid 网格布局 | 分为两行区域 content1 与 content2  |
| Aside  | Grid 指定区域 | 和主区域并排分布（通过 grid-area） |
| Footer | 固定定位      | 固定在底部，始终可见               |

### 三、关键代码

  .nav {

   list-style: none;   /* 去掉圆点 */

   padding: 0;

   margin: 0;

   display: flex;     /* 横向排列的关键：使用 flex 布局 */

   justify-content: center; /* 让导航项水平居中 */

   background-color: lightgreen;  /* 设置背景色 */

   font-size: 16px;

  }

  main {

   grid-area: main;

   display: grid;

   grid-template-rows: repeat(2,1fr); /*设置两行,均等分配*/

   grid-template-areas:/*为区域命名*/

   "content1"

   "content2";

   justify-items: center;

  }

   .content1{

​    grid-area: content1;

​    background-color: lightblue;  

​    width: 90%;

​    padding: 100px;

​    display: flex;

​    justify-content: center;

​    justify-content: center;   /* 水平居中 */

​    align-items: center;     /* 垂直居中 */

​    text-align: center;      /* 多行文字也水平居中 */

​    height: 200px;        /* 给定高度才能垂直居中 */

   }

   .content2{

​    grid-area: content2;

​    background-color: lightpink;

​    width: 90%;

​    padding: 100px;

​    display: flex;

​    justify-content: center;   /* 水平居中 */

​    align-items: center;     /* 垂直居中 */

​    text-align: center;      /* 多行文字也水平居中 */

​    height: 200px;        /* 给定高度才能垂直居中 */

   }