# FED19 发布订阅模式

#### 描述

请补全JavaScript代码，完成"EventEmitter"类实现发布订阅模式。

#### 注意：

1.  同一名称事件可能有多个不同的执行函数
2. 通过"on"函数添加事件
3. 通过"emit"函数触发事件



### 题解

本题考察**设计模式**。

根据题目要求，完成"EventEmitter"类实现发布订阅模式，考虑到**同一名称事件可能有多个不同的执行函数**，所以在构造函数中需要**以对象的结构存放事件**，核心步骤有：

1. 构造函数中创建”events“对象变量用于存放所有的事件
2. 添加”on“函数，用于订阅事件。当总事件中不存在此事件时创建新的事件数组，当存在时将”fn“函数添加在该事件对应数组中
3. 添加”emit“函数，用于发布事件，遍历该事件下的函数数组并全部执行

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            class EventEmitter {
                // 补全代码
                constructor() {
                    this.events = {}
                }
                on(event, fn) {
                    if(!this.events[event]) {
                        this.events[event] = [fn]
                    } else {
                        this.events[event].push(fn)
                    }
                }
                emit(event) {
                    if(this.events[event]) {
                        this.events[event].forEach( callback => callback() )
                    }
                }
            }
        </script>
    </body>
</html>
```

