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

+  url查询参数转json格式
```JavaScript
// ES6
const query = (search = '') => ((querystring = '') => (q => (querystring.split('&').forEach(item => (kv => kv[0] && (q[kv[0]] = kv[1]))(item.split('='))), q))({}))(search.split('?')[1]);

// 对应ES5实现
var query = function(search) {
  if (search === void 0) { search = ''; }
  return (function(querystring) {
    if (querystring === void 0) { querystring = ''; }
    return (function(q) {
      return (querystring.split('&').forEach(function(item) {
        return (function(kv) {
          return kv[0] && (q[kv[0]] = kv[1]);
        })(item.split('='));
      }), q);
    })({});
  })(search.split('?')[1]);
};

query('?key1=value1&key2=value2'); // es6.html:14 {key1: "value1", key2: "value2"}
```

+  获取URL参数
```JavaScript
function getQueryString(key){
  var reg = new RegExp("(^|&)"+ key +"=([^&]*)(&|$)");
  var r = window.location.search.substr(1).match(reg);
  if(r!=null){
      return  unescape(r[2]);
  }
  return null;
}
```

+  日期格式化
```JavaScript
// 方法一
function format1(x, y) {
  var z = {
    y: x.getFullYear(),
    M: x.getMonth() + 1,
    d: x.getDate(),
    h: x.getHours(),
    m: x.getMinutes(),
    s: x.getSeconds()
  };
  return y.replace(/(y+|M+|d+|h+|m+|s+)/g, function(v) {
    return ((v.length > 1 ? "0" : "") + eval('z.' + v.slice(-1))).slice(-(v.length > 2 ? v.length : 2))
  });
}

format1(new Date(), 'yy-M-d h:m:s'); // 19-03-03 23:20:14

// 方法二
Date.prototype.format = function (fmt) { 
  var o = {
    "M+": this.getMonth() + 1, //月份 
    "d+": this.getDate(), //日 
    "h+": this.getHours(), //小时 
    "m+": this.getMinutes(), //分 
    "s+": this.getSeconds(), //秒 
    "q+": Math.floor((this.getMonth() + 3) / 3), //季度 
    "S": this.getMilliseconds() //毫秒 
  };
  if (/(y+)/.test(fmt)){
    fmt = fmt.replace(RegExp.$1, (this.getFullYear() + "").substr(4 - RegExp.$1.length));
  } 
  for (var k in o){
    if (new RegExp("(" + k + ")").test(fmt)){
      fmt = fmt.replace(RegExp.$1, (RegExp.$1.length == 1) ? (o[k]) : (("00" + o[k]).substr(("" + o[k]).length)));
    }
  }     
  return fmt;
}

new Date().format('yy-M-d h:m:s'); // 19-03-03 23:29:41
```