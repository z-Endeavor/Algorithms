# FED11 Function.call

#### 描述

请补全JavaScript代码，要求实现Function.call函数的功能且该新函数命名为"_call"。



### 题解

本题考察**原型对象**。

根据题目要求，实现一个仿Object.create功能的"_objectCreate"函数。该函数创建一个新对象，使用现有的对象来提供新创建的对象的proto，核心步骤有：

1. 创建一个新函数
1. 将传入的对象作为原型
1. 返回新的对象

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _objectCreate = proto => {
                // 补全代码
                if (typeof proto !== 'object' || proto === null) return null;
                const fn = function(){};
                fn.prototype = proto;
                return fn;
            }
        </script>
    </body>
</html>
```

