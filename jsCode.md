积累的``JS``代码片段

+  浮点数取整
```JavaScript
const x = 123.4545;
x >> 0; // 123
~~x; // 123
x | 0; // 123
Math.floor(x); // 123
```

> 注意：前三种方法只适用于32个位整数，对于负数的处理上和``Math.floor``是不同的。

```JavaScript
Math.floor(-12.53); // -13
-12.53 | 0; // -12
```

+  生成6位数字验证码
```JavaScript
// 方法一
('000000' + Math.floor(Math.random() *  999999)).slice(-6);

// 方法二
Math.random().toString().slice(-6);

// 方法三
Math.random().toFixed(6).slice(-6);

// 方法四
'' + Math.floor(Math.random() * 999999);
```

+  16进制颜色代码生成
```JavaScript
(function() {
  return '#'+('00000'+
    (Math.random()*0x1000000<<0).toString(16)).slice(-6);
})();
```

+  驼峰命名转下划线
```JavaScript
'componentWillReceiveProps'.match(/^[a-z][a-z0-9]+|[A-Z][a-z0-9]*/g).join('_').toLowerCase(); // component_will_receive_props
```