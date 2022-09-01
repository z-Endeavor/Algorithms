# FED44 数组合并


#### 描述

合并数组 arr1 和数组 arr2。不要直接修改数组 arr，结果返回新的数组

#### 示例1

```
输入：[1, 2, 3, 4], ['a', 'b', 'c', 1]
输出：[1, 2, 3, 4, 'a', 'b', 'c', 1]
```



### 题解

可以使用 `concat` 直接连接数组。

```javascript
function concat(arr1, arr2) {
    return arr1.concat(arr2)
}
```

