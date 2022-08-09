# JS2 文件扩展名


#### 描述

请补全JavaScript代码，要求以字符串的形式返回文件名扩展名，文件名参数为"filename"。



### 题解

注意文件扩展名是 `.扩展名` 的形式，不要忘记了 `.` 。

主要考察**字符串的处理**，利用字符串的方法找到扩展名返回即可。

#### 1、split

利用`split`方法将字符串以 `.` 分割到数组，接着取数组的**最后一个元素**。

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
    </head>
    <body>
        
        <script>
            const _getExFilename = (filename) => {
                // 补全代码
                let str = filename.split('.');
                return '.' + str[str.length-1];
            }
        </script>
    </body>
</html>
```

#### 2、LastIndexOf

也可以利用 `lastIndexOf` 方法找到 `.` 的索引，返回后面

`lastIndexOf` 返回最后一次出现指定值的索引。

> 文件名中可能会出现 `.` ，所以不能使用 `indexOf` （返回第一次出现指定值的索引）。

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
    </head>
    <body>
        
        <script>
            const _getExFilename = (filename) => {
                // 补全代码
                let index = filename.lastIndexOf('.');
                return filename.slice(index);
            }
        </script>
    </body>
</html>
```

