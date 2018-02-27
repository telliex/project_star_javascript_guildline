# Javascript 编程风格
所谓"编程风格"（programming style），指的是编写代码的样式规则。不同的程序员，往往有不同的编程风格。

有人说，编译器的规范叫做"语法规则"（grammar），这是程序员必须遵守的；而编译器忽略的部分，就叫"编程风格"（programming style），这是程序员可以自由选择的。好的编程风格有助于写出质量更高、错误更少、更易于维护的程序。

## Javascript 编程风格目的

整个 guildline 著重点为：
1. 代码清晰易读、减少出错。
2. 可读性，团队可接受。
3. 质量更高、错误更少、更易于维护的程序。

### 使用2个空格缩进


### 使用双引号
```
  var hello = "Hello World!";
```

### 适当添加空行，增加代码的易读性

```
// bad code
  if (condition) {
    for (condition1; condition2; condition3) {
      var foo = 0;
      var bar = 1;
      // a comment
      if (condition) {
        alert(foo);
      } else {
        alert(bar);
      }
    }
  }

// good code
  if (condition) {

    for (condition1; condition2; condition3) {
      var foo = 0;
      var bar = 1;

      // a comment
      if (condition) {
        alert(foo);
      } else {
        alert(bar);
      }
    }
  }
```

### 编辑器配置
将你的编辑器按照下面的配置进行设置，以避免常见的代码不一致和差异：
* 用软缩进代替制表符
* 设置文件编码为 UTF-8
* 换行符使用 lf（Unix 风格）
* 在文件结尾添加一个空白行
* 保存文件时，删除尾部的空白符

```
# editorconfig.org

  root = true

  [*]
  charset = utf-8
  indent_size = 2
  end_of_line = lf
  indent_style = space
  insert_final_newline = true
  trim_trailing_whitespace = true
```
参照文档并将这些配置信息添加到项目的 `.editorconfig` 文件中。更多信息请参考 [EditorConfig](http://editorconfig.org/) 。


此为 javascript guideline，更多如 HTML、CSS guildline 可参考[Web前端代码风格指南](https://dondevi.github.io/web-frontend-guide/style-guide/codestyle.html)



12 面向对象
12.1 统一使用构造器+原型方法进行面向对象方法开发，不使用拷贝继承

13 格式化
13.1 统一使用 js-beautify 和统一配置文件进行格式化
13.3 语法与风格检查使用 jshint

