# FED2 数组去重


#### 描述

请补全JavaScript代码，要求去除数组参数中的重复数字项并返回该数组。

注意：

1. 数组元素仅包含数字



### 题解

题目要求使用事件代理，也即是不要在自身绑定`onclick`,我们可以选择它的父元素`ul`。

#### 1、使用Set去重

直接使用 ES6 中的 `Set` 方法进行去重。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _deleteRepeat = array => {
                // 补全代码
                return [...new Set(array)];
                // return Array.from(new Set(array));
            }
        </script>
    </body>
</html>
```

#### 2、使用新数组对不重复的元素保存

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _deleteRepeat = array => {
                // 补全代码
                var newArr = [];
                array.forEach(item => {
                    if (newArr.indexof(item) === -1) {
                        newArr.push(item);
                    }
                })
                return newArr;
            }
        </script>
    </body>
</html>
```

