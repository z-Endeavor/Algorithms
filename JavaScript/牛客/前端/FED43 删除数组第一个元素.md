# FED43 删除数组第一个元素


#### 描述

删除数组 arr 第一个元素。不要直接修改数组 arr，结果返回新的数组

#### 示例1

```
输入：[ 1, 2, 3, 4 ]
输出：[2, 3, 4]
```



### 题解

可以使用 `slice` 直接返回新子数组。

```javascript
function curtail(arr) {
    return arr.slice(1)
}
```

可以定义新数组变量，用 `splice` 方法删除后返回。注意 `splice` 函数返回的不是数组，不能直接返回函数运行结果。

```javascript
function curtail(arr) {
    var newArr = [...arr]
    newArr.splice(0,1)
    return newArr
}
```

也可以用`shift` 方法删除第一个元素。注意 `shfit` 函数返回的不是数组，不能直接返回函数运行结果。

```javascript
function curtail(arr) {
    var newArr = [...arr]
    newArr.shift()
    return newArr
}
```

