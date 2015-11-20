# Unicode 和 UTF-8 的关系

## 概要

- 位（bit）字节（byte）
    - 位：两种状态
    - 字节：2^8 256种状态
- Unicode字母A: `\u0041`1 汉字严: `\u4E25`
- Unicode只是符号集，只规定了符号的二进制代码，没有规二进制代码如何存储
- UTF-8是Unicode的实现方式之一，其他实现方式还有UTF-16，UTF-32
- UTF-8是变长编码方式

## 编码规则

- 第一位是0：字符为一个字节
- 第一位是1：连续有多少个1，就表示当前字符占用多少个字节

```
Unicode符号范围（十六进制） | UTF-8编码方式（二进制）
0000 0000 -> 0000 007F | 0xxxxxxx （等同于ASCII）
0000 0080 -> 0000 07FF | 110xxxxx 10xxxxxx 
0000 0800 -> 0000 FFFF | 1110xxxx 10xxxxxx 10xxxxxx 
0001 0000 -> 0010 FFFF | 11110xxx 10xxxxxx 10xxxxxx 10xxxxxx
```

例如严（4E25）（0100 1110 0010 0101）

```
规则：0000 0800 -> 0000 FFFF | 1110xxxx 10xxxxxx 10xxxxxx 
格式：1110{0100} 10{111000} 10{100101}
```

## 参考：

- <http://www.ruanyifeng.com/blog/2007/10/ascii_unicode_and_utf-8.html>
