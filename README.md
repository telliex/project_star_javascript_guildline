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
3.1 赋值，定义，返回值，方法调用后强制需要加分号
3.2 定义变量时，不使用逗号
3.3 objectMap 最后一个属性不带逗号
```
// bad code
let arr = [],str = "",obj = {a:1,b:2,};

// good code
let arr = [];
let str = "";
let obj = {a:1,b:2};
```

4 函数

4.1 函数内部不允许嵌套函数
4.2 函数内部不允许使用arguments.callee和arguments.caller
4.3 函数参数不得超过5个 （多于5个使用objectType代替）
```
// bad code
function myTestFunc(a,b,c,d,e,f,g,h){};

// good code
function myTestFunc(params){
    let a = params.a;
    let b = params.b;
}
```
5 debug
5.1 允许使用try/catch
5.2 上线代码不允许使用debugger，console，alert等调试异常的关键字

6 循环
6.1 循环使用for，不在非必要条件下不使用while
6.2 循环一致使用递增
6.3 循环内不允许定义函数和变量

7 逻辑控制
7.1 控制条件内不要使用定义变量
7.2 分支超过5种的判断使用 switch case，switch case 需要带 default
7.3 判断条件过长，使用变量标识
```
// bad code
if( flag === 0 || $(".div").length > 0 || $("#id").hasClass("hide")){}

// good code
let isRead = (flag === 0);
let hasDiv = $(".div").length > 0;
let isDisplay = $("#id").hasClass("hide");
if(isRead || hasDiv || isDisplay){}
```





