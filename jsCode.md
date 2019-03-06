积累的``JS``代码片段

+ 浮点数取整
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

+ 生成6位数字验证码
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

+ 16进制颜色代码生成
```JavaScript
(function() {
  return '#'+('00000'+
    (Math.random()*0x1000000<<0).toString(16)).slice(-6);
})();
```

+ 驼峰命名转下划线
```JavaScript
'componentWillReceivePr ops'.match(/^[a-z][a-z0-9]+|[A-Z][a-z0-9]*/g).join('_').toLowerCase(); // component_will_receive_props
```

+ url查询参数转json格式
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

+ 获取URL参数
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

+ 日期格式化
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

+ n维数组展开成一维数组
```JavaScript
var foo = [1, [2, 3], ['4', 5, ['6',7,[8]]], [9], 10];

// 方法一
// 限制：数组项不能出现`,`，同时数组项全部变成了字符数字
foo.toString().split(','); // ["1", "2", "3", "4", "5", "6", "7", "8", "9", "10"]

// 方法二
// 转换后数组项全部变成数字了
eval('[' + foo + ']'); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

// 方法三，使用ES6展开操作符
// 写法太过麻烦，太过死板
[1, ...[2, 3], ...['4', 5, ...['6',7,...[8]]], ...[9], 10]; // [1, 2, 3, "4", 5, "6", 7, 8, 9, 10]

// 方法四
JSON.parse(`[${JSON.stringify(foo).replace(/\[|]/g, '')}]`); // [1, 2, 3, "4", 5, "6", 7, 8, 9, 10]

// 方法五
const flatten = (ary) => ary.reduce((a, b) => a.concat(Array.isArray(b) ? flatten(b) : b), []);
flatten(foo); // [1, 2, 3, "4", 5, "6", 7, 8, 9, 10]

// 方法六
function flatten(a) {
  return Array.isArray(a) ? [].concat(...a.map(flatten)) : a;
}
flatten(foo); // [1, 2, 3, "4", 5, "6", 7, 8, 9, 10]

// 方法七
var flatten = function(arr) {
  var result = [];
  var flat = function* (a) {
    var length = a.length;
    for (var i = 0; i < length; i++) {
      var item = a[i];
      if (typeof item !== 'number') {
        yield * flat(item);
      } else {
        yield item;
      }
    }
  }

  for (var f of flat(arr)) {
    result.push(f);
  }

  return result;
}
```

+ 统计文字个数
```JavaScript
function wordCount(data) {
  var pattern = /[a-zA-Z0-9_\u0392-\u03c9]+|[\u4E00-\u9FFF\u3400-\u4dbf\uf900-\ufaff\u3040-\u309f\uac00-\ud7af]+/g;
  var m = data.match(pattern);
  var count = 0;
  if( m === null ) return count;
  for (var i = 0; i < m.length; i++) {
    if (m[i].charCodeAt(0) >= 0x4E00) {
      count += m[i].length;
    } else {
      count += 1;
    }
  }
  return count;
}

var text = '贷款买房，也意味着你能给自己的资产加杠杆，能够撬动更多的钱，来孳生更多的财务性收入。';
wordCount(text); // 38
```

+ 特殊字符转义
```JavaScript
function htmlspecialchars (str) {
  var str = str.toString().replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, '&quot;');
  return str;
}

htmlspecialchars('&jfkds<>'); // "&amp;jfkds&lt;&gt;"
```

+ 动态插入js
```JavaScript
function injectScript(src) {
    var s, t;
    s = document.createElement('script');
    s.type = 'text/javascript';
    s.async = true;
    s.src = src;
    t = document.getElementsByTagName('script')[0];
    t.parentNode.insertBefore(s, t);
}
```

