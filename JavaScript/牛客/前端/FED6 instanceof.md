# FED6 instanceof

#### 描述

请补全JavaScript代码，要求以Boolean的形式返回第一个实例参数是否在第二个函数参数的原型链上。



### 题解

本题考察**原型链**。

**`instanceof`** **运算符**用于检测构造函数的 `prototype` 属性是否出现在某个实例对象的原型链上。

根据题目要求，实现一个仿instanceof功能的"_instanceof"函数，该函数可以判断首参是否在第二个Fn构造函数的原型链上，核心步骤有：

1. 获取首个对象参数的原型对象
1. 获取Fn函数的原型对象
1. 进入死循环，当两个参数的原型对象相等时返回true
1. 当两个参数的原型对象不相等时获取首个对象参数原型的原型，继续循环，直到为null或相等时返回。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _instanceof = (target, Fn) => {
                // 补全代码
                let proto = target.__proto__
                let prototype = Fn.prototype
                while (true) {
                    if(proto === Fn.prototype) return true
                    if(proto === null) return false
                    proto = proto.__proto__
                }
            }
        </script>
    </body>
</html>
```

