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