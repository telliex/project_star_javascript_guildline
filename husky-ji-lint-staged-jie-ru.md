# husky 及 lint-staged 接入指南

## Step1:npm 包安装
```
npm i -D eslint husky lint-staged
```

安装包说明：
* eslint: 进行 JavaScript 代码检查的基础包；
* husky：在 .git/hooks 中写入 pre-commit 等脚本激活钩子，在 Git 操作时触发；
* lint-staged：参考 Git 中 staged 暂存区概念，在每次提交时只检查本次提交的文件。

## Step2:必须在 package.json 同路径下新建 .eslintrc，继承基础规则包
```
## 此處以 airbnb guideline 為例
{
  "extends": "airbnb-base", 
  "globals":{
    // 在这里写系统特殊需要的全局变量，不需要则不写 globals
  },
  "rules": {
    // 在这里写覆盖规则，不需要则不写 rules
  }
}
```

## Step3:修改 package.json 配置，设置 precommit 和 lint-staged

```
{
  "scripts": {
    "precommit": "lint-staged"
  },
  "lint-staged": {
    "src/**/*.js": ["eslint --fix", "git add"]
  }
}
```

钩子触发流程说明
当开发者执行 git add 操作将代码提交到暂存区后，再执行 git commit 操作时：
1. 由于 husky 在 .git/hooks 中写入了 pre-commit 钩子，该钩子在 git commit 执行时被触发，执行 npm run precommit 脚本（即 lint-staged 命令）；
2. lint-staged 利用配置的文件过滤路径，对暂存区文件一个个进行匹配，匹配成功时，运行 eslint –fix 并自动将修改添加到暂存区：
3. 此时如果有报错，则流程终止，无法执行 commit 操作。


