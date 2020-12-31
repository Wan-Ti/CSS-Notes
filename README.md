# CSS-Notes

**该写的代码不要省，不该写的代码不要写**

1.语法

 ```
 语法一：样式语法
  选择器 {
      属性名：属性值；
      /*注释*/
      }
      
语法二：@语法
 @charset "UTF-8";
 @import url(2.css);
 @media (min-width: 100px) and (max-width: 200px){语法一;}
   
  注意：
  @charset必须放在第一行；
  前两个@语法必须以分号;结尾；
 ```
 
 2. 查资料
 ```
Google搜索关键词加MDN；</br>
CSS tricks;</br>
张鑫旭的博客；</br>
    
联系素材：
dribbble.com顶级设计师社区(不提供下载)
```
   
 
 ## 基本概念
 
 ### 文档流Normal Flow
 
 1. 流动方向
   inline元素从左到右到达最右边后换行；
   block元素从上到下，每一个都另起  一行；
   inline-block也是从左到右;
 
 2. 宽度
   inline宽度为内部inline元素的和，不能用width指定；
 block默认自动计算宽度，可用width指定；
 inline-block结合前两者特点，可用width指定；
 
 3. 高度
 inline高度由line-height间接确定，与height无关；
 block高度由内部文档流元素决定，可以设height;
 inline-block与block类似，可以设置height;
 
 需要注意的是在HTML5中所有元素不再区分内联元素与块级元素。进行区分的办法是看该元素的属性。即display的属性值为inline还是block;
 
 4. Overflow溢出情况
 · 当内容大于容器</br>
 
    等内容的宽度或高度大于容器的，会溢出
    可用overflow来设置是否显示滚动条；
    auto是灵活设置
    scroll是永远显示
    hidden是直接隐藏溢出部分
    visible是直接显示溢出部分
    overflow可以分为overflow-x和overflow-y
      
 5. 脱离文档流
   具有 float以及position:absolute/fixed属性的元素会脱离文档流；
   
 ### 两种盒模型
 
 两种盒模型分别为border-box和content-box；
 
 ```
 border-box:
 width:border+padding(内边距)ontent
 
 content-box：
 width:content
 
 ```
 
 ### margin合并(内边距塌陷)
 
 组织合并：
 
    · 父子合并
      用padding/border挡住；
      用overflo:hidden挡住
      用display：flex,
    · 兄弟合并
      符合预期；
      用inline-block消除

 
 ## 基本单位
 
长度单位

    · px;  
    · em;
    · 百分数;
    · 整数；
    · rem:；
    · vw和vh;
颜色
 
    · 十六进制；
    · RGBA;
    · hsl;
    
 ## float布局
 
 **不适合在手机页面使用**
 
 
 步骤
 
    子元素上加float：left和width;
    在父元素上加.clearfix
 经验
 
    · 预留一些空间，或者最后一个元素不设置width;
    · 解决IE的双倍margin bug:添加一个display:inline-block；

<a href="">使用float完成的双栏布局(如顶部条) </a> ；</br>
<a href="">使用float完成的三栏布局 (如内容区)</a> ；</br>
<a href="">使用float完成的四栏布局 (如导航)</a> ；</br>
<a href="">使用float完成的平均布局 (如产品展示区)</a> ；</br>
<p>小技巧：在进行平均布局时，在布局中间添加一个x图层可以使得多余的边距值为负</p>


## flex布局

<a href="https://css-tricks.com/almanac/properties/f/flex/">flex布局教程</a>

**flex布局有两个重要组成部分：container | items**

### container元素所属样式
1. 如何将一个元素变成flex容器
```
CSS 
  .container{
      display:flex; /* or inline-flex */
  }
```

2. 改变items的流动方向

```
CSS
    .container{
    	flex-direction:row|row-reverse|column|column-reverse
    }
    
```

3. 改变折行方式

```
CSS
   .container{
   		flex-wrap:nowrap|wrap|wrap-reverse;
   }

```

4. 轴对齐方式

**重点属性**
```
display:flex;
flex-direction:row/column;
flex-wrap:wrap;
just-content:center/space-between;
align-items:center;
```

**默认主轴是横轴，除非改变flex-direction方向**；</br>
**默认次轴是纵轴**



