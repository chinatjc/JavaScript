### 变量

#### 声明变量

```javascript
    var message;
```

<br>

#### 初始化变量

```javascript
    var message = 123;
```

#### 定义的变量，是 ***定义该变量时作用域*** 的 ***局部变量***
```javascript
    function test() {
        var message = 1;
    }
    test();

    console.log(message); // error
```

#### 同时定义多个变量，用逗号 (,) 分隔开，以分号 (;) 结尾
```javascript
    var first = 1,
        second = 2,
        third = 3;
```
