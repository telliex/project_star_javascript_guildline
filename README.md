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
