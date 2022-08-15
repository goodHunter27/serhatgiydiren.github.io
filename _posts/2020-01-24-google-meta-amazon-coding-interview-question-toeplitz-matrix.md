---
title: Google Meta Amazon Coding Interview Question - Toeplitz Matrix
published: true
---

{% include temp.md %}

Given a matrix in the form `(int height, int weight, vector < vector < int > > matrix)`, determine if the matrix is in the form of Toeplitz. 

> In linear algebra, a Toeplitz matrix or diagonal-constant matrix, named after Otto Toeplitz, is a matrix in which each descending diagonal from left to right is constant. For instance, the following matrix is a Toeplitz matrix: 

| A | B | C | D | E 
| F | A | B | C | D 
| G | F | A | B | C 
| H | G | F | A | B 
| I | H | G | F | A 
| J | I | H | G | F 


[For more information, click here.](https://en.wikipedia.org/wiki/Toeplitz_matrix){:target="_blank"} 

```cpp
bool is_toeplitz(const int &height, const int &width, const vector < vector < int > > &matrix)
{
 for(int i = 1 ; i < height ; i++)
  for(int  j = 1 ; j < width ; j++)
   if (matrix[i][j] != matrix[i-1][j-1]) return false;

 return true;
}
```
