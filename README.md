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


## Grid布局

 
