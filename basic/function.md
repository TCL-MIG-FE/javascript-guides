# 函数

- 函数表达式：

```javascript
// 匿名函数表达式
const anonymous = function() {
    return true;
};

// 命名函数表达式
const named = function named() {
    return true;
};

// 立即调用的函数表达式（IIFE）
(function() {
    console.log('Welcome to the Internet. Please follow me.');
})();
```

- 永远不要在一个非函数代码块（`if`、`while` 等）中声明一个函数，然后把那个函数赋给一个变量。浏览器允许你这么做，但它们的解析表现不一致。

```javascript
// bad
if (currentUser) {
    function test() {
      console.log('Nope.');
    }
}

// good
let test;
if (currentUser) {
    test = function test() {
      console.log('Yup.');
    };
}
```

- 永远不要把参数命名为 `arguments`。这将取代函数作用域内的 `arguments` 对象。

```javascript
// bad
function nope(name, options, arguments) {
    // ...stuff...
}

// good
function yup(name, options, args) {
    // ...stuff...
}
```

- 尽量少用 arguments。可以选择 rest 语法 ... 替代。

```javascript

  // bad
  function concatenateAll() {
      const args = Array.prototype.slice.call(arguments);
      return args.join('');
  }

  // good
  function concatenateAll(...args) {
      return args.join('');
  }
```

- 直接给函数的参数指定默认值，不要使用一个变化的函数参数。

```javascript
// bad
function handleThings(opts) {
  opts = opts || {};
  // ...
}

// good
function handleThings(opts = {}) {
  // ...
}
```

- 直接给函数参数赋值时需要避免副作用。

```javascript
var b = 1;
// bad
function count(a = b++) {
  console.log(a);
}
count();  // => 1
count();  // => 2
count(3); // => 3
count();  // => 3
```
