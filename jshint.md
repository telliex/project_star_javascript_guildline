
编辑器环境： Sublime Text 3

### 安装 SublimeLinter
SublimeLinter 是 SublimeText 的插件，它只是一个进行代码检查的框架，可以包括其他代码检查插件。
1. 按下 Ctrl+Shift+p 进入 Command Palette
2. 输入install进入 Package Control: Install Package
3. 输入SublimeLinter。进行安装.

### 安装 SublimeLinter-jshint
由于 SublimeLinter 只是一个 linter 插件的框架，因此，还需要安装额外的 linter 插件。
1. 按下 Ctrl+Shift+p 进入 Command Palette
2. 输入install进入 Package Control: Install Package
3. 输入SublimeLinter-jshint。进行安装.

### 安装 nodeJS 和 jshint

#### 安装 Node.js
#### 通过 npm 安装 jshint
```
npm install -g jshint
```


### 设置.jshintrc
在项目根目录新建一个文件：.jshintrc 。 api參考地址：[传送门](http://jshint.com/docs/options/)。
```
{
  "immed": true, // 立即执行函数必须用括号包起来 `(function () { } ());` 
  "noempty": true, // 禁止出现空的代码块 `{ }`
  "quotmark": "single", // 引号的使用规则，必须都是单引号
  "bitwise": true, //不能使用位运算符&
  "curly": true, //不能省略循环和条件语句的大括号
  "forin":true, //for in需要hasOwnProperty检查
  "latedef":"nofunc", //先定义变量,函数声明除外
  "undef":true, //变量未定义
  "unused":"strict", //检查未使用的变量与函数参数，跳过函数
  "noarg":true, //禁止使用 arguments.caller 和 arguments.callee
  "maxparams": 4, //最多参数个数
  "browser":true, //允许与浏览器相关的关键字,如document、history、clearIntreval等
  "devel":true, //允许与开发相关的关键字,像alert,console等
  "indent": 2, //缩进2空格
  "maxerr":50, //超过50个错误,jslint停止工作
  "newcap":true, //允许构造器函数首字母非大写
  "nomen": true, //不允许在两边(最前或最后)悬挂下划线符号(_)
  "plusplus": false, //允许++和--
  "eqeqeq": true, //使用===做判断
  "maxlen": 120, //行最大长度
  "strict":true, //函数级别必须有"use strict"指令
  //"maxstatements": 5,//限制函数内声明语句的个数
  "node": true, //node环境
  "jquery":true //jquery环境
}
```

### SublimeLinter的运行模式
SublimeLinter的运行模式，总共有四种，分别如下：
* true - 在用户输入时在后台进行即时校验
* false - 只有在初始化的时候才进行校验
* "load-save" - 当文件加载和保存的时候进行校验
* "save-only" - 只有当文件被保存的时候进行校验 (推荐)

可在Tools->Sublime Linter->Lint Mode中进行设置
可以在每次保存时显示错误提示窗口。通过Tools->Sublime Linter->Show Errors On Save设置
错误标记样式(Mark Style)以及侧边栏主题(Gutter Theme)

![errors](/images/error01.png)
![errors](/images/error02.jpeg)

黄色代表警告，红色代表错误。