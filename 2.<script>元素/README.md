### 在 HTML 中使用 JavaScript

#### <script> src 属性

> src可以指定 **任何域** 的js，不受同源策略的影响

<br>

#### <script> 元素的加载顺序

> 一般的加载方式：在html中遇到<script>时，停止html的解析与渲染，进行<script>的加载和执行代码，完成之后再进行html的解析与渲染

```html
    <script type="text/javascript" src="js/main.js"></script>
```

![Alt text](https://i.loli.net/2018/11/21/5bf4e2099d1e5.png "Optional title")

<br>

> async：在html中遇到<script>时，异步加载js，html的解析与渲染没有阻塞，js加载完成之后，停止html的解析与渲染，执行js代码，完成之后再进行html的解析与渲染

```html
    <script type="text/javascript" src="js/main.js" async></script>
```

![Alt text](https://i.loli.net/2018/11/21/5bf4e33ba5320.png "Optional title")

<br>

> defer：在html中遇到<script>时，异步加载js，html的解析与渲染没有阻塞，js加载完成之后，等待浏览器遇到<\/html>标签之后，再执行js代码

```html
    <script type="text/javascript" src="js/main.js" defer></script>
```

![Alt text](https://i.loli.net/2018/11/21/5bf4e3ef30957.png "Optional title")

<br>

#### \<noscript\>

> 在不支持javascript脚本的情况下，会执行\<noscript\>里的代码，否则浏览器会忽视\<noscript\>

```html
    <!-- 当不支持javascript脚本时，会执行<noscript>里的代码，跳转到相应的页面 -->
    <noscript>
        <meta http-equiv=refresh content="0; url=http://www.baidu.com/baidu.html?from=noscript">
    </noscript>
```
