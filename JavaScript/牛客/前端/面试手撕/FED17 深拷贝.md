# FED17 深拷贝

#### 描述

请补全JavaScript代码，要求实现对象参数的深拷贝并返回拷贝之后的新对象。

#### 注意：

1. 需要考虑函数、正则、日期、ES6新对象
2. 需要考虑循环引用问题



### 题解

本题考察**递归、遍历、Map**。

根据题目要求，实现对象参数的深拷贝并返回拷贝之后的新对象，因为需要考虑参数对象和参数对象的每个数据项的数据类型可能包括函数、正则、日期、ES6新对象且必须考虑循环引用问题，所以需要引入ES6新对象Map并且详细的判断数据类型，核心步骤有：

1. 如果对象参数的数据类型不为“object”或为“null”，则直接返回该参数
2. 获取到对象参数的构造函数名，判断是否为函数、正则、日期、ES6新对象其中之一，如果是则直接返回通过该参数对象对应的构造函数生成的新实例对象
3. 当以上条件判断之后函数依然没有结束时继续进行以下操作
4. 在Map对象中获取当前参数对象，如果能获取到，则说明这里为循环引用并返回Map对象中该参数对象的值
5. 如果在Map对象中没有获取到对应的值，则保存该参数对象到Map中，作为标记
6. 根据该参数的数据类型是否为数组创建新对象
7. 遍历该对象参数，将每一项递归调用该函数本身的返回值赋给新对象

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _sampleDeepClone = (target, map = new Map()) => {
                // 补全代码
                if(typeof target === 'object' && target !== null) {
                    const constructor = target.constructor
                    if(/^(Function|RegExp|Date|Map|Set)$/i.test(constructor.name)) return new constructor(target)
                    if(map.get(target)) return map.get(target)
                    map.set(target, true)
                    const cloneTarget = Array.isArray(target) ? [] : {}
                    for(prop in target) {
                        if(target.hasOwnProperty(prop)) {
                            cloneTarget[prop] = _completeDeepClone(target[prop], map)
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

