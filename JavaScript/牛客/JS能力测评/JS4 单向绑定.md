# JS4 单向绑定

#### 描述

请补全JavaScript代码，要求每当id为"input"的输入框值发生改变时触发id为"span"的标签内容同步改变。

#### 注意

1. 必须使用DOM0级标准事件（onchange）



### 题解

首先利用 `document.querySelector(tag)` 获取DOM元素，接着**用onchange事件监听**input框发生改变事件，同步修改span中的值。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	<input id="input" type="text" />
        <span id="span"></span>

        <script type="text/javascript">
            // 补全代码
            var input = document.querySelector('input');
            var span = document.querySelector('span');
            input.onchange = function() {
                span.innerHTML = input.value;
            }
        </script>
    </body>
</html>
```

