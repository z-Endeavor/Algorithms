# FED21 修改this指向


#### 描述

封装函数 f，使 f 的 this 指向指定的对象



### 题解

利用 `call()` 、 `bind()` 、 `apply()` 三种方法改变this指向。

- call(obj, arg1, arg2 ...)
- bind(obj, arg1, arg2, ...)：返回的是函数，需要调用才执行。
- apply(obj, [arg1, arg2, ..])：参数是数组形式传入。

注意题目要求返回的是函数。

#### 1、apply

```javascript
function bindThis(f, oTarget) {
    return function(){
        return f.apply(oTarget, arguments)
    }
}
```

#### 2、bind

```javascript
function bindThis(f, oTarget) {
	return f.bind(oTarget)
}
```

#### 3、call

```javascript
function bindThis(f, oTarget) {
    return function() {
        return f.call(oTarget, ...arguments)
    }
}
```

