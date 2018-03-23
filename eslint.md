# ESlint 自動檢查程式碼的工具

avaScript 是一个动态的弱类型语言，在开发中比较容易出错。因为没有编译程序，为了寻找 JavaScript 代码错误通常需要在执行过程中不断调试。像 ESLint 这样的可以让程序员在编码的过程中发现问题而不是在执行的过程中。

### 安装 ESLint

#### Step1 安装 ESlint
```
npm i -g eslint
```

#### Step2 建立设置文件,产出 .eslintrc.js
```
eslint --init

## 下面为问答设定
How would you like to configure ESLint? Use a popular style guide
Which style guide do you want to follow? Airbnb
Do you use React? No
What format do you want your config file to be in? JavaScript
```

## 配置文件相关
ESLint 配置文件优先级：
.eslintrc.js (输出一个配置对象)
.eslintrc.yaml
.eslintrc.yml
.eslintrc.json（ ESLint 的 JSON 文件允许 JavaScript 风格的注释）
.eslintrc（可以是 JSON 也可以是 YAML
package.json（在 package.json 里创建一个 eslintConfig 属性，在那里定义你的配置）

可配置 .eslintignore 文件告诉 ESLint 去忽略特定的文件和目录。

```
## 配置文件內容
module.exports = {
    "extends": "airbnb-base"
};
```

## vscode 
### setting

```
// 將您的設定放入此檔案中以覆寫預設值
{
  "editor.snippetSuggestions": "top",
  "editor.tabSize": 2,
  "eslint.autoFixOnSave": true,
  "editor.renderControlCharacters": true,
  "files.eol": "\n",
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    { "language": "html", "autoFix": true }
  ],
  "git.ignoreLimitWarning": true
}
```

### 文件内块注释来临时禁止规则出现警告
```
## 文件中使用
/* eslint-disable */

alert('foo');

/* eslint-enable */
```

```
## 文件顶部使用
/* eslint-disable */

alert('foo');
```

### 规则配置
>rules: {
>    "规则名": [规则值, 规则配置]
>}
>
>"off"或者0    //关闭规则关闭
>"warn"或者1    //在打开的规则作为警告（不影响退出代码）
>"error"或者2    //把规则作为一个错误（退出代码触发时为1）

```
module.exports = {
  root: true,
  parser: 'babel-eslint',
  parserOptions: {
    //设置"script"（默认）或"module"如果你的代码是在ECMAScript中的模块。
    sourceType: 'module'
  },
  env: {
    browser: true,
  },
  // https://github.com/feross/standard/blob/master/RULES.md#javascript-standard-style
  extends: 'standard',
  // required to lint *.vue files
  plugins: [
    'html'
  ],
  // add your custom rules here
  'rules': {
    // allow paren-less arrow functions
    'arrow-parens': 0,
    // allow async-await
    'generator-star-spacing': 0,
    // allow debugger during development
    'no-debugger': process.env.NODE_ENV === 'production' ? 2 : 0,
    "no-unused-vars": [2, { 
      // 允许声明未使用变量
      "vars": "local",
      // 参数不检查
      "args": "none" 
    }],
    // 关闭语句强制分号结尾
    "semi": [0],
    //空行最多不能超过100行
    "no-multiple-empty-lines": [0, {"max": 100}],
    //关闭禁止混用tab和空格
    "no-mixed-spaces-and-tabs": [0],
  }
}
```



## 参考
[ESLint 配置文件 .eslintrc 参数说明](https://gist.github.com/rswanderer/29dc65efc421b3b5b0442f1bd3dcd046)