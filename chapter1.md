结构 | 规则
---- | ---
模块 | mixedCase
类 | MyClass
公有方法 | mixedCase
公有变量 | mixedCase
常量 | CSS_BTN_CLOSE
私有方法 | _mixedCase
私有变量 | _mixedCase
方法（method）参数 | mixedCase
函数 | mixedCase
对象 | mixedCase
实例 | mixedCase

### 1.1 避免单字母命名。命名应具备描述性。
```
// bad code
function q() {
  // ...stuff...
}

// good code
function query() {
  // ..stuff..
}
```
### 1.2 使用驼峰式命名对象、函数和实例。
```
// bad
const OBJEcttsssss = {};
const this_is_my_object = {};
function c() {}

// good
const thisIsMyObject = {};
function thisIsMyFunction() {}
```

### 1.3 使用帕斯卡式命名构造函数或类。
```
// bad code

function user(options) {
  this.name = options.name;
}

const bad = new user({
  name: 'nope',
});

// good code

class User {
  constructor(options) {
    this.name = options.name;
  }
}

const good = new User({
  name: 'yup',
});
```

### 1.4 私有变量函数前置使用 "_" 标示
```
// bad code
MyConstructor.prototype.private=function(){}

this.__firstName__ = 'Panda';

// good code
function _private(){};
MyConstructor.prototype._private=_private;

this._firstName = 'Panda';
```

### 1.5 如果你的文件只输出一个类，那你的文件名必须和类名完全保持一致。
```
// file contents
class CheckBox {
  // ...
}
export default CheckBox;

// in some other file
// bad code
import CheckBox from './checkBox';

// bad code
import CheckBox from './check_box';

// good code
import CheckBox from './CheckBox';
```

### 1.6 当你导出默认的函数时使用驼峰式命名。你的文件名必须和函数名完全保持一致。
```
function makeStyleGuide() {
}

export default makeStyleGuide;
```


### 1.7 构造器首字母大写，方法变量需要遵循小驼峰式命名规则
```
// bad code
function slidepage(){};
slidepage.prototype.resizepage = function(){};

// good code
function SlidePage(){};
SlidePage.prototype.resizePage = function(){};
```

### 1.8 常量名全部大写，单词间用下划线分隔。如：“CSS_BTN_CLOSE”, "TXT_LOADING"
```
// bad code
const maxpeoplesize = 10;

// good code
const MAX_PEOPLE_SIZE = 10;
```

### 1.10 特殊命名规范

1. 前面加 "is" 的变量名 应该 为布尔值，同理可以为 "has", "can" 或者 "should"。
2. 术语 "compute" 作为变量名应为已经计算完成的变量。
3. 术语 "find" 作为变量名应为已经查找完成的变量。
4. 术语 "initialize" 或者 "init" 作为变量名应为已经实例化（初始化）完成的类或者其他类型的变量。
5. 带有 "num" 或者 "count" 开头的变量名约定为数字（对象）。
6. 重复变量建议使用 "i", "j", "k" （依次类推）等名称的变量。
7. 补充用语必须使用补充词，例如： get/set, add/remove, create/destroy, start/stop, insert/delete, begin/end, etc.



