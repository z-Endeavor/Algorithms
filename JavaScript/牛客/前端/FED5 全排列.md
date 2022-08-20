# FED5 全排列

#### 描述

请补全JavaScript代码，要求以数组的形式返回字符串参数的所有排列组合。

注意：

1. 字符串参数中的字符无重复且仅包含小写字母
2. 返回的排列组合数组不区分顺序

#### 示例1

```
输入：_permute('abc')
输出：['abc','acb','bac','bca','cab','cba']
```



### 题解

根据题目要求，通过快速排序实现数组参数中数字从小到大排序。快速排序的基本思想是通过分治来使一部分均比另一部分小（大）再使两部分重复该步骤而实现有序的排列。核心步骤有：

1. 选择一个基准值（pivot）
2. 以基准值将数组分割为两部分
3. 递归分割之后的数组直到数组为空或只有一个元素为止

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

