对于网页的scrollTop，如下代码在chrome正常，但是ie和ff会异常

```javascript 

    document.body.scrollTop
    $('body').scrollTop()

```

所以如果使用的话，使用：

```javascript

    document.body.scrollTop || document.documentElement.scrollTop
    $(window).scrollTop()
    $(document).scrollTop()
    $('html, body').scrollTop()

```

body.scrollTop和documentElement.scrollTop兼容性如下

document.compatMode == BackCompat

| | body.scrollTop | documentElement.scrollTop  |
| --- | --- | --- |
| ie6 | 正常 | 0 |
| ie7/8/9 | 正常 | 0 |
| ie10/11 |  正常 | 正常 |
| chrome | 正常 | 0 |
| ff | 正常 | 0 |

document.compatMode == CSS1Compat

| | body.scrollTop | documentElement.scrollTop  |
| --- | --- | --- |
| ie6 | 0 | 正常 |
| ie7/8/9 | 0 | 正常 |
| ie10/11 | 0 | 正常 |
| chrome | 正常 | 0 |
| ff | 0 | 正常 |
