# FED45 添加元素


#### 描述

在数组 arr 的 index 处添加元素 item。不要直接修改数组 arr，结果返回新的数组

#### 示例1

```
输入：[1, 2, 3, 4], 'z', 2
输出：[1, 2, 'z', 3, 4]
```



### 题解

可以直接使用 `splice` 实现。注意 `splice` 方法返回的不是数组。

```javascript
function insert(arr, item, index) {
    var newArr = [...arr]
    newArr.splice(index, 0, item)
    return newArr
}
```

