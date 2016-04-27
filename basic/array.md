# 数组

- 使用直接量创建数组。

```javascript
// bad
const items = new Array();

// good
const items = [];
```

- 向数组增加元素时使用 Array#push 来替代直接赋值。

```javascript

const someStack = [];

// bad
someStack[someStack.length] = 'something string';

// good
someStack.push('something string');
```

- 使用拓展运算符 `...` 复制数组。

```javascript
// bad
const len = items.length;
const itemsCopy = [];
let i;

for (i = 0; i < len; i++) {
    itemsCopy[i] = items[i];
}

// good
const itemsCopy = [...items];
```


- 使用 Array#slice 将类数组对象转换成数组。

```javascript
function trigger() {
  const args = Array.prototype.slice.call(arguments);
  ...
}
```