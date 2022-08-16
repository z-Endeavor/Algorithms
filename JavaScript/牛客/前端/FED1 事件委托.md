# FED1 事件委托


#### 描述

请补全JavaScript代码，要求如下：

1. 给"ul"标签添加点击事件
2. 当点击某"li"标签时，该标签内容拼接"."符号。如：某"li"标签被点击时，该标签内容为".."

注意：

1. 必须使用DOM0级标准事件（onclick）



### 题解

题目要求使用事件代理，也即是不要在自身绑定`onclick`,我们可以选择它的父元素`ul`。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	<ul>
            <li>.</li>
            <li>.</li>
            <li>.</li>
        </ul>

        <script type="text/javascript">
            // 补全代码
            var ul = document.querySelector('ul');
            ul.onclick = e => {
                e.target.innerText += '.';
            }
        </script>
    </body>
</html>
```

