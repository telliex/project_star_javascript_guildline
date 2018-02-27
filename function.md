### 7.1 使用简写
```
// bad
if (name !== '') {
  // ...stuff...
}

// good
if (name) {
  // ...stuff...
}

// bad
if (collection.length > 0) {
  // ...stuff...
}

// good
if (collection.length) {
  // ...stuff...
}
```

### 7.1 赋值，定义，返回值，方法调用后强制需要加分号，除了for, function, if, switch, try, while

### 7.3 定义变量时，不使用逗号

### 7.4 objectMap 最后一个属性不带逗号
```
// bad code
let arr = [],str = "",obj = {a:1,b:2,};

// good code
let arr = [];
let str = "";
let obj = {a:1,b:2};
```



### 7.5 循环使用for，不在非必要条件下不使用while
### 7.6 循环一致使用递增
### 7.7 循环内不允许定义函数和变量
### 7.8 所有的循环体和判断体都需要用"{}"括起来。
```
// bad code
if (condition)
    statement;

// good code
if (condition) {
    statement;
}
```
### 7.9 for-in循环体中必须用 hasOwnProperty 方法检查成员是否为自身成员。避免来自原型链上的污染。



### 7.10 控制条件内不要使用定义变量
### 7.11 分支超过5种的判断使用 switch case，switch case 需要带 default
### 7.12 判断条件过长，使用变量标识
```
// bad code
if( flag === 0 || $(".div").length > 0 || $("#id").hasClass("hide")){}

// good code
let isRead = (flag === 0);
let hasDiv = $(".div").length > 0;
let isDisplay = $("#id").hasClass("hide");
if(isRead || hasDiv || isDisplay){}
```

### 7.13 判断中禁止使用yoda表达式
```
// bad code
if (5 == n) {
    // do something...
}

// good code
if (n == 5) {
    // do something...

}
```

### 7.14 判断使用严格类型判断 0，null，undefined ，固定字符 用===代替==，用!==代替!=。

### 7.15 禁用 with, void, evil

### 7.16 使用 2 个空格缩进
```
// bad
function() {
∙∙∙∙const name;
}

// bad
function() {
∙const name;
}

// good
function() {
∙∙const name;
}
```


### 7.17 在花括号前放一个空格。
```
// bad
function test(){
  console.log('test');
}

// good
function test() {
  console.log('test');
}

// bad
dog.set('attr',{
  age: '1 year',
  breed: 'Bernese Mountain Dog',
});

// good
dog.set('attr', {
  age: '1 year',
  breed: 'Bernese Mountain Dog',
});
```
### 7,18 在控制语句（if、while 等）的小括号前放一个空格。在函数调用及声明中，不在函数的参数列表前加空格。
```
// bad
if(isJedi) {
  fight ();
}

// good
if (isJedi) {
  fight();
}

// bad
function fight () {
  console.log ('Swooosh!');
}

// good
function fight() {
  console.log('Swooosh!');
}

```
### 7.19 使用空格把运算符隔开。
```
// bad
const x=y+5;

// good
const x = y + 5;
```

### 7.20 在使用长方法链时进行缩进。使用前面的点 . 强调这是方法调用而不是新语句。
```
// bad
$('#items').find('.selected').highlight().end().find('.open').updateCount();

// bad
$('#items').
  find('.selected').
    highlight().
    end().
  find('.open').
    updateCount();

// good
$('#items')
  .find('.selected')
    .highlight()
    .end()
  .find('.open')
    .updateCount();

// bad
const leds = stage.selectAll('.led').data(data).enter().append('svg:svg').class('led', true)
    .attr('width', (radius + margin) * 2).append('svg:g')
    .attr('transform', 'translate(' + (radius + margin) + ',' + (radius + margin) + ')')
    .call(tron.led);

// good
const leds = stage.selectAll('.led')
    .data(data)
  .enter().append('svg:svg')
    .classed('led', true)
    .attr('width', (radius + margin) * 2)
  .append('svg:g')
    .attr('transform', 'translate(' + (radius + margin) + ',' + (radius + margin) + ')')
    .call(tron.led);
```


### 7.21 在块末和新语句前插入空行。
```
// bad
if (foo) {
  return bar;
}
return baz;

// good
if (foo) {
  return bar;
}

return baz;

// bad
const obj = {
  foo() {
  },
  bar() {
  },
};
return obj;

// good
const obj = {
  foo() {
  },

  bar() {
  },
};

return obj;
```
### 7.22 行首逗号：不需要。
```
// bad
const story = [
    once
  , upon
  , aTime
];

// good
const story = [
  once,
  upon,
  aTime,
];

// bad
const hero = {
    firstName: 'Ada'
  , lastName: 'Lovelace'
  , birthYear: 1815
  , superPower: 'computers'
};

// good
const hero = {
  firstName: 'Ada',
  lastName: 'Lovelace',
  birthYear: 1815,
  superPower: 'computers',
};
```

### 适当添加空行，增加代码的易读性

```
// bad code
  if (condition) {
    for (condition1; condition2; condition3) {
      var foo = 0;
      var bar = 1;
      // a comment
      if (condition) {
        alert(foo);
      } else {
        alert(bar);
      }
    }
  }

// good code
  if (condition) {

    for (condition1; condition2; condition3) {
      var foo = 0;
      var bar = 1;

      // a comment
      if (condition) {
        alert(foo);
      } else {
        alert(bar);
      }
    }
  }
```





