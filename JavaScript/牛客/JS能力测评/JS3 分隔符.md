# JS3 分隔符

#### 描述

请补全JavaScript代码，要求返回参数数字的千分位分隔符字符串。

#### 示例

```
输入：_comma(12300)
输出：'12,300'
```



### 题解

利用**递归**的思想：

- 若数字小于1000，直接返回字符串。
- 若数字大于1000，将数字除以1000，**余数作为后3位数，商进行递归**，用 `,` 拼接。

注意题目要求返回字符串。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            function _comma(number) {
                // 补全代码
                if (number < 1000) {
                    return number.toString();
                } else {
                    return _comma(parseInt(number / 1000)) + ',' + _comma(number % 1000);
                }
            }
        </script>
    </body>
</html>
```

