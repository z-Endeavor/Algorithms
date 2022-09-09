# FED14 Object.freeze

#### 描述

请补全JavaScript代码，要求实现Object.freeze函数的功能且该新函数命名为"_objectFreeze"



### 题解

本题考察**defineProperty**。

根据题目要求，实现一个仿Object.freeze功能的"_objectFreeze"函数，该函数可以冻结一个对象，一个被冻结的对象不能被修改、不能添加新的属性、不能删除已有属性，核心步骤有：

1. 进入对象参数的遍历体中
2. 判断当前对象参数是否为普通对象或数组
3. 如果是普通对象或数组，则递归调用该函数，函数参数为当前遍历项
4. 如果不是，则直接设置该参数的可写性为false
5. 最后通过Object.seal函数封闭该对象，阻止添加新属性并将所有现有属性标记为不可配置

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _objectFreeze = object => {
                // 补全代码
                for(prop in object) {
                    const type = Object.prototype.toString.call(object[prop])
                    if(type === '[Object object]' || type === '[Object array]'){
                        _objectFreeze(object[prop])
                    } else {
                        Object.defineProperty(object, prop, {
                            writable: false
                        })
                    }
                }
                Object.seal(object)
            }
        </script>
    </body>
</html>
```

