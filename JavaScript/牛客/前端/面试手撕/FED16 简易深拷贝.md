# FED16 简易深拷贝

#### 描述

请补全JavaScript代码，要求实现对象参数的深拷贝并返回拷贝之后的新对象。

#### 注意：

1. 参数对象和参数对象的每个数据项的数据类型范围仅在数组、普通对象（{}）、基本数据类型中
2. 无需考虑循环引用问题



### 题解

本题考察**递归、遍历**。

根据题目要求，实现对象参数的深拷贝并返回拷贝之后的新对象，因为参数对象和参数对象的每个数据项的数据类型范围仅在数组、普通对象（{}）、基本数据类型中且**无需考虑循环引用问题**，所以不需要做过多的数据类型判断，核心步骤有：

1. 如果对象参数的数据类型不为“object”或为“null”，则直接返回该参数
2. 根据该参数的数据类型是否为数组创建新对象
3. 遍历该对象参数，将每一项递归调用该函数本身的返回值赋给新对象

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _sampleDeepClone = target => {
                // 补全代码
                if(typeof target === 'object' && target !== null) {
                    const cloneTarget = Array.isArray(target) ? [] : {}
                    for(prop in target) {
                        if(target.hasOwnProperty(prop)) {
                            cloneTarget[prop] = _sampleDeepClone(target[prop])
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

