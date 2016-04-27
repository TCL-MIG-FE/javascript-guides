# 对象

- 使用字面值创建对象。

```javascript
// bad
const item = new Object();

// good
const  item = {};
```

- 不要使用[保留字](http://es5.github.io/#x7.6.1)作为键名。

```javascript
// bad
const superman = {
    default: { clark: 'kent' },
    private: true
};

// good
const superman = {
    defaults: { clark: 'kent' },
    hidden: true
};
```

- 使用同义词替换需要使用的保留字。

```javascript
// bad
const superman = {
    class: 'alien'
};

// bad
const superman = {
  klass: 'alien'
};

// good
const superman = {
  type: 'alien'
};
```


- 创建有动态属性名的对象时，使用可被计算的属性名称。
  [include](../codes/basic-object.js)


- 使用对象属性值的简写。

```javascript
const lukeSkywalker = 'Luke Skywalker';

// bad
const obj = {
  lukeSkywalker: lukeSkywalker,
};

// good
const obj = {
  lukeSkywalker,
};
```

- 在对象属性声明前把简写的属性分组。

```javascript
    const anakinSkywalker = 'Anakin Skywalker';
    const lukeSkywalker = 'Luke Skywalker';

    // bad
    const obj = {
        episodeOne: 1,
        twoJedisWalkIntoACantina: 2,
        lukeSkywalker,
        episodeThree: 3,
        mayTheFourth: 4,
        anakinSkywalker,
    };

    // good
    const obj = {
        lukeSkywalker,
        anakinSkywalker,
        episodeOne: 1,
        twoJedisWalkIntoACantina: 2,
        episodeThree: 3,
        mayTheFourth: 4,
    };
```