# Rotate Image

You are given an n x n 2D matrix representing an image, rotate the image by 90 degrees (clockwise).

You have to rotate the image in-place, which means you have to modify the input 2D matrix directly. **DO NOT** allocate another 2D matrix and do the rotation.

## Example:

![image](https://user-images.githubusercontent.com/68459485/126895734-61801b37-d6b8-411d-99ca-eadd1730bf86.png)

_**Input:**_ `matrix = [[1,2,3],[4,5,6],[7,8,9]]`

_**Output:**_ `[[7,4,1],[8,5,2],[9,6,3]]`

## Constraints:

`matrix.length == n`

`matrix[i].length == n`

`1 <= n <= 20`

`-1000 <= matrix[i][j] <= 1000`

## Solution in JavaScript

```
var rotate = function(matrix) {
    for (let i = 0; i < matrix.length; i++) {
        for (let j = i; j < matrix.length; j++) {
            let temp = matrix[j][i]
            matrix[j][i] = matrix[i][j]
            matrix[i][j] = temp
        }
    }
    
    for (let i = 0; i < matrix.length; i++) {
        for (let j = 0; j < matrix.length / 2; j++) {
            let temp = matrix[i][j]
            matrix[i][j] = matrix[i][matrix.length - j - 1]
            matrix[i][matrix.length - j - 1] = temp
        }
    }
};
```
