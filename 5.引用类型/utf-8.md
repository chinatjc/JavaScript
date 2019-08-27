> utf-8 编码

- utf-8 用1～4个字节编码 unicode字符
- unicode编号 -> utf-8编码
    - 查找字符对应的 `16进制unicode编号`
    - 查找 `下面列表` 中对应 `unicode编号区间段`
    - 用 `2进制的unicode编号` 去填充 utf-8 的缺省位置，不够的补0
    - 最终用 `16进制数` 来表示 utf-8编码

```javascript
    const str = '中';
    const unicodeCode16 = str.codePointAt().toString(16); // 4e2d，对应 utf-8对照表中的第三行
    const unicodeCode2 = str.codePointAt().toString(2); // 100111000101101
    const utf8Code2 = '111001001011100010101101'; // 100111000101101 + 1110xxxx 10xxxxxx 10xxxxxx -> 111001001011100010101101
    const utf8Code16 = parseInt(utf8Code2, 2).toString(16); // e4b8ad
```

- unicode编号 与 utf-8编码对照表

Unicode编号(十六进制) | UTF-8 字节流(二进制)
   :-:               |   :-
00000000 - 0000007F  | 0xxxxxxx
00000080 - 000007FF  | 110xxxxx 10xxxxxx
00000800 - 0000FFFF  | 1110xxxx 10xxxxxx 10xxxxxx
00010000 - 001FFFFF  | 11110xxx 10xxxxxx 10xxxxxx 10xxxxxx
00200000 - 03FFFFFF  | 111110xx 10xxxxxx 10xxxxxx 10xxxxxx 10xxxxxx
04000000 - 7FFFFFFF  | 1111110x 10xxxxxx 10xxxxxx 10xxxxxx 10xxxxxx 10xxxxxx
