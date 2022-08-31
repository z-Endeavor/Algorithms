# FED12 Function.bind

#### 描述

请补全JavaScript代码，要求实现Function.bind函数的功能且该新函数命名为"_bind"。



### 题解

本题考察**this，apply**。

根据题目要求，实现一个仿Function.bind功能的"Function._bind"函数，该函数会**返回一个新的函数且该新函数内部通过apply修改了函数内部this指向**，核心步骤有：

1. 创建一个新this来保存旧的this对象
2. 返回一个匿名函数，该匿名函数返回通过apply修改了指针指向的函数运算结果。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            // 补全代码
            Function.prototype._bind = function(target, ...args1) {
                const _this = this
                return function(...args2){
                    return _this.apply(target, args1.concat(args2))
                }
            }
        </script>
    </body>
</html>
```

