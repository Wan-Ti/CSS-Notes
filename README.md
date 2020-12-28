# CSS-Notes

1. 控制文本自动换行，超出内容省略
```
white-space:nowrap;
text-overflow:ellipsis;
overflow:hidden;
```

2.如何查看或取消默认样式</br>
  查看：Chrome开发工具-Elements-Styles-user agent stylesheet</br>
  取消：进入大厂首页->Chrome开发者工具，找到类似代码->复制到自己项目中->命名为reset.css
  ```
 * {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
*::before,
*::after {
  box-sizing: border-box;
}
a {
  color: inherit;
  text-decoration: none;
}
input,
button {
  font-family: inherit;
}
ol,
ul {
  list-style: none;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
  ```
  
# 部分标签常用属性

## a标签的属性取值
   作用：{
       跳转外部页面；
       跳转内部锚点；
       跳转到邮箱或电话等；
        }

### href取值

```
· 网址：
  <a href="https://google.com">谷歌</a>
  <a href="http://google.com">谷歌</a>
  <a href="//google.com">谷歌</a>
 
 · 路径：
   <a href="/a/b/c"></a>
   <a href="a/b/c"></a>
   <a href="index.html"></a>
   
  . 伪协议
     <a href="javacrtipt:alert(a)">执行JavaScript</a>
     <a href="mailto:邮箱">点击发送邮件</a>
     <a href="tel:123456">点击拨打电话</a>
     
   · id
     <a href="#xxx">跳转ID为XXX的部分</a>
  
```

### target取值

```
内置名字：
<a target="_blank">在一个新的页面打开链接</a>；
<a target="_top">在最顶层页面打开链接</a>；
<a target="_parent">在父页面打开链接</a>；
<a target="_self">在当前页面打开</a>；
```

## table标签常用属性

### table关联标签

<table>
  <thead>
    <tr>
       <th>A</th>
       <th>B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
       <th>数学</th>
       <td>1</td>
       <td>2</td>
    </tr>
    <tr>
       <th>语文</th>
       <td>1</td>
       <td>2</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
       <th></th>
       <td></td>
    </tr>
  </tfoot>
</table>
### table相关的样式属性


 
