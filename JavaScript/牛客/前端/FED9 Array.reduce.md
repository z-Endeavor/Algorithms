# FED9 Array.reduce

#### 描述

请补全JavaScript代码，要求实现Array.reduce函数的功能且该新函数命名为"_reduce"。

#### 示例1

```
输入：[1,2,3]._reduce((left, right) => left + right)
输出：6
```



### 题解

根据题目要求，实现一个仿Array.reduce功能的"Array._reduce"函数。

**`reduce()`** 方法对数组中的每个元素按序执行一个由您提供的 **reducer** 函数，每一次运行 **reducer** 会将先前元素的计算结果作为参数传入，最后将其结果汇总为单个返回值。

一个 “reduce” 函数，包含四个参数：

- `previousValue`：上一次调用 `callbackFn` 时的返回值。在第一次调用时，若指定了初始值 `initialValue`，其值则为 `initialValue`，否则为数组索引为 0 的元素 `array[0]`。
- `currentValue`：数组中正在处理的元素。在第一次调用时，若指定了初始值 `initialValue`，其值则为数组索引为 0 的元素 `array[0]`，否则为 `array[1]`。
- `currentIndex`：数组中正在处理的元素的索引。若指定了初始值 `initialValue`，则起始索引号为 0，否则从索引 1 起始。
- `array`：用于遍历的数组。

`initialValue` 可选

作为第一次调用 `callback` 函数时参数 *previousValue* 的值。若指定了初始值 `initialValue`，则 `currentValue` 则将使用数组第一个元素；否则 `previousValue` 将使用数组第一个元素，而 `currentValue` 将使用数组第二个元素。

因此有如下步骤：

1. ”_reduce“函数第一个参数为回调函数，第二个参数为初始值
2. 进入数组长度的循环体中
3. 当初始值为空时，首个被加数为数组的第一项
4. 当初始值不为空时，首个被加数为初始值

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            // 补全代码
            Array.prototype._reduce = function(f, initValue) {
                for (let i=0; i<this.length; i++) {
                    if (initValue === undefined) {
                        initValue = f(this[i], this[i+1], i+1, this);
                        i++;
                    } else {
                        initValue = f(initValue, this[i], i, this);
                    }
                }
                return initValue;
            }
        </script>
    </body>
</html>
```

