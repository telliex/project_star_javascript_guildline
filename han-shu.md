### 4.1 函数内部不允许嵌套函数
### 4.2 函数内部不允许使用arguments.callee和arguments.caller
### 4.3 函数参数不得超过5个 （多于5个使用objectType代替）
```
// bad code
function myTestFunc(a,b,c,d,e,f,g,h){};

// good code
function myTestFunc(params){
    let a = params.a;
    let b = params.b;
}
```


### 使用函数声明代替函数表达式。

### 不要在一个非函数代码块（if、while 等）中声明一个函数，把那个函数赋给一个变量。浏览器允许你这么做，但它们的解析表现不一致。

### 直接给函数的参数指定默认值，不要使用一个变化的函数参数。
```
// really bad code
function handleThings(opts) {
  // 不！我们不应该改变函数参数。
  // 更加糟糕: 如果参数 opts 是 false 的话，它就会被设定为一个对象。
  // 但这样的写法会造成一些 Bugs。
  //（译注：例如当 opts 被赋值为空字符串，opts 仍然会被下一行代码设定为一个空对象。）
  opts = opts || {};
  // ...
}

// still bad code
function handleThings(opts) {
  if (opts === void 0) {
    opts = {};
  }
  // ...
}

// good code
function handleThings(opts = {}) {
  // ...
}
```

### 永远不要在一个非函数代码块（if、while 等）中声明一个函数，把那个函数赋给一个变量。浏览器允许你这么做，但它们的解析表现不一致。

```
// bad code
if (currentUser) {
  function test() {
    console.log('Nope.');
  }
}

// good code
let test;
if (currentUser) {
  test = () => {
    console.log('Yup.');
  };
}
```

### 不要使用 arguments。可以选择 rest 语法 ... 替代
```
// bad code
function concatenateAll() {
    const args = Array.prototype.slice.call(arguments);
    return args.join('');
}

// good code
function concatenateAll(...args) {
    return args.join('');
}
```

### 使用函数声明代替函数表达式。
```
// bad code
const foo = function () {
};

// good code
function foo() {
}
```

### 当你必须使用函数表达式（或传递一个匿名函数）时，使用箭头函数符号。
```
// bad code
[1, 2, 3].map(function (x) {
    return x * x;
});

// good code
[1, 2, 3].map((x) => {
    return x * x;
});
```
### 总是使用 class。避免直接操作 prototype 。因为 class 语法更为简洁更易读。
```
// bad code
function Queue(contents = []) {
    this._queue = [...contents];
}
Queue.prototype.pop = function() {
    const value = this._queue[0];
    this._queue.splice(0, 1);
    return value;
}

// good code
class Queue {
    constructor(contents = []) {
      this._queue = [...contents];
    }
    pop() {
      const value = this._queue[0];
      this._queue.splice(0, 1);
      return value;
    }
}
```

### 使用 extends 继承，extends 不会破坏 instanceof。
```
// bad code
const inherits = require('inherits');
function PeekableQueue(contents) {
    Queue.apply(this, contents);
}
inherits(PeekableQueue, Queue);
PeekableQueue.prototype.peek = function() {
    return this._queue[0];
}

// good code
class PeekableQueue extends Queue {
    peek() {
      return this._queue[0];
    }
}
```

