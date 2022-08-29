# FED7 Array.map

#### 描述

请补全JavaScript代码，要求实现Array.map函数的功能且该新函数命名为"_map"。

#### 示例1

```
输入：[1,2]._map(i => i * 2)
输出：[2,4]
```



### 题解

本题考察 `Array.map()`。

根据题目要求，实现一个仿Array.map功能的"Array._map"函数，该函数创建一个新数组，该新数组的结果是数组中的每个元素都调用一次函数参数后的返回值，核心步骤有：

1. 创建一个空数组用于承载新的内容
2. 循环遍历数组中的每个值，分别调用函数参数，将返回值添加进空数组中
3. 返回新的数组

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>

        <script type="text/javascript">
            // 补全代码
            Array.prototype._map = function(f) {
                let res = [];
                this.forEach(item => {
                    res.push(f(item));
                })
                return res;
            }
        </script>
    </body>
</html>
```

