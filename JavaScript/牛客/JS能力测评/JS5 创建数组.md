# JS5 创建数组

#### 描述

请补全JavaScript代码，要求返回一个长度为参数值并且每一项值都为参数值的数组。

#### 注意

1. 请勿直接使用for/while



### 题解

#### 1、Array.fill

`Array(number)` 在构造实例时带入参数，生产参数长度的空数组。

`Array.fill(number)` 直接**将数组的每一项都改为参数值**。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _createArray = (number) => {
                // 补全代码
                return Array(number).fill(number);
            }
        </script>
    </body>
</html>
```

#### 2、Array.from

利用`Array.from` 对一个类似数组或可迭代对象创建一个新的、浅拷贝的数组实例。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _createArray = (number) => {
                // 补全代码
                return Array.from(Array(number), () => number);
            }
        </script>
    </body>
</html>
```

