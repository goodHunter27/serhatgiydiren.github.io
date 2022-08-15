---
title: Google Meta Amazon Coding Interview Question - Toeplitz Matrix
published: true
---

Given a matrix in the form `(int height, int weight, vector < vector < int > > matrix)`, determine the matrix is in the form of Toeplitz. 

In linear algebra, a Toeplitz matrix or diagonal-constant matrix, named after Otto Toeplitz, is a matrix in which each descending diagonal from left to right is constant. For instance, the following matrix is a Toeplitz matrix: 

| A | B | C |
| D | A | B |

[For more information for Toeplitz Matrix, click here.]([https://amzn.to/3vdVLXd](https://en.wikipedia.org/wiki/Toeplitz_matrix)){:target="_blank"} 

```cpp
bool is_toeplitz(const int &height, const int &width, const vector < vector < int > > &matrix)
{
 for(int i = 1 ; i < height ; i++)
  for(int  j = 1 ; j < width ; j++)
   if (matrix[i][j] != matrix[i-1][j-1]) return false;

 return true;
}
```
