# JS8 数组排序

#### 描述

请补全JavaScript代码，根据预设代码中的数组，实现以下功能：

1. 列表只展示数组中的name属性
2. 实现点击"销量升序"按钮，列表内容按照销量升序重新渲染
3. 实现点击"销量降序"按钮，列表内容按照销量降序重新渲染

#### 注意

1. 必须使用DOM0级标准事件（onclick）



### 题解

考察数组的 `sort()`  根据**升序降序分别对原数组进行排序**。

排序完成后直接在元素内按顺序添加名字信息。

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
    </head>
    <body>
        <button class='up'>销量升序</button>
        <button class='down'>销量降序</button>
        <ul></ul>

        <script>
            var cups = [
                { type: 1, price: 100, color: 'black', sales: 3000, name: '牛客logo马克杯' },
                { type: 2, price: 40, color: 'blue', sales: 1000, name: '无盖星空杯' },
                { type: 4, price: 60, color: 'green', sales: 200, name: '老式茶杯' },
                { type: 3, price: 50, color: 'green', sales: 600, name: '欧式印花杯' }
            ]
            var ul = document.querySelector('ul');
            var upbtn = document.querySelector('.up');
            var downbtn = document.querySelector('.down');
            // 补全代码
            upbtn.onclick = () => {
                cups.sort((a,b) => { return a.sales - b.sales; });
                ul.innerHTML = getName();
            }
            
            downbtn.onclick = () => {
                cups.sort((a,b) => { return b.sales - a.sales; });
                ul.innerHTML = getName();
            }
            
            let getName = function() {
                var str = '';
                for (let i = 0; i<cups.length; i++) {
                    // str += '<li>' + cups[i].name + '</li>';
                    str += `<li>${cups[i].name}</li>`;
                }
                return str;
            }
            
        </script>
    </body>
</html>
```

