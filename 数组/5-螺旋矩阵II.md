# 5-螺旋矩阵II

**模拟行为**的题目在数组中也比较常见，不涉及到什么算法，就是单纯的模拟，比较考察对代码的掌控能力。

最好<u>不要利用随意的判断</u>来模拟，会导致代码混乱，并且避免不了“修修补补”。还是需要**有条理**的进行模拟。

**相关题目**：

- [59.螺旋矩阵II]: #螺旋矩阵II

- [54.螺旋矩阵]: #螺旋矩阵



59. ## 螺旋矩阵II

给你一个正整数 `n` ，生成一个包含 `1` 到 `n2` 所有元素，且元素按顺时针顺序螺旋排列的 `n x n` 正方形矩阵 `matrix`。

**示例1：**

![https://assets.leetcode.com/uploads/2020/11/13/spiraln.jpg](https://assets.leetcode.com/uploads/2020/11/13/spiraln.jpg)

```
输入：n = 3
输出：[[1,2,3],[8,9,4],[7,6,5]]
```

**示例2：**

```
输入：n = 1
输出：[[1]]
```

**提示：**

- `1 <= n <= 20` 



### 思路

本题目就是**模拟过程**，不涉及特殊的算法，考察代码的掌控能力。

注意本题是n x n的正方形矩阵，因此**行和列的情况相同**。

坚持“**循环不变量”**原则，考虑好边界条件。

确定**每一条边左闭右开的区间原则，每一次循环画一圈**，模拟顺时针画矩阵：

- 填充上行从左到右
- 填充右列从上到下
- 填充下行从右到左
- 填充左列从下到上

最关键的就是**循环的边界条件**，很容易出错。

```java
class Solution {
    public int[][] generateMatrix(int n) {
        int[][] arr = new int[n][n];
		// 定义循环次数
        int loop = n / 2;
		// 定义每圈循环的起始位置
        int startX = 0, startY = 0;
		// 填充数字计数
        int num = 1;
		// 填充矩阵
        while (loop > 0) {
            // 填充每一圈上行从左到右，左闭右开
            for (int j=startY; j<n-startY-1; j++) {
                arr[startX][j] = num++;
            }
            // 填充每一圈右列从上到下，左闭右开
            for (int i=startX; i<n-startX-1; i++) {
                arr[i][n-startY-1] = num++;
            }
            // 填充每一圈下行从右到左，左闭右开
            for (int j=n-startY-1; j>startY; j--) {
                arr[n-startX-1][j] = num++;
            }
            // 填充每一圈左列从下到上，左闭右开
            for (int i=n-startX-1; i>startX; i--) {
                arr[i][startY] = num++;
            }
			// 更新每一圈的起始位置
            startX++;
            startY++;
            // 循环次数更新
            loop--;
        }
		// 如果n为奇数，单独处理矩阵中间的数
        if (n % 2 == 1) {
            arr[n/2][n/2] = n * n;
        }

        return arr;
    }
}
```





54. ## 螺旋矩阵

给你一个 `m` 行 `n` 列的矩阵 `matrix` ，请按照 **顺时针螺旋顺序** ，返回矩阵中的所有元素。

**示例1：**

![https://assets.leetcode.com/uploads/2020/11/13/spiral1.jpg](https://assets.leetcode.com/uploads/2020/11/13/spiral1.jpg)

```
输入：matrix = [[1,2,3],[4,5,6],[7,8,9]]
输出：[1,2,3,6,9,8,7,4,5]
```

**示例2：**

![https://assets.leetcode.com/uploads/2020/11/13/spiral.jpg](https://assets.leetcode.com/uploads/2020/11/13/spiral.jpg)

```
输入：matrix = [[1,2,3,4],[5,6,7,8],[9,10,11,12]]
输出：[1,2,3,4,8,12,11,10,9,5,6,7]
```

**提示：**

- `m == matrix.length`
- `n == matrix[i].length`
- `1 <= m, n <= 10`
- `-100 <= matrix[i][j] <= 100`



### 思路







> 注意在这边定义的x、y是对应**二维数组的下标**，不要想当然的与坐标系的x、y相对应，否则会导致边界条件考虑错误！
