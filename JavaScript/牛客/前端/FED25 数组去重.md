# FED25 数组去重


#### 描述

为 Array 对象添加一个去除重复项的方法

#### 示例1

```
输入：[false, true, undefined, null, NaN, 0, 1, {}, {}, 'a', 'a', NaN]
输出：[false, true, undefined, null, NaN, 0, 1, {}, {}, 'a']
```



### 题解

#### 1、直接用Set去重

```javascript
Array.prototype.uniq = function () {
    return Array.from(new Set(this))
}

Array.prototype.uniq = function () {
    return [...new Set(this)];
}
```

#### 2、利用Set进行判断去重

```javascript
Array.prototype.uniq = function () {
    let arr = this
    let res = []
    let set = new Set()
    for(let i=0; i<arr.length; i++) {
        if(!set.has(arr[i])) {
            res.push(arr[i])
            set.add(arr[i])
        }
    }
    return res
}
```

