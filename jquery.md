### 10.1 使用 $ 作为存储 jQuery 对象的变量名前缀。
```
// bad code
const sidebar = $('.sidebar');

// good code
const $sidebar = $('.sidebar');
```

### 10.2 缓存 jQuery 查询。
```
// bad code
function setSidebar() {
  $('.sidebar').hide();

  // ...stuff...

  $('.sidebar').css({
    'background-color': 'pink'
  });
}

// good code
function setSidebar() {
  const $sidebar = $('.sidebar');
  $sidebar.hide();

  // ...stuff...

  $sidebar.css({
    'background-color': 'pink'
  });
}
```

### 10.3 对 DOM 查询使用层叠 $('.sidebar ul') 或 父元素 > 子元素 $('.sidebar > ul');对有作用域的 jQuery 对象查询使用 find。
```
// bad code
$('ul', '.sidebar').hide();

// bad
$('.sidebar').find('ul').hide();

// good
$('.sidebar ul').hide();

// good
$('.sidebar > ul').hide();

// good
$sidebar.find('ul').hide();
```