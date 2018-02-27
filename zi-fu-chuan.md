### 4.1 字符串使用单引号 '' 

### 4.2 字符串超过 80 个字节应该使用字符串连接号换行

### 4.3 过度使用字串连接符号可能会对性能造成影响
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

### 4.4 程序化生成字符串时，使用模板字符串代替字符串连接。
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

### 4.5 HTML 语法字串时，使用反单引号
```
// bad code
var str = "<div><span><a href="#">myhref</a></span></div>";

// good code
//使用反单引号
`<div>
    <span>
        <a href="#">myhref</a>
    </span>
</div>`
```

