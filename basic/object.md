# 对象

- 使用直接量创建对象。

    ```javascript
    // bad
    var item = new Object();

    // good
    var item = {};
    ```

- 不要使用[保留字](http://es5.github.io/#x7.6.1)作为键名，它们在 IE8 下不工作。[更多信息](https://github.com/airbnb/javascript/issues/61)。

    ```javascript
    // bad
    var superman = {
      default: { clark: 'kent' },
      private: true
    };

    // good
    var superman = {
      defaults: { clark: 'kent' },
      hidden: true
    };
    ```

- 使用同义词替换需要使用的保留字。

    ```javascript
    // bad
    var superman = {
      class: 'alien'
    };

    // bad
    var superman = {
      klass: 'alien'
    };

    // good
    var superman = {
      type: 'alien'
    };
    ```