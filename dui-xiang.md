### 使用字面值创建对象，下面类型的对象不建议用new构造：new Number, new String, new Boolean, new Object(用{}代替), new Array(用[]代替)

```
// bad code
const item = new Object();

// good code
const item = {};
```


### 不要使用new命令，改用Object.create()命令。


### 如果你的代码在浏览器环境下执行，别使用 保留字 作为键值。这样的话在 IE8 不会运行。 但在 ES6 模块和服务器端中使用没有问题。
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

### 使用对象方法的简写
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

