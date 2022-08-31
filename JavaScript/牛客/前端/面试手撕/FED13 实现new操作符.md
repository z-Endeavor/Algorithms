# FED13 实现new操作符

#### 描述

请补全JavaScript代码，要求实现Function.bind函数的功能且该新函数命名为"_bind"。



### 题解

本题考察**原型链**。

`new`关键字会进行如下操作：

1. 创建一个空的简单 JavaScript 对象（即**`{}`**）；
2. 为步骤 1 新创建的对象添加属性**`__proto__`**，将该属性链接至构造函数的原型对象 ；
3. 将步骤 1 新创建的对象作为**`this`**的上下文 ；
4. 如果该函数没有返回对象，则返回**`this`**。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _new = function(constructor, ...args) {
                // 补全代码
                // 创建一个新对象
                const obj = {}
                // 为新对象添加属性__proto__，链接至构造函数的原型对象
                obj.__proto__ = constructor.prototype
                // 执行构造函数，this被绑定在新对象上
                const res = constructor.apply(obj, args)
                // 确保返回一个对象
                return res instanceof Object ? res : obj
            }
        </script>
    </body>
</html>
```

