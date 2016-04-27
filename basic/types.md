# 类型

- **原始值**: 存取直接作用于它自身。

    + `string`
    + `number`
    + `boolean`
    + `null`
    + `undefined`

    ```javascript
    const foo = 1;
    let bar = foo;

    bar = 9;

    console.log(foo, bar); // => 1, 9
    ```

- **复杂类型**: 存取时作用于它自身值的引用。

    + `object`
    + `array`
    + `function`

    ```javascript
    const foo = [1, 2];
    let bar = foo;

    bar[0] = 9;

    console.log(foo[0], bar[0]); // => 9, 9
    ```

- **判断具体类型**

    ```javascript
    const array = [];
    const nodes = document.querySelectorAll("h1");

    const getType = (v) => Object.prototype.toString.call(v);

    console.log(getType(array)) // => "[object Array]"

    console.log(getType(nodes)) // => "[object NodeList]"

    console.log(typeof(nodes)) // => "object"

    ```

    **注意**： 通过`typeof`也可以获取变量的类型，但不是太准确，酌情使用


- null vs undefined
    
    `null`是一个对象，`undefined`是`window`的一个属性。

    ```javascript
    typeof(null) // => "object"
    typeof(undefined) // => "undefined"

    const getType = (v) => Object.prototype.toString.call(v);

    getType(null) // => "[object Null]"
    getType(undefined) // => "[object undefined]"

    console.log( null == undefined ) // => true
    console.log( null === undefined ) // => true
 
    ```


