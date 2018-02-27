
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
  "curly": true, // 所有的代码块必须使用大括号
  "eqeqeq": true, // 表示判断相等时，必须使用 ===
  "immed": true, // 立即执行函数必须用括号包起来 `(function () { } ());`
  "noarg": true, // 止使用 `arguments.caller` 和 `arguments.callee`
  "noempty": true, // 禁止出现空的代码块 `{ }`
  "quotmark": "single", // 引号的使用规则，必须都是单引号
  "undef": true,  // 所有的局部变量都必须先声明再使用
  "unused": true,  // 禁止变量已经声明，但却不使用
  "node": true // 表明你的项目是NodeJS项目，require等node特有的全局函数将通过检查
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