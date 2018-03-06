### 6.1 总是使用模组 (import/export) 而不是其他非标准模块系统
```
// bad code
const AirbnbStyleGuide = require('./AirbnbStyleGuide');
module.exports = AirbnbStyleGuide.es6;

// good code
import AirbnbStyleGuide from './AirbnbStyleGuide';
export default AirbnbStyleGuide.es6;

// best code
import { es6 } from './AirbnbStyleGuide';
export default es6;
```

### 6.2 不要使用通配符 import
```
// bad code
import * as AirbnbStyleGuide from './AirbnbStyleGuide';

// good code
import AirbnbStyleGuide from './AirbnbStyleGuide';
```

### 6.3 让 import 和 export 各司其职让事情能保持一致，不要从 import 中直接 export
```
// bad code
// filename es6.js
export { es6 as default } from './airbnbStyleGuide';

// good code
// filename es6.js
import { es6 } from './AirbnbStyleGuide';
export default es6;
```

### 6.4 一个模块只干一件事

#### 6.4.1 Javascript代码应符合jshint检验标准我们正在编写属于自己特殊定制的jshint标准配置，所有通过提交的代码 （非三方包，自身业务逻辑）都需要通过jslint检查

    * 在sublime下配置：[uipoet/sublime-jshint · GitHub](https://github.com/uipoet/sublime-jshint)
    * 在vim下配置：[Shutnik/jshint2.vim · GitHub](https://github.com/Shutnik/jshint2.vim)
    
#### 6.4.2 Javascript代码 格式化 使用统一格式 js-beautify
所有代码提交之前需要进行格式化，统一使用js-beautify工具和我们统一的标准配置。

    * 在sublime下配置：[enginespot/js-beautify-sublime · GitHub](https://github.com/enginespot/js-beautify-sublime)
    * 在vim下配置：[maksimr/vim-jsbeautify · GitHub](https://github.com/maksimr/vim-jsbeautify)

#### 6.4.3 jshint和js-beautify的配置

* [.jshintrc配置](https://gist.github.com/xiaojue/fbe80093dc8058431568)
* [.jsbeautifyrc配置](https://gist.github.com/xiaojue/4e41578aa90c8d907130)
* [.eslintrc配置](https://github.com/hax/dotfiles/blob/master/es2016.eslintrc)



