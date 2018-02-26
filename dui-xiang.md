### 3.1 使用字面值创建对象，下面类型的对象不建议用new构造：new Number, new String, new Boolean, new Object(用{}代替), new Array(用[]代替)

```
// bad code
const item = new Object();
const items = new Array();

// good code
const item = {};
const items = [];
```

### 3.2 不要使用new命令，改用Object.create()命令。


### 3.3 如果你的代码在浏览器环境下执行，别使用 保留字 作为键值。这样的话在 IE8 不会运行。 但在 ES6 模块和服务器端中使用没有问题。
```
// bad code
const superman = {
  default: { clark: 'kent' },
  private: true,
};

// good code
const superman = {
  defaults: { clark: 'kent' },
  hidden: true,
};
```

### 3.4 使用对象方法的简写
```
// bad code
const atom = {
  value: 1,
  addValue: function (value) {
    return atom.value + value;
  },
};

// good code
const atom = {
  value: 1,
  addValue(value) {
    return atom.value + value;
  },
};
```

### 使用对象属性值的简写
```
const lukeSkywalker = 'Luke Skywalker';

// bad code
const obj = {
    lukeSkywalker: lukeSkywalker,
};

// good code
const obj = {
    lukeSkywalker,
};
```
### 向数组添加元素时使用 Arrary#push 替代直接赋值。
```

// bad code
someStack[someStack.length] = 'abracadabra';

// good code
someStack.push('abracadabra');
```
### 使用拓展运算符 ... 复制数组。
```
// bad code
const len = items.length;
const itemsCopy = [];
let i;

for (i = 0; i < len; i++) {
  itemsCopy[i] = items[i];
}

// good code
const itemsCopy = [...items];

```

### 解構：使用解构存取和使用多属性对象。
```
// bad code
function getFullName(user) {
    const firstName = user.firstName;
    const lastName = user.lastName;

    return `${firstName} ${lastName}`;
}

// good code
function getFullName(obj) {
    const { firstName, lastName } = obj;
    return `${firstName} ${lastName}`;
}

// best code
function getFullName({ firstName, lastName }) {
    return `${firstName} ${lastName}`;
}

```

### 解構：对数组使用解构赋值。
```
const arr = [1, 2, 3, 4];

// bad code
const first = arr[0];
const second = arr[1];

// good code
const [first, second] = arr;
```

### 解構：需要回传多个值时，使用对象解构，而不是数组解构。
```
// bad code
function processInput(input) {
    // then a miracle occurs
    return [left, right, top, bottom];
}

// 调用时需要考虑回调数据的顺序。
const [left, __, top] = processInput(input);

// good code
function processInput(input) {
    // then a miracle occurs
    return { left, right, top, bottom };
}

// 调用时只选择需要的数据
const { left, right } = processInput(input);

```




