# Useful Python Code

## Unpacking
>>> a, b, c = 1, 2, 3<br />
>>> a, b, c<br />
(1, 2, 3)<br />
>>> a, b, c = [1,2,3]<br />
>>> a,b,c<br />
(1,2,3)<br />
>>> a,b,c = (2 * i + 1 for i in range(3))<br />
>>> a,b,c<br />
(1,3,5)<br />
>>> a,(b,c),d = [1,(2,3),4]<br />
>>> a<br />
1<br />
>>> b<br />
2<br />
>>> c<br />
3<br />
>>> d<br />
4<br />
