# FED3 合法的URL

#### 描述

请补全JavaScript代码，要求以Boolean的形式返回字符串参数是否为合法的URL格式。

注意：

1. 协议仅为HTTP（S）



### 题解

本题考察 **正则表达式**。

分析URL的结构：

1. 首先以HTTP(S)协议开头，注意URL可以不包含该协议信息。 `/^(https?:\/\/)?/`
2. 主机域名部分可以是任意字母或数字，包含“-”或不包含“-”。 `(([A-Za-z0-9]+-[A-Za-z0-9]+|[A-Za-z0-9]+)\.)+`
3. 顶级域名com cn等为2-6位字母。`([A-Za-z]{2,6})+`
4. 端口号为数字，可选项。 `(:\d+)?`
5. 请求路径如/login之类的，任意字符，可选项。 `(\/.*)?`
6. 问号传参和哈希值如?age=1，可选项。 `(\?.*)?` `(#.*)?`
7. 最后结束符。 `$`

最后用 `RegExp` 的 `test` 方法测试是否匹配。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _isUrl = url => {
                // 补全代码
                return /^(https?:\/\/)?(([A-Za-z0-9]+-[A-Za-z0-9]+|[A-Za-z0-9]+)\.)+([A-Za-z]{2,6})+(:\d+)?(\/.*)?(\?.*)?(#.*)?$/.test(url);
            }
        </script>
    </body>
</html>
```

