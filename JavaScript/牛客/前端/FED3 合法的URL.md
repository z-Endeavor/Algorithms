# FED3 合法的URL

#### 描述

请补全JavaScript代码，要求以Boolean的形式返回字符串参数是否为合法的URL格式。

注意：

1. 协议仅为HTTP（S）



### 题解



```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _quickSort = array => {
                // 补全代码
                // 定义返回条件 如果数组的长度小于1 那么就返回就行了
                if (array.length <= 1) return array;
                // 先将找到数组的中间位置的下标
                var pivotIndex = Math.floor(array.length / 2);
                // 在元素数组中删除这个元素。 并保存这个数
                var pivot = array.splice(pivotIndex, 1)[0];
                var left = [];
                var right = [];
                // 比数组中间位置元素小的放在left,数组中间位置元素大的放在right
                for (var i=0; i<array.length; i++) {
                    if (array[i] < pivot) {
                        left.push(array[i]);
                    } else {
                        right.push(array[i]);
                    }
                }
                return _quickSort(left).concat([pivot], _quickSort(right));
            }
        </script>
    </body>
</html>
```

