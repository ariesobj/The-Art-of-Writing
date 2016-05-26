Native Matrix Multiplication Implementation
===========================================

```python
# Given two matrix A and B, calculate matrix multiplication of A and B, i.e AB.
#
# Native implementation (by definition)
#
# Assumption:
#   X = <x_ij> = X[i][j]
#   matrix multiplicative can be defined for matrix A and B
#     (if not, IndexError would be raised)
#
def mul(X, Y):
    # According to the assumption on the above:
    #   X: a by b
    #   Y: b by c

    a = len(X)
    b = len(Y)
    c = len(Y[0])

    return [[sum(X[y][i] * Y[i][x] for i in range(b)) for x in range(c)] for y in range(a)]

```

위 방식은 가장 직관적이고 간단하면서 시간복잡도로 `O(n**3)` 를 갖습니다.

코드의 길이를 직관적으로 줄이기 위해 [List Comprehension][reference for list comprehensions]를 사용하였습니다.

[tutorial for list comprehensions]: https://docs.python.org/3/tutorial/datastructures.html#list-comprehensions
[reference for list comprehensions]: https://docs.python.org/3/reference/expressions.html#displays-for-lists-sets-and-dictionaries
