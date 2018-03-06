# Javascript 编程风格

所谓"编程风格"（programming style），指的是编写代码的样式规则。不同的程序员，往往有不同的编程风格。

编译器的规范叫做"语法规则"（grammar），这是程序员必须遵守的；而编译器忽略的部分，就叫"编程风格"（programming style），这是程序员可以自由选择的。好的编程风格有助于写出质量更高、错误更少、更易于维护的程序。

## Javascript 编程风格目的

整个 guildline 著重点为：  
1. 代码清晰易读、减少出错。  
2. 可读性，团队可接受。  
3. 质量更高、错误更少、更易于维护的程序。

## 编程环境建立

### 编辑器配置

将你的编辑器按照下面的配置进行设置，以避免常见的代码不一致和差异：

* 用软缩进代替制表符
* 设置文件编码为 UTF-8
* 换行符使用 lf（Unix 风格）
* 在文件结尾添加一个空白行
* 保存文件时，删除尾部的空白符

### editorconfig.org

```
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

### 自动化测试

* 语法与风格检查使用 jshint



