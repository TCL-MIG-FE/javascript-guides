# 字符串

- 使用单引号 `''` 包裹字符串。

```javascript
// bad
const name = "Bob Parr";

// good
const name = 'Bob Parr';

// bad
const fullName = "Bob " + this.lastName;

// good
const fullName = 'Bob ' + this.lastName;
```

- 超过 100 个字符的字符串应该使用连接符写成多行。

```javascript
// bad
const errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';

// bad
const errorMessage = 'This is a super long error that was thrown because \
of Batman. When you stop to think about how Batman had anything to do \
with this, you would get nowhere \
fast.';

// good
const errorMessage = 'This is a super long error that was thrown because ' +
    'of Batman. When you stop to think about how Batman had anything to do ' +
    'with this, you would get nowhere fast.';
```

- 程序化生成字符串时，使用模板字符串代替字符串连接。

```javascript
// bad
function sayHi(name) {
    return 'How are you, ' + name + '?';
}

// bad
function sayHi(name) {
    return ['How are you, ', name, '?'].join();
}

// good
function sayHi(name) {
    return `How are you, ${name}?`;
}
```