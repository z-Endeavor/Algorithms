# FED20 观察者模式

#### 描述

请补全JavaScript代码，完成"Observer"、"Observerd"类实现观察者模式。要求如下：

1. 被观察者构造函数需要包含"name"属性和"state"属性且"state"初始值为"走路"
2. 被观察者创建"setObserver"函数用于保存观察者们
3. 被观察者创建"setState"函数用于设置该观察者"state"并且通知所有观察者
4. 观察者创建"update"函数用于被观察者进行消息通知，该函数需要打印（console.log）数据，数据格式为：小明正在走路。其中"小明"为被观察者的"name"属性，"走路"为被观察者的"state"属性

#### 注意：

1. "Observer"为观察者，"Observerd"为被观察者



### 题解

本题考察**设计模式**。

根据题目要求完成"Observer"、"Observerd"类实现观察者模式。核心步骤有：

1. 被观察者构造函数声明三个属性分别为"name"用于保存被观察者姓名、"state"用于保存被观察者状态（初始值为‘走路’）、"observers"用于保存观察者们
2. 被观察者创建"setObserver"函数，该函数通过数组的push函数将观察者参数传入"observers"数组中
3. 被观察者创建"setState"函数，该函数首先通过参数修改被观察者的"state"属性，然后通过遍历"observers"数组分别调用各个观察者的"update"函数并且将该被观察者作为参数传入
4. 观察者创建"update"函数，用于打印信息

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset=utf-8>
    </head>
    <body>
    	
        <script type="text/javascript">
            // 补全代码
            class Observerd {
                constructor(name){
                    this.name = name
                    this.state = '走路'
                    this.observers = []
                }
                setObserver(observer) {
                    this.observers.push(observer)
                }
                setState(state) {
                    this.state = state
                    this.observers.forEach( item => item.update(this) )
                }
            }

            class Observer {
                constructor() {
                    
                }
                update(observerd) {
                    console.log(observerd.name + '正在' + observerd.state)
                }
            }
        </script>
    </body>
</html>
```

