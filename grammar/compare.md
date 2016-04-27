# 比较运算符 & 等号

- 优先使用 `===` 和 `!==` 而不是 `== `和 `!=`。

- 条件表达式的强制转换规则：
    
    1. **对象**被计算为 **true**
    2. **undefined**被计算为 **false**
    3. **null**被计算为 false
    4. **布尔值**被计算为**布尔的值**
    5. **数字**如果是**+0**、**-0**、或 **NaN** 被计算为 **false**, 否则为 **true**
    6. **字符串**如果是空字符串`''`,则被计算为**false**，否则为**true**

```javascript
if ([0]) {
    // true
    // An array is an object, objects evaluate to true
}
```

- 使用简写。

```javascript
// bad
if (name !== '') {
    // ...stuff...
}

// good
if (name) {
    // ...stuff...
}

// bad
if (collection.length > 0) {
    // ...stuff...
}

// good
if (collection.length) {
    // ...stuff...
}
```

- 想了解更多信息，参考 Angus Croll 的[Truth Equality and JavaScript](https://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/)。