# FED42 添加元素


#### 描述

在数组 arr 开头添加元素 item。不要直接修改数组 arr，结果返回新的数组

#### 示例1

```
输入：[1, 2, 3, 4], 10
输出：[10, 1, 2, 3, 4]
```



### 题解

可以使用 `concat` 直接连接数组。

```javascript
function prepend(arr, item) {
    return [item].concat(arr)
}
```

也可以用 `unshift` 方法在数组开头添加元素。注意 `unshift` 函数返回的不是数组，不能直接返回函数运行结果。

```javascript
function prepend(arr, item) {
    var newArr = [...arr]
    newArr.unshift(item)
    return newArr
}
```

