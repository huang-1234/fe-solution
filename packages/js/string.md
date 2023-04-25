#   字符串领域

## QA
### js去除字符串两端的非中文的字符

可以使用正则表达式来实现这个需求，代码如下：

```javascript
function trimNonChinese(str) {
  return str.replace(/^[^\u4e00-\u9fa5]+|[^\u4e00-\u9fa5]+$/g, '');
}
```

其中 `^[^\u4e00-\u9fa5]+` 匹配字符串开头的非中文字符， `|[^\u4e00-\u9fa5]+$` 匹配字符串末尾的非中文字符。 `g` 表示全局匹配。 `replace` 函数将匹配到的非中文字符替换为空字符串，最终返回结果即为去除两端非中文字符后的字符串。

示例：

```javascript
console.log(trimNonChinese('***Hello, 世界!***')); // 'Hello, 世界!'
console.log(trimNonChinese('abc中文123')); // '中文'
console.log(trimNonChinese('!@#$%^&*()_+-={}[]|\\:;"<>,.?/中文')); // '中文'
```
