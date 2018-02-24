# javascript guildline 原则

本规范适用于桌机与手持装置开发，配合 jshint 进行检查及格式化



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
参照文档并将这些配置信息添加到项目的.editorconfig文件中。更多信息请参考 [EditorConfig](http://editorconfig.org/) 。


此为 javascript guideline，更多如 HTML、CSS guildline 可参考[Web前端代码风格指南](https://dondevi.github.io/web-frontend-guide/style-guide/codestyle.html)

