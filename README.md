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
