### 10.1 尽量使用英文

### 10.2 文件开头必须要有文件说明注释，时间，作者
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
### 10.3 函数或对象描述方法
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
### 10.4 简单的类型的参数可以直接在函数参数定义中注释说明。 
```
function(/*String*/ foo, /*int*/ bar)...
```  

### 10.5 返回值
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
