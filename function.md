### 使用简写
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

### 3.1 赋值，定义，返回值，方法调用后强制需要加分号，除了for, function, if, switch, try, while

### 定义变量时，不使用逗号

### 3.3 objectMap 最后一个属性不带逗号
```
// bad code
let arr = [],str = "",obj = {a:1,b:2,};

// good code
let arr = [];
let str = "";
let obj = {a:1,b:2};
```



### 6.1 循环使用for，不在非必要条件下不使用while
### 6.2 循环一致使用递增
### 6.3 循环内不允许定义函数和变量
### 6.4 所有的循环体和判断体都需要用"{}"括起来。
```
// bad code
if (condition)
    statement;

// good code
if (condition) {
    statement;
}
```
### 6.5 for-in循环体中必须用 hasOwnProperty 方法检查成员是否为自身成员。避免来自原型链上的污染。



### 7.1 控制条件内不要使用定义变量
### 7.2 分支超过5种的判断使用 switch case，switch case 需要带 default
### 7.3 判断条件过长，使用变量标识
```
// bad code
if( flag === 0 || $(".div").length > 0 || $("#id").hasClass("hide")){}

// good code
let isRead = (flag === 0);
let hasDiv = $(".div").length > 0;
let isDisplay = $("#id").hasClass("hide");
if(isRead || hasDiv || isDisplay){}
```

### 7.4 判断中禁止使用yoda表达式
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

### 7.5 判断使用严格类型判断 0，null，undefined ，固定字符 用===代替==，用!==代替!=。



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



