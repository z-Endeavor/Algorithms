# FED18 寄生组合式继承

#### 描述

请补全JavaScript代码，要求通过寄生组合式继承使"Chinese"构造函数继承于"Human"构造函数。要求如下：

1. 给"Human"构造函数的原型上添加"getName"函数，该函数返回调用该函数对象的"name"属性
2. 给"Chinese"构造函数的原型上添加"getAge"函数，该函数返回调用该函数对象的"age"属性



### 题解

本题考察**原型链、call、Object.create**。

根据题目要求，通过寄生组合式继承使"Chinese"构造函数继承于"Human"构造函数。寄生组合式继承，即**通过借用构造函数来继承属性，通过原型链的形式来继承方法**，只调用了一次父类构造函数，效率高，也避免了在子类的原型对象上创建不必要的、多余的属性，原型链也不会被改变，核心步骤有：

1. 在"Human"构造函数的原型上添加"getName"函数
2. 在”Chinese“构造函数中通过call函数借助”Human“的构造器来获得通用属性
3. Object.create函数返回一个对象，该对象的 `__proto__` 属性为对象参数的原型。此时将”Chinese“构造函数的原型和通过Object.create返回的实例对象联系起来
4. 最后修复"Chinese"构造函数的原型链，即自身的"constructor"属性需要指向自身
5. 在”Chinese“构造函数的原型上添加”getAge“函数

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            // 补全代码
            function Human(name) {
                this.name = name
                this.kingdom = 'animal'
                this.color = ['yellow', 'white', 'brown', 'black']
            }
            Human.prototype.getName = function() {
                return this.name
            }

            function Chinese(name,age) {
                Human.call(this, name)
                this.age = age
                this.color = 'yellow'
            }
            Chinese.prototype = Object.create(Human.prototype)
            Chinese.prototype.constructor = Chinese
            Chinese.prototype.getAge = function() {
                return this.age
            }
            
        </script>
    </body>
</html>
```

