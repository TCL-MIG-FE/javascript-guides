# 逗号 & 分号

- 不要在行首出现逗号

```javascript
// bad
const story = [
    once
  , upon
  , aTime
];

// good
const story = [
    once,
    upon,
    aTime
];

// bad
const hero = {
    firstName: 'Ada'
  , lastName: 'Lovelace'
  , birthYear: 1815
  , superPower: 'computers'
};

// good
const hero = {
    firstName: 'Ada',
    lastName: 'Lovelace',
    birthYear: 1815,
    superPower: 'computers'
};
```

- 在语句的介绍或者匿名函数的头部加入分号

```javascript
// bad
(function() {
  const name = 'Skywalker'
  return name
})()

// good
(() => {
    const name = 'Skywalker';
    return name;
})();

// good (防止函数在两个 IIFE 合并时被当成一个参数)
;(() => {
  const name = 'Skywalker';
  return name;
})();
```