---
title: Google Meta Amazon Coding Interview Question - Toeplitz Matrix
published: true
---

```cpp
bool is_toeplitz(const int &height, const int &width, const vector < vector < int > > &matrix)
{
 for(int i = 1 ; i < height ; i++)
  for(int  j = 1 ; j < width ; j++)
   if (matrix[i][j] != matrix[i-1][j-1]) return false;

 return true;
}
```
