# 数组

- 使用直接量创建数组。

    ```javascript
    // bad
    var items = new Array();

    // good
    var items = [];
    ```

- 向数组增加元素时使用 Array#push 来替代直接赋值。

    ```javascript

    var someStack = [];

    // bad
    someStack[someStack.length] = 'something string';

    // good
    someStack.push('something string');
    ```

- 当你需要拷贝数组时，使用 Array#slice。

    ```javascript
    var len = items.length;
    var itemsCopy = [];
    var i;

    // bad
    for (i = 0; i < len; i++) {
      itemsCopy[i] = items[i];
    }

    // good
    itemsCopy = items.slice();
    ```

- 使用 Array#slice 将类数组对象转换成数组。

    ```javascript
    function trigger() {
      var args = Array.prototype.slice.call(arguments);
      ...
    }
    ```