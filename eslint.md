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

## vscode setting
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




## 参考
[ESLint 配置文件 .eslintrc 参数说明](https://gist.github.com/rswanderer/29dc65efc421b3b5b0442f1bd3dcd046)