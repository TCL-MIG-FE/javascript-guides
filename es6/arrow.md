# 箭头函数

- 当你必须使用函数表达式（或传递一个匿名函数）时，使用箭头函数符号。

箭头函数会创造一个新的`this`执行环境（参考[Arrow Functions -MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/Arrow_functions)），同时会是代码更简洁。

```javascript

// bad
[1, 2, 3].map(function (x) {
    return x * x;
});


// good
[1, 2, 3].map((x) => {
return x * x;
});
```

- 如果一个函数适合用一行写出并且只有一个参数，那就把花括号、圆括号和 `return`都省略掉。如果不是，那就不要省略。

```javascript
// good
[1, 2, 3].map(x => x * x);

// good
[1, 2, 3].reduce((total, n) => {
    return total + n;
}, 0);
```

