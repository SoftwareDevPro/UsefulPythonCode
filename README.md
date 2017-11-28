# Useful Python Code

## Unpacking
>>> a, b, c = 1, 2, 3
>>> a, b, c
(1, 2, 3)
>>> a, b, c = [1,2,3]
>>> a,b,c
(1,2,3)
>>> a,b,c = (2 * i + 1 for i in range(3))
>>> a,b,c
(1,3,5)
>>> a,(b,c),d = [1,(2,3),4]
>>> a
1
>>> b
2
>>> c
3
>>> d
4
