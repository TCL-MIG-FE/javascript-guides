# 空格

空格主要用来格式化代码，保证代码的一致性和可阅读性，一般的IDE都可以直接格式化代码。在WebStorm中，我们可以同时按住`Ctrl + ALT + L`来格式代码。

- 使用**4**个空格作为缩进。

```javascript
// bad
function() {
∙∙const name;
}

// good
function() {
∙∙∙∙const name;
}
```


- 在花括号前放一个空格。

```javascript
// bad
function test(){
    console.log('test');
}

// good
function test() {
    console.log('test');
}

// bad
dog.set('attr',{
    age: '1 year',
    breed: 'Bernese Mountain Dog',
});

// good
dog.set('attr', {
    age: '1 year',
    breed: 'Bernese Mountain Dog',
});
```

- 在控制语句（`if`、`while` 等）的小括号前放一个空格。在函数调用及声明中，不在函数的参数列表前加空格。

```javascript
// bad
if(isJedi) {
    fight ();
}

// good
if (isJedi) {
    fight();
}

// bad
function fight () {
    console.log ('Swooosh!');
}

// good
function fight() {
    console.log('Swooosh!');
}
```

- 使用空格把运算符隔开。

```javascript
// bad
const x=y+5;

// good
const x = y + 5;
```
- 在块末和新语句前插入空行。

```javascript
// bad
if (foo) {
    return bar;
}
return baz;

// good
if (foo) {
    return bar;
}

return baz;

// bad
const obj = {
    foo() {
    },
    bar() {
    }
};
return obj;

// good
const obj = {
    foo() {
    },

    bar() {
    }
};

return obj;
```

- 在使用长方法链时进行缩进。使用前面的点**`.`**强调这是方法调用而不是新语句。

```javascript
// bad
$('#items').find('.selected').highlight().end().find('.open').updateCount();

// bad
$('#items').
  find('.selected').
    highlight().
    end().
  find('.open').
    updateCount();

// good
$('#items')
  .find('.selected')
    .highlight()
    .end()
  .find('.open')
    .updateCount();
```