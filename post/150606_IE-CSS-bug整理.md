# IE CSS bug 整理

## IE6/7 `inline-block` 不要用 `text-indent` 去删除文字

- 使用`block`
- 或者`font-size:0; line-height:0;`
- `line-height:特别大; overflow:hidden;`

## IE6 `float` 宽度无法自适应

ie6下设置li的float属性后导致宽度不能自适应

```html
<ul> 
    <li><a href="#">ie6x</a></li> 
    <li><a href="#">IE6XXX</a></li> 
</ul> 
```

解决办法，给嵌套的“a”标签也设置float属性

## IE6 line-hight bug

如果元素内既有inline元素又有inline-block，line-height会失效

解决方法：
1. 都设为`inline-block`
2. 给`inline-block`加上`_margin-top`

## IE6/7 下 `margin` 定位元素和绝对定位元素重叠

```html
<div class="box">
    <span class="abs">pic</span>
    <div class="ml140">txt</div>
</div>
```

```css
.box { width:350px; }
.abs { position:absolute; }
.ml140 { margin-left:140px; }
```

解决方法：左侧浮动元素为inline标签
