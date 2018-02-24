# javascript guildline 原则

本规范适用于桌机与手持装置开发，配合 jshint 进行检查及格式化



整个 guildline 著重点为：
1.可读性
2.团队可接受能力


1 变量与宣告：
1.1 声明以 `let`,`const` 替代 `var`
```
// bad code
MyGlobalVariable

// good code
let myGlobalVariable;
```  

1.2 变量在函数内部或循环控制条件之前提前声明
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

1.3 私有变量函数前置使用 "_" 标示
```
// bad code
MyConstructor.prototype.private=function(){}

// good code
function _private(){};

MyConstructor.prototype._private=_private;
```

1.4 变量命名规则
    * 布尔值开头带 is,has,can
```
// bad code
let readYet = false;

// good code
let isRead = false;
```

1.5 构造器首字母大写，方法变量需要遵循驼峰命名规则
```
// bad code
function slidepage(){};
slidepage.prototype.resizepage = function(){};

// good code
function SlidePage(){};
SlidePage.prototype.resizePage = function(){};
```

2 常量
2.1 常量需要大写
2.2 常量需要定义在文件头部，并使用 "_" 分割
```
// bad code
const maxpeoplesize = 10;

// good code
const MAX_PEOPLE_SIZE = 10;
```

3 编码细节




