# jQuery最佳实践

- 使用 `$` 作为`jQuery`对象变量名的前缀。

```javascript
// bad
const sidebar = $('.sidebar');

// good
const $sidebar = $('.sidebar');
```

- 缓存 jQuery 查询。

```javascript
// bad
function setSidebar() {
    $('.sidebar').hide();

    // ...stuff...

    $('.sidebar').css({
    'background-color': 'pink'
    });
}

// good
function setSidebar() {
    const $sidebar = $('.sidebar');
    $sidebar.hide();

    // ...stuff...

    $sidebar.css({
        'background-color': 'pink'
    });
}
```

- 尽量使用`jQuery`的`find`方法来获取`DOM`

```javascript
// bad
$('ul', '.sidebar').hide();


// good
$('.sidebar ul').hide();

// good
$('.sidebar > ul').hide();

// good
$sidebar.find('ul').hide();
```