```
CSS 
    .container{
    	justify-content:flex-start|flex-end|center|space-between|space-around|space-evenly
    }
    
    .container{
    	align-item:stretch|flex-start;
    }
```
5. 多行内容分布
```
CSS
   .container{
   		align-center:flex-start|flex-end|center|space-between|space-around|space-evenly
    }
```

### items元素所属属性

flex-shrink控制items区域横向缩小；</br>
flex-basis控制items区域基准宽度；
```
flex:flex-grow flex-shrink flex-basis;
```
align-self定制align-items;


## Grid

**二维布局用Grid;一维布局用Flex**

<a href="https://css-tricks.com/snippets/css/complete-guide-grid/">Grid布局教程</a>

**Gird布局分为container和items两个部分**

## container元素相关属性

**成为container**
```
CSS 
   .container{
   	 display:grid|inline-grid;
   }
```

## 对行和列进行设置

```
CSS
  .container{
    grid-template-column:10px 50px auto 50px 40px ;
    grid-template-row:25% 100px auto;
  }
```

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/17fa8e4e77ca45efbef76df147f97e4a~tplv-k3u1fbpfcp-watermark.image)

也可以对每一行或每一列命名从而单独设置该行或该列的尺寸
```
.item-a{
  grid-column-start:2;
  grid-column-end:five;
  grid-row-start:row1-start;
  grid-row-end:3;
}

```

## 对相邻行或相邻列之间的空隙gap进行设置

```
CSS
  .container{
    grid-template-columns:100px 50px 1px;
    grid-template-rows:80px auto 80px;
    grid-column-gap:10px;
    grid-row-gap:15px;
  }
```

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c9ee83218aff4a288644e8d102b59d09~tplv-k3u1fbpfcp-watermark.image)

## CSS定位

**布局是屏幕平面上的**
**定位是垂直于屏幕的**

一个div元素的分层自顶向依次是：内联子元素->浮动元素->块级子元素->border->background

### 属性Position

position

    · static是默认值，待在文档流里；
    · relative相对定位，升起来但是不脱离文档流；
    · absolute绝对定位，定位的基准是祖先里的非static
    · fixed固定定位，定位基准是viewport;
    · sticky粘滞定位，不常用；
经验

    · 如果写了absolute，一般都需要补一个relative；
    · 如果写了absolute或fixed，一定要补充top和left属性
    

#### 1.position:relative

使用场景

    · 用于做位移（很少用的）
    · 用于给absolute元素做父级元素
配合Z-index

    · z-index:auto默认值。不创建新层叠上下文；
    · z-index：0/1/2;
    · z-index:-1/-2

#### 2.position:absolute
使用场景

    · 脱离原来的位置，另起一层，比如对话框的关闭按钮；
    · 鼠标提示
 配合Z-index
 
 经验：
 
     ·某些浏览器如果不写top/left会位置错乱；
     ·善用left:100%;
     ·善用left:50%;
     ·加负margin
 
 white-space：nowrap;/* 文字部分不自动换行*/
 
**absolut是相对于第一个祖先定位不是static(一般不特殊说明都认为是static)的元素为参考系进行定位**

#### 3.position:fixed

**相对于视口定位**

使用场景

    ·烦人的广告
    ·回到顶部

配合z-index

经验

    ·手机尽量不要使用

### 层叠上下文

**需要注意的是层叠上下文会出现的场景**

<a href="https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Understanding_z_index/The_stacking_context">点击查阅：层叠上下文相关属性</a>

在层叠上下文中。定位元素也就是该元素的z-index的值为0，1，2；则该元素是浮动于内联子元素之上。如果该元素的z-index值为-1，-2，-3；则该元素下沉于background之下；

z-index/flex/opacity/transform

注意区分：opacity:0与background:RGBA(255,255,255,0)的区别:</br>
background-color:transparent和opacity:0所针对的不是同一个对象,前者只是针对元素的背景颜色，后者是针对元素本身，且对子元素是有覆盖性继承性的。所以元素设定了opacity后，它的子元素也会继承opacity属性，而且无法消除.举例说明：一个div内有大段文字，你设定div的bgc为红色且透明度为56%，代码：background-color: rgba(191, 19, 13, 0.56);刷新后的效果只是div的背景色会变，其内容颜色不受影响。但你设div的opacity:0.56；意思就是整个div（包括里面的内容）都变成透明度为56%，显示效果就是整个div包括里面的文字内容等都变成透明度为56%


 