+ 格式化数量
```JavaScript
// 方法一
function formatNum (num, n) {
  if (typeof num == "number") {
    num = String(num.toFixed(n || 0));
    var re = /(-?\d+)(\d{3})/;
    while (re.test(num)) num = num.replace(re, "$1,$2");
    return num;
  }
  return num;
}

formatNum(2313123, 3); // "2,313,123.000"

// 方法二
'2313123'.replace(/\B(?=(\d{3})+(?!\d))/g, ','); // "2,313,123"

// 方法三
function formatNum(str) {
  return str.split('').reverse().reduce((prev, next, index) => {
    return ((index % 3) ? next : (next + ',')) + prev
  });
}

formatNum('2313323'); // "2,313,323"
```

+ 身份证验证
```JavaScript
function chechCHNCardId(sNo) {
  if (!this.regExpTest(sNo, /^[0-9]{17}[X0-9]$/)) {
    return false;
  }
  sNo = sNo.toString();

  var a, b, c;
  a = parseInt(sNo.substr(0, 1)) * 7 + parseInt(sNo.substr(1, 1)) * 9 + parseInt(sNo.substr(2, 1)) * 10;
  a = a + parseInt(sNo.substr(3, 1)) * 5 + parseInt(sNo.substr(4, 1)) * 8 + parseInt(sNo.substr(5, 1)) * 4;
  a = a + parseInt(sNo.substr(6, 1)) * 2 + parseInt(sNo.substr(7, 1)) * 1 + parseInt(sNo.substr(8, 1)) * 6;
  a = a + parseInt(sNo.substr(9, 1)) * 3 + parseInt(sNo.substr(10, 1)) * 7 + parseInt(sNo.substr(11, 1)) * 9;
  a = a + parseInt(sNo.substr(12, 1)) * 10 + parseInt(sNo.substr(13, 1)) * 5 + parseInt(sNo.substr(14, 1)) * 8;
  a = a + parseInt(sNo.substr(15, 1)) * 4 + parseInt(sNo.substr(16, 1)) * 2;
  b = a % 11;

  if (b == 2) {
    c = sNo.substr(17, 1).toUpperCase();
  } else {
    c = parseInt(sNo.substr(17, 1));
  }

  switch (b) {
    case 0:
      if (c != 1) {
        return false;
      }
      break;
    case 1:
      if (c != 0) {
        return false;
      }
      break;
    case 2:
      if (c != "X") {
        return false;
      }
      break;
    case 3:
      if (c != 9) {
        return false;
      }
      break;
    case 4:
      if (c != 8) {
        return false;
      }
      break;
    case 5:
      if (c != 7) {
        return false;
      }
      break;
    case 6:
      if (c != 6) {
        return false;
      }
      break;
    case 7:
      if (c != 5) {
        return false;
      }
      break;
    case 8:
      if (c != 4) {
        return false;
      }
      break;
    case 9:
      if (c != 3) {
        return false;
      }
      break;
    case 10:
      if (c != 2) {
        return false;
      };
  }
  return true;
}
```

+ 测试质数
```JavaScript
function isPrime(n) {
  return !(/^.?$|^(..+?)\1+$/).test('1'.repeat(n))
}
```

+ 统计字符串中相同字符出现的次数
```JavaScript
var arr = 'abcdaabc';

var info = arr
    .split('')
    .reduce((p, k) => (p[k]++ || (p[k] = 1), p), {});
    
console.log(info); //{ a: 3, b: 2, c: 2, d: 1 }
```

+ 使用void 0来解决undefined被污染问题
```JavaScript
undefined = 1;
!!undefined; // true
!!void(0); // false
```

+ 单行写一个评级组件
```JavaScript
"★★★★★☆☆☆☆☆".slice(5 - rate, 10 - rate);
```

+ JavaScript 错误处理的方式的正确姿势
```JavaScript
try {
    something
} catch (e) {
    window.location.href =
        "http://stackoverflow.com/search?q=[js]+" +
        e.message;
}
```

+ 匿名函数自执行写法
```JavaScript
( function() {}() );
( function() {} )();
[ function() {}() ];

~ function() {}();
! function() {}();
+ function() {}();
- function() {}();

delete function() {}();
typeof function() {}();
void function() {}();
new function() {}();
new function() {};

var f = function() {}();

1, function() {}();
1 ^ function() {}();
1 > function() {}();
```
