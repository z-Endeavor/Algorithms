# JS6 判断版本

#### 描述

请补全JavaScript代码，该函数接收两个参数分别为旧版本、新版本，当新版本高于旧版本时表明需要更新，返回true，否则返回false。

#### 注意

1. 版本号格式均为"X.X.X"
2. X∈[0,9]
3. 当两个版本号相同时，不需要更新



### 题解

#### 1、嵌套判断

最直接的思路是从高到低嵌套判断版本号， 利用 `split('.')` 分割三位版本号分别比较。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _shouldUpdate = (oldVersion, newVersion) => {
                // 补全代码
                let oldVer = oldVersion.split('.');
                let newVer = newVersion.split('.');
                if (newVer[0] > oldVer[0]) {
                    return true;
                } else {
                    if (newVer[1] > oldVer[1]) {
                        return true;
                    } else {
                        if (newVer[2] > oldVer[2]) {
                            return true;
                        } else {
                            return false;
                        }
                    }
                }
            }
        </script>
    </body>
</html>
```

#### 2、比较完整版本号

版本号三位都是**1位数字**，所以可以直接将字符串拼接为数字比较。

- 去除版本号中的`.`
- 将新旧版本号转换为数字 （甚至可以略过这步，直接比较字符串大小）
- 比较大小

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _shouldUpdate = (oldVersion, newVersion) => {
                // 补全代码
                let oldVer = parseInt(oldVersion.split('.').join(''));
                let newVer = parseInt(newVersion.split('.').join(''));
                return newVer > oldVer;
            }
        </script>
    </body>
</html>
```

