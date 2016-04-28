# 模块

- 总是使用`import/export`进行模块化导入或者导出，而不是其他非标准模块系统。

```javascript
 // bad
const MigStyleGuide = require('./MigbnbStyleGuide');
module.exports = MigStyleGuide.es6;

// ok
import MigStyleGuide from './MigStyleGuide';
export default MigStyleGuide.es6;

// best
import { es6 } from './MigStyleGuide';
export default es6;
```

- 不要从 `import` 中直接 `export`, 让两者各司其职。

```javascript
// bad
// filename es6.js
export { es6 as default } from './MigStyleGuide';

// good
// filename es6.js
import { es6 } from './MigStyleGuide';
export default es6;
```