# scrollTop 注意事项

对于网页的 `scrollTop`，如下代码在 chrome 正常，但是 ie 和 ff 会异常

```js 
    document.body.scrollTop
    $('body').scrollTop()

```

所以如果使用的话，使用：

```js
    document.body.scrollTop || document.documentElement.scrollTop
    $(window).scrollTop()
    $(document).scrollTop()
    $('html, body').scrollTop()

```

`body.scrollTop` 和 `documentElement.scrollTop` 兼容性如下

标准模式（`document.compatMode == BackCompat`）：

| | body.scrollTop | documentElement.scrollTop  |
| --- | --- | --- |
| ie6 | 正常 | 0 |
| ie7/8/9 | 正常 | 0 |
| ie10/11 |  正常 | 正常 |
| chrome | 正常 | 0 |
| ff | 正常 | 0 |

混杂模式（`document.compatMode == CSS1Compat`）：

| | body.scrollTop | documentElement.scrollTop  |
| --- | --- | --- |
| ie6 | 0 | 正常 |
| ie7/8/9 | 0 | 正常 |
| ie10/11 | 0 | 正常 |
| chrome | 正常 | 0 |
| ff | 0 | 正常 |
