# form entype

## application/x-www-form-urlencoded（默认）

- get: 浏览器把form穿成一个字符串（name1=value1&name2=value2...）放到url后
- post: 浏览器把form穿成一个字符串（name1=value1&name2=value2...）封装到html body中

对于普通的HTML Form POST请求:

```html
<form method="post"action="http://w.sohu.com" >
    <input type="text" name="txt1">
    <input type="text" name="txt2">
</form>
```

```
POST / HTTP/1.1
Content-Type:application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate
Host: w.sohu.com
Content-Length: 21
Connection: Keep-Alive
Cache-Control: no-cache
 
txt1=hello&txt2=world

```

## multipart/form-data

当存在type=file的控件时使用，boundary一般是30-40位的随机字符串

```html
<form method="post" action="http://w.sohu.com/upload" enctype="multipart/form-data">
    <input type="text" name="desc">
    <input type="file" name="pic">
</form>
```

```
POST /upload HTTP/1.1
User-Agent: SOHUWapRebot
Accept-Language: zh-cn,zh;q=0.5
Accept-Charset: GBK,utf-8;q=0.7,*;q=0.7
Connection: keep-alive
Content-Length: 60408
Content-Type:multipart/form-data; boundary=ZnGpDtePMx0KrHh_G0X99Yef9r8JZsRJSXC
Host: w.sohu.com
 
--ZnGpDtePMx0KrHh_G0X99Yef9r8JZsRJSXC
Content-Disposition: form-data;name="desc"
Content-Type: text/plain; charset=UTF-8
Content-Transfer-Encoding: 8bit
 
desc=hello
--ZnGpDtePMx0KrHh_G0X99Yef9r8JZsRJSXC
Content-Disposition: form-data;name="pic"; filename="photo.jpg"
Content-Type: application/octet-stream
Content-Transfer-Encoding: binary
 
[图片二进制数据]
--ZnGpDtePMx0KrHh_G0X99Yef9r8JZsRJSXC--
```
