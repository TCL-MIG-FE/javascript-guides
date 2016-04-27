# 变量提升

- `var` 声明会被提升至该作用域的顶部，但它们赋值不会提升。`let` 和 `const` 被赋予了一种称为[「暂时性死区（Temporal Dead Zones, TDZ）」](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_dead_zone_and_errors_with_let)的概念。这对于了解为什么 [type of](http://es-discourse.com/t/why-typeof-is-no-longer-safe/15) 不再安全相当重要。

```javascript
// 我们知道这样运行不了 
// （假设 notDefined 不是全局变量）
function example() {
    console.log(notDefined); // => throws a ReferenceError
}

// 由于变量提升的原因，
// 在引用变量后再声明变量是可以运行的。
// 注：变量的赋值 `true` 不会被提升。
function example() {
    console.log(declaredButNotAssigned); // => undefined
    var declaredButNotAssigned = true;
}

// 编译器会把函数声明提升到作用域的顶层，
// 这意味着我们的例子可以改写成这样：
function example() {
    let declaredButNotAssigned;
    console.log(declaredButNotAssigned); // => undefined
    declaredButNotAssigned = true;
}

// 使用 const 和 let
function example() {
    console.log(declaredButNotAssigned); // => throws a ReferenceError
    console.log(typeof declaredButNotAssigned); // => throws a ReferenceError
    const declaredButNotAssigned = true;
}
```

- 匿名函数表达式的变量名会被提升，但函数内容并不会。

```javascript
function example() {
    console.log(anonymous); // => undefined

    anonymous(); // => TypeError anonymous is not a function

    var anonymous = function() {
        console.log('anonymous function expression');
    };
}
```

- 命名的函数表达式的变量名会被提升，但函数名和函数函数内容并不会。

```javascript
function example() {
    console.log(named); // => undefined

    named(); // => TypeError named is not a function

    superPower(); // => ReferenceError superPower is not defined

    var named = function superPower() {
        console.log('Flying');
    };
}

// the same is true when the function name
// is the same as the variable name.
function example() {
    console.log(named); // => undefined

    named(); // => TypeError named is not a function

    var named = function named() {
        console.log('named');
    }
}
```

- 函数声明的名称和函数体都会被提升。

```javascript
function example() {
    superPower(); // => Flying

    function superPower() {
        console.log('Flying');
    }
}
```