# FED5 全排列

#### 描述

请补全JavaScript代码，要求以数组的形式返回字符串参数的所有排列组合。

注意：

1. 字符串参数中的字符无重复且仅包含小写字母
2. 返回的排列组合数组不区分顺序

#### 示例1

```
输入：_permute('abc')
输出：['abc','acb','bac','bca','cab','cba']
```



### 题解

本题使用**递归**思路。

‘abc’的全排列等于 ('a'拼接上'bc'的全排列数组中的每一项) + ('b'拼接上'ac'的全排列数组的每一项) + ('c'拼接上'ab'的全排列数组的每一项)。

1. 当字符串长度为1的时候，返回自身，作为递归结束的条件。
2. 当字符串长度大于1时，循环遍历字符串的每一个字符，获取剩余字符串作为新的递归字符串。

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            const _permute = string => {
                // 补全代码
                let res = []
                if (string.length === 1) {
                    res.push(string)
                    return res
                } else {
                    for (let i=0; i<string.length; i++) {
                        let x = string[i]
                        let restStr = string.slice(0,i) + string.slice(i+1,string.length)
                        _permute(restStr).forEach( item => {
                            res.push(x + item)
                        })
                    }
                }
                return res
            }
        </script>
    </body>
</html>
```

