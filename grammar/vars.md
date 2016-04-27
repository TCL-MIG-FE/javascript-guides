# 变量

- `let` vs `var`

```javascript
var a = 5;
var b = 10;

if (a === 5) {
  let a = 4; // The scope is inside the if-block
  var b = 1; // The scope is inside the function

  console.log(a);  // 4
  console.log(b);  // 1
} 

console.log(a); // 5
console.log(b); // 1
```

- 直使用 const 来声明变量，避免产生全局变量

```javascript
// bad
superPower = new SuperPower();

// good
const superPower = new SuperPower();
```

- 使用 const 声明每一个变量。
> 为什么？增加新变量将变的更加容易，而且你永远不用再担心调换错 `;` 跟 `,`。

```javascript
// bad
const items = getItems(),
    goSportsTeam = true,
    dragonball = 'z';

// bad
// (compare to above, and try to spot the mistake)
const items = getItems(),
    goSportsTeam = true;
    dragonball = 'z';

// good
const items = getItems();
const goSportsTeam = true;
const dragonball = 'z';
```

- 将所有的 const 和 let 分组

```javascript   
// bad
let i, len, dragonball,
  items = getItems(),
  goSportsTeam = true;

// bad
let i;
const items = getItems();
let dragonball;
const goSportsTeam = true;
let len;

// good
const goSportsTeam = true;
const items = getItems();
let dragonball;
let i;
let length;
```