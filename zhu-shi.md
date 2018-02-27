# 注释原则
当代码不够清晰的时候使用注释，当代码很明了的时候不应当添加注释

### 8.1 尽量使用英文

### 8.2 文件开头必须要有文件说明注释，时间，作者
```
/**
 * ===========================================================
 *  文件标题
 * ===========================================================
 *
 *  从这里开始写这个文件的简要说明。
 *
 *  当需要进行更细致的解释说明、提供文档文本时，较长的说明文本就很
 *  有用了。这种长长的说明文本，可以包括示例 HTML、链接 等等其他你
 *  认为重要或者有用的东西。
 * 
 * ===========================================================
 *
 * @author (作者)
 * @create (创建时间)
 * 
 * @update (修改时间) (修改者)
 *   1. (修改内容)
 * @update (修改时间) (修改者)
 *   ...
 *
 * @todo: 这个“‘需做’陈述”描述了一个接下来要去做的小工作。这种文本，
 *       如果超长了的话，应该在80个半角字符（如英文）或40个全角字符
 *       （如中文）后便换行，并且保持对齐。
 */
```

### 8.3 函数或对象描述方法
* 总结（summary）: 简短的表述此函数或者对象实现的目的
* 描述（description）: 对于此函数或者类的简短的描述
* 返回（return）: 描述此函数返回什么（并不包括返回类型）

```
function(){
    // summary: Soon we will have enough treasure to rule all of New Jersey.
    // description: Or we could just get a new roomate.
    //  Look, you go find him.  He don't yell at you.
    //  All I ever try to do is make him smile and sing around
    //  him and dance around him and he just lays into me.
    //  He told me to get in the freezer 'cause there was a carnival in there.
    // returns:  Look, a Bananarama tape!
}
```

### 8.4 简单的类型的参数可以直接在函数参数定义中注释说明。 
```
function(/*String*/ foo, /*int*/ bar)...
```  

### 8.5 返回值
函数可以同时返回多个不同（类型）的值，所以应每个返回值之后加入返回类型的注释。注释在行内注释即可，如果所有的返回值为同一类型，则指明返回的类型；如为多个不同的返回值，则标注返回类型为"mixed"。
```
function() {
 if (arguments.length) {
  return "You passed argument(s)"; // String
 } else {
        return false; // Boolean
    }
}
```

### 8.6 单行注释
* 独占一行，用来解释下一行
* 注释之前有一行空行
* 缩进的层级与下一行代码保持一致
* // 后保留一个空格
* 尾部注释与代码之间至少有一个缩进
* 尾部注释太长的时候应该移到代码的上一行

```
  // a comment
  let foo1 = 0;

  let foo2 = 0;  // keep an indent
```  

### 8.7 给注释增加 FIXME 或 TODO 的前缀可以帮助其他开发者快速了解这是一个需要复查的问题，或是给需要实现的功能提供一个解决方式。这将有别于常见的注释，因为它们是可操作的。使用FIXME -- need to figure this out 或者 TODO -- need to implement。
```
// 使用  FIXME: 标注问题。
class Calculator {
  constructor() {
    // FIXME: shouldn't use a global here
    total = 0;
  }
}


// 使用 TODO: 标注问题的解决方式。
class Calculator {
  constructor() {
    // TODO: total should be configurable by an options param
    this.total = 0;
  }
}
```



