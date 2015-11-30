# 关于 `table-layout`

正常情况下咱们可以设置td的宽度，完全不需要这个`table-layout: fixed`

```html
<tr>
    <td width="20%">hello</td>
    <td width="40%">world</td>
</tr>
```

![](https://raw.githubusercontent.com/cgzero/note/master/img/150914/normal.png)

但是当 **出现一个超级长的英文单词，宽度将被撑开**（除非使用`word-break: break-all`）

```html
<tr>
    <td width="20%">hellohellohellohellohellohellohellohello</td>
    <td width="40%">world</td>
</tr>
```

![](https://raw.githubusercontent.com/cgzero/note/master/img/150914/long-text.png)

加上`table-layout: fixed`就好了

![](https://raw.githubusercontent.com/cgzero/note/master/img/150914/fixed.png)

当然单独依靠这一个属性也是不够的，所以我们需要添加`word-wrap: break-word`让单词折行，必要时还可以添加`word-break: break-all`强制折行

![](https://raw.githubusercontent.com/cgzero/note/master/img/150914/fixed-and-break-word.png)
