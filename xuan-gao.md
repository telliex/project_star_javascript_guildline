### 1.1 变量声明以 `let`、`const` 替代 `var`
```
// bad code
MyGlobalVariable

// good code
let myGlobalVariable;
const yourGlobalVariable;
```

### 1.2 变量在函数内部或循环控制条件之前提前声明
```
// bad code
function test(){
    for(var i=0;i<list.length;i++){
        var item=list[i];
    }
}

// good code
function test(){
let i;
let item;
let len=list.length;
    for(i=0;i<len;i++){
        item=list[i];
    }
}
```

### 1.3 变量必须在声明初始化以后才能使用，即便是 NULL 类型。

### 1.4 将所有的 const 和 let 分组
```
// bad code
let i, len, dragonball,
      items = getItems(),
      goSportsTeam = true;

// bad code
let i;
const items = getItems();
let dragonball;
const goSportsTeam = true;
let len;

// good code
const goSportsTeam = true;
const items = getItems();
let dragonball;
let i;
let length
```
