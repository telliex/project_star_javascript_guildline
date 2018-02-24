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

1.5 构造器首字母大写，方法变量需要遵循小驼峰式命名规则
```
// bad code
function slidepage(){};
slidepage.prototype.resizepage = function(){};

// good code
function SlidePage(){};
SlidePage.prototype.resizePage = function(){};
```

1.6 下面类型的对象不建议用new构造：new Number, new String, new Boolean, new Object(用{}代替), new Array(用[]代替)

1.7 常量名全部大写，单词间用下划线分隔。如：“CSS_BTN_CLOSE”, "TXT_LOADING"
```
// bad code
const maxpeoplesize = 10;

// good code
const MAX_PEOPLE_SIZE = 10;
```

3 编码细节
3.1 赋值，定义，返回值，方法调用后强制需要加分号，除了for, function, if, switch, try, while
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
6.4 所有的循环体和判断体都需要用"{}"括起来。
```
// bad code
if (condition)
    statement;

// good code
if (condition) {
    statement;
}
```
6.5 for-in循环体中必须用 hasOwnProperty 方法检查成员是否为自身成员。避免来自原型链上的污染。


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

7.4 判断中禁止使用yoda表达式
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

7.5 判断使用严格类型判断 0，null，undefined ，固定字符 用===代替==，用!==代替!=。

8 字符串
```
// bad code
var str = "<div><span><a href="#">myhref</a></span></div>";

// good code
//使用反单引号
`<div>
    <span>
        <a href="#">myhref</a>
    </span>
</div>`
```

9 原型
9.1 禁止对顶级对象进行原型修改，必要时请以 addMethod 方法加入

```
// bad code
Function.prototype.cutHtml = function(){};

// good code
Function.prototype.addMethod=function(name,fn){
    this.prototype[name]=fn
};
let Methods=function(){};
Methods.addMethod('cutHtml',function(){
    //do something...
});

```

10 注解
10.1 文件开头必须要有文件说明注释，时间，作者
```
/**
 *@author designsor#http://gmail.com
 *@date 20150721
 *@fileoverview 本文件用于xxx，实现了xxx方法，注意事项xxx
 */
```
补充注解

11 特性
11.1 禁用 with, void, evil


12 面向对象
12.1 统一使用构造器+原型方法进行面向对象方法开发，不使用拷贝继承

13 格式化
13.1 统一使用 js-beautify 和统一配置文件进行格式化
13.2 使用 2 个空格缩进
13.3 语法与风格检查使用 jshint

14 模块化
14.1 一个模块只干一件事
14.1.1 Javascript代码应符合jshint检验标准我们正在编写属于自己特殊定制的jshint标准配置，所有通过提交的代码 （非三方包，自身业务逻辑）都需要通过jslint检查。

    * 在sublime下配置：[uipoet/sublime-jshint · GitHub](https://github.com/uipoet/sublime-jshint)
    * 在vim下配置：[Shutnik/jshint2.vim · GitHub](https://github.com/Shutnik/jshint2.vim)
    
14.1.2 Javascript代码 格式化 使用统一格式 js-beautify
所有代码提交之前需要进行格式化，统一使用js-beautify工具和我们统一的标准配置。

    * 在sublime下配置：[enginespot/js-beautify-sublime · GitHub](https://github.com/enginespot/js-beautify-sublime)
    * 在vim下配置：[maksimr/vim-jsbeautify · GitHub](https://github.com/maksimr/vim-jsbeautify)

14.1.3 jshint和js-beautify的配置

* [.jshintrc配置](https://gist.github.com/xiaojue/fbe80093dc8058431568)
* [.jsbeautifyrc配置](https://gist.github.com/xiaojue/4e41578aa90c8d907130)
* [.eslintrc配置](https://github.com/hax/dotfiles/blob/master/es2016.eslintrc)


## 参考
* [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
* [Airbnb JavaScript Style Guide](http://airbnb.io/javascript/)

