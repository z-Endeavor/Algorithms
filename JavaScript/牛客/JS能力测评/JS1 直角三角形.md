# JS1 直角三角形


### 描述

请补全JavaScript代码，要求在页面上渲染出一个直角三角形，三角形换行要求使用"br"实现。三角形如下：

```
*
**
***
```



### 题解

获取到元素后，直接用 **`innerHTML `** 结合`<br>`画三角形即可。

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
    </head>
    <body>
        <div class='triangle'></div>

        <script>
            var triangle = document.querySelector('.triangle');
            // 补全代码
            triangle.innerHTML = '*<br>**<br>***'
        </script>
    </body>
</html>
```

