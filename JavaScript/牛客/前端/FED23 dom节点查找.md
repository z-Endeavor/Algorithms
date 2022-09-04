# FED23 dom节点查找


#### 描述

查找两个节点的最近的一个共同父节点，可以包括节点自身

#### 输入描述

oNode1 和 oNode2 在同一文档中，且不会为相同的节点



### 题解

两个节点不为相同节点，判断**一个节点的父节点是否包含另一个节点**即可。

使用节点的 `parentNode` 属性和 `contains()` 方法。

```javascript
function commonParentNode(oNode1, oNode2) {
    while(true) {
        oNode1 = oNode1.parentNode
        if (oNode1.contains(oNode2)) {
            return oNode1
        }
    }
}
```

