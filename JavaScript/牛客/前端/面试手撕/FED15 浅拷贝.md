# FED15 浅拷贝

#### 描述

请补全JavaScript代码，要求实现一个对象参数的浅拷贝并返回拷贝之后的新对象。

#### 注意：

1. 参数可能包含函数、正则、日期、ES6新对象



### 题解

本题考察**遍历**。

根据题目要求，实现一个对象参数的浅拷贝并返回拷贝之后的新对象，因为可能包含函数、正则、日期、ES6新对象，所以需要对这些对象类型进行特殊判断，核心步骤有：

1. 如果对象参数的数据类型不为"object"或为"null"，则直接返回该参数
2. 如果是"object"，就获取该参数的构造函数名，通过正则表达式判断该对象是否为函数、正则、日期、ES6新对象等，如果返回true，则直接返回该参数
3. 当以上条件判断之后函数依然没有结束时，此时通过数组的原型方法判断该参数为普通对象或数组并创建相应数据类型的新变量
4. 进入遍历体，将对象参数的每一项赋值给新变量
5. 最终返回该新变量

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _shallowClone = target => {
                // 补全代码
                if (typeof target === 'object' && target !== null) {
                    const constructor = target.constructor
                    if(/^(Function|RegExp|Date|Map|Set)$/i.test(constructor.name)) return target
                    const cloneTarget = Array.isArray(target) ? [] : {}
                    for(prop in target) {
                        if(target.hasOwnProperty(prop)) {
                            cloneTarget[prop] = target[prop]
                        }
                    }
                    return cloneTarget
                } else {
                    return target
                }
            }
        </script>
    </body>
</html>
```

