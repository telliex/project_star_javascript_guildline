### 总是使用模组 (import/export) 而不是其他非标准模块系统。
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
### 不要使用通配符 import
```
// bad code
import * as AirbnbStyleGuide from './AirbnbStyleGuide';

// good code
import AirbnbStyleGuide from './AirbnbStyleGuide';
```
### 让 import 和 export 各司其职让事情能保持一致，不要从 import 中直接 export。
```
// bad code
// filename es6.js
export { es6 as default } from './airbnbStyleGuide';

// good code
// filename es6.js
import { es6 } from './AirbnbStyleGuide';
export default es6;
```