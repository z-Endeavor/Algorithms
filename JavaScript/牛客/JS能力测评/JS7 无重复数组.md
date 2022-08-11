# JS7 无重复数组

#### 描述

请补全JavaScript代码，实现一个函数，要求如下：

1. 根据输入的数字范围[start,end]和随机数个数"n"生成随机数
2. 生成的随机数存储到数组中，返回该数组
3.  返回的数组不能有相同元素

#### 注意

1. 不需要考虑"n"大于数字范围的情况

#### 示例

```
输入：getUniqueNums(2,10,4)
输出：[4,6,2,8]
```



### 题解

注意必须生成 n 个元素的数组，而不是进行 n 次随机数生成。

#### 1、数组判断去重

利用 `Math.random()` 生成随机数。

` Array.includes()` 判断数字不存在后，存入数组。

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
    </head>
    <body>

        <script>
            const _getUniqueNums = (start,end,n) => {
                // 补全代码
                var res = [];
                while(res.length < n) {
                    let num = Math.floor(Math.random() * (end-start+1) + start);
                    if (!res.includes(num)) {
                        res.push(num);
                    }
                }
                return res;
            }
        </script>
    </body>
</html>
```

#### 2、利用 Set 去重

利用 `Set` 数据结构自动实现去重功能。

利用 `...` 扩展操作符将集合转为数组返回。

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
    </head>
    <body>

        <script>
            const _getUniqueNums = (start,end,n) => {
                // 补全代码
                var res = new Set();
                while(res.length < n) {
                    res.add(Math.floor(Math.random() * (end-start+1) + start));
                }
                return [...res];
            }
        </script>
    </body>
</html>
```

