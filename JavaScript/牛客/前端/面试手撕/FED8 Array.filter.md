# FED8 Array.filter

#### 描述

请补全JavaScript代码，要求实现Array.filter函数的功能且该新函数命名为"_filter"。

#### 示例1

```
输入：[1,2]._filter(i => i>1)
输出：[2]
```



### 题解

本题考察 `Array.filter()`。

根据题目要求，实现一个仿Array.filter功能的"Array._filter"函数，该函数创建一个新数组，该数组包含通过函数参数条件的所有元素，核心步骤有：

1. 创建一个空数组用于承载新的内容
2. 循环遍历数组中的每个值，分别调用函数参数，将满足判断条件的元素添加进空数组中
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
            Array.prototype._filter = function(f) {
                let res = [];
                this.forEach( item => {
                    if (f(item)) res.push(item);
                })
                return res;
            }
        </script>
    </body>
</html>
```

