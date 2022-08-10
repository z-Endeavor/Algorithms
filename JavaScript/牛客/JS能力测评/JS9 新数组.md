# JS9 新数组

#### 描述

请补全JavaScript代码，该函数接受两个参数分别为数组、索引值，要求在不改变原数组的情况下返回删除了索引项的新数组。



### 题解

#### 1、暴力遍历

遍历数组，将`index`之外的数组元素push到新数组中。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _delete = (array,index) => {
                // 补全代码
                let res = [];
                for (let i = 0; i < array.length; i++) {
                    if (i != index) {
                        res.push(array[i]);
                    }
                }
                return res;
            }
        </script>
    </body>
</html>
```

#### 2、利用数组的 slice 和 concat 方法

利用 `slice` 获取数组的子串，再利用 `concat` 重新连接成新数组。

> `slice`方法返回一个新的数组对象，原始数组不会被改变。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _delete = (array,index) => {
                // 补全代码
                return array.slice(0, index).concat(array.slice(index+1, array.length));
            }
        </script>
    </body>
</html>
```

#### 3、利用数组的 splice 方法

利用 `splice` 删除现有元素来修改数组。

利用扩展运算符 `...` 来复制新的数组。

> `splice` 方法会改变原始数组。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _delete = (array,index) => {
                // 补全代码
                let newArr = [...array];
                newArr.splice(index, 1);
                return newArr;
            }
        </script>
    </body>
</html>
```

