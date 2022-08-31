# FED11 Function.call

#### 描述

请补全JavaScript代码，要求实现Function.call函数的功能且该新函数命名为"_call"。



### 题解

本题考察**this**。

该函数会临时修改内部this的指向并返回结果。

Function里面的this指向的肯定是一个实例方法，call传入两个参数，第一个参数是一个对象（默认window），第二个参数是针对this这个实例方法的参数。

1. 给传入的对象加上一个fn属性，这个属性指向this，也就是要调用的方法
2. 然后再从这个对象里面调用fn这个方法，即可得到答案
3. 删除填进去的属性

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            // 补全代码
            Function.prototype._call = function(obj=window, ...args){
                let fn = Symbol('obj')
                obj.fn = this
                let res = obj.fn(...args)
                delete obj.fn
                return res
            }
        </script>
    </body>
</html>
```

