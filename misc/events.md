# 事件处理

- 当给事件附加数据时（无论是 DOM 事件还是私有事件），传入一个哈希而不是原始值,这样会使程序具有更好的扩展性。

```javascript
// bad
$(this).trigger('listingUpdated', listing.id);

...

$(this).on('listingUpdated', function(e, listingId) {
  // do something with listingId
});
```

更好的写法：
```javascript
// good
$(this).trigger('listingUpdated', { listingId : listing.id });

...

$(this).on('listingUpdated', function(e, data) {
  // do something with data.listingId
});
```