### 字符串使用单引号 '' 。
### 字符串超过 80 个字节应该使用字符串连接号换行。
### 过度使用字串连接符号可能会对性能造成影响。
```
// bad code
const errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';

// bad code
const errorMessage = 'This is a super long error that was thrown because \
of Batman. When you stop to think about how Batman had anything to do \
with this, you would get nowhere \
fast.';

// good code
const errorMessage = 'This is a super long error that was thrown because ' +
  'of Batman. When you stop to think about how Batman had anything to do ' +
  'with this, you would get nowhere fast.';
```

### 程序化生成字符串时，使用模板字符串代替字符串连接。
```
// bad code
function sayHi(name) {
    return 'How are you, ' + name + '?';
}

// good code
function sayHi(name) {
    return `How are you, ${name}?`;
}
```
