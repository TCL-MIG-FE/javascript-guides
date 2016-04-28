# 命名规则

- 避免单字母命名，命名应具备描述性。

```javascript
// bad
function q() {
  // ...stuff...
}

// good
function query() {
  // ..stuff..
}
```

- 使用驼峰式命名对象、函数和实例。

```javascript
// bad
const OBJEcttsssss = {};
const this_is_my_object = {};
function c() {}

// good
const thisIsMyObject = {};
function thisIsMyFunction() {}
```
- 使用Pascal式命名构造函数或类。

```javascript
// bad
function user(options) {
    this.name = options.name;
}

const bad = new user({
    name: 'nope',
});

// good
class User {
    constructor(options) {
        this.name = options.name;
    }
}

const good = new User({
    name: 'yup',
});
```

- 使用下划线`_`开头命名私有属性。

```javascript
// bad
this.__firstName__ = 'Panda';
this.firstName_ = 'Panda';

// good
this._firstName = 'Panda';
```

- 别保存`this`的引用。使用箭头函数或 [`Function#bind`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)。

```javascript
// bad
function foo() {
    const self = this;
    return function() {
        console.log(self);
    };
}

// bad
function foo() {
    const that = this;
    return function() {
        console.log(that);
    };
}

// good
function foo() {
    return () => {
        console.log(this);
    };
}
```

- 如果文件只输出一个类，文件名必须和类名完全保持一致。

```javascript
// file contents
class CheckBox {
    // ...
}

export default CheckBox;

// in some other file
// bad
import CheckBox from './checkBox';

// bad
import CheckBox from './check_box';

// good
import CheckBox from './CheckBox';
```

- 导出默认的函数时使用驼峰式命名

```javascript
function makeStyleGuide() {
}

export default makeStyleGuide;
```

- 导出单例、函数库、空对象时使用帕斯卡式命名。

```javascript
const MigStyleGuide = {
  es6: {
  }
};

export default MigStyleGuide;
```