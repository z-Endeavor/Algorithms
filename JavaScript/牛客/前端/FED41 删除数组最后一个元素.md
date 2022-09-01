# FED41 删除数组最后一个元素


#### 描述

删除数组 arr 最后一个元素。不要直接修改数组 arr，结果返回新的数组

#### 示例1

```
输入：[ 1, 2, 3, 4 ]
输出：[1, 2, 3]
```



### 题解

可以使用 `slice` 直接返回新子数组。

```javascript
function truncate(arr) {
    return arr.slice(0, -1)
    // return arr.slice(0, arr.length-1)
}
```

可以定义新数组变量，用 `splice` 方法删除后返回。

```javascript
function truncate(arr) {
    let newArr = [...arr]
    newArr.splice(-1, 1)
    return newArr
}
```

