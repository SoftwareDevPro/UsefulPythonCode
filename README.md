# Useful Python Code

## Unpacking
\>\>\> a, b, c = 1, 2, 3<br />
\>\>\> a, b, c<br />
\(1, 2, 3\)<br />
\>\>\> a, b, c = [1,2,3]<br />
\>\>\> a,b,c<br />
(1,2,3)<br />
\>\>\> a,b,c = (2 * i + 1 for i in range(3))<br />
\>\>\> a,b,c<br />
(1,3,5)<br />
\>\>\> a,(b,c),d = [1,(2,3),4]<br />
\>\>\> a<br />
1<br />
\>\>\> b<br />
2<br />
\>\>\> c<br />
3<br />
\>\>\> d<br />
4<br />
<br />

## Unpacking for swapping variables:

\>\>\> a, b = 1, 2<br />
\>\>\> a, b, = b, a<br />
\>\>\> a, b<br />
(2, 1)<br />
<br />

## Extended unpacking (use in Python 3 only)

\>\>\> a, *b, c = [1, 2, 3, 4, 5]<br />
\>\>\> a<br />
1<br />
\>\>\> b<br />
[2,3,4]<br />
\>\>\> c<br />
5<br />

<br />

## Negative Indexing

\>\>\> a = [01,2,3,4,5,6,7,8,9,0,10]<br />
\>\>\> a[-1]<br />
10<br />
\>\>\> a[-3]<br />
8<br />

<br />

## List slices (a[start:end])

\>\>\> a = [0,1,2,3,4,5,6,7,8,9,10]<br />
\>\>\> a[2:8]<br />
[2,3,4,5,6,7]<br />

<br />

## List Slices with Negative Indexing

\>\>\> a = [0,1,3,4,5,6,7,8,9,10]<br />
\>\>\> a[-4:-2]<br />
[7,8]<br />

<br />

## List Slices with Step \(a\[start\: end\: step\]\)

\>\>\> a = [0,1,2,3,4,5,6,7,8,9,10]<br />
\>\>\> a[::2]<br />
[0,2,3,4,6,8,10]<br />
\>\>\> a[::3]<br />
[0,3,6,9]<br />
\>\>\> a[2:8:2]<br />
[2,4,6]<br />


<br />

## List Slices with negative step

\>\>\> a = [0,1,2,3,4,5,6,7,8,9,10]<br />
\>\>\> a[::-1]<br />
[10,9,8,7,6,5,4,3,2,1,0]<br />
\>\>\> a[::-2]<br />
[10,8,6,4,2,0]<br />

<br />

## List Slice Assignment

\>\>\> a = [1,2,3,4,5]<br />
\>\>\> a[2:3] = [0,0]<br />
\>\>\> a<br />
[1,2,0,0,4,5]<br />
\>\>\> a[1:1] = [8,9]<br />
\>\>\> a<br />
[1,8,9,2,0,0,4,5]<br />
\>\>\> a[1:-1] = []<br />
\>\>\> a<br />
[1, 5]<br />

<br />

## Naming Slices (slice(start,end,step))

\>\>\> a = [0,1,2,3,4,5]<br />
\>\>\> LASTTHREE = slice(-3, None)<br />
\>\>\> LASTTHREE<br />
slice(-3, None)<br />
\>\>\> a[LASTTHREE]<br />
[3,4,5]<br />

<br />

## Iterating over list index and value pairs (enumerate)

\>\>\> a = ['Hello','world','!']<br />
\>\>\> for i,x in enumerate(a):<br />
\.\.\.     print '{}: {}'.format(i,x)<br />
\.\.\.<br />
0: Hello<br />
1: world<br />
2: !<br />

<br />

## Iterating over dictionary key and value pairs (dict.iteritems)

\>\>\> m = {'a': 1, 'b': 2, 'c': 3, 'd': 4}<br />
\>\>\> for k,v, in m.itermitems():<br />
\.\.\.   print '{}:{}'.format(k, v)<br />
\.\.\.<br />
a: 1<br />
c: 3<br />
b: 2<br />
d: 4<br />

<br />

## Zipping and unzipping list and iterables

\>\>\> a = [1,2,3]<br />
\>\>\> b = ['a','b','c']<br />
\>\>\> z = zip(a,b)<br />
\>\>\> z<br />
[(1,'a'),(2,'b'),(3,'c')]<br />
\>\>\>(*z)<br />
[(1,2,3),('a','b','c')]<br />

<br />

## Grouping adjacent list items using zip

\>\>\> a = [1,2,3,4,5,6]<br />
\>\>\> # Using iterators<br />
\>\>\> group_adjacent = lambda a, k: zip(*([iter(a)]*k))<br />
\>\>\> group_adjacent(a,3)<br />
[(1,2,3),(4,5,6)]<br />
\>\>\> group_adjacent(a,2)<br />
[(1,2),(3,4),(5,6)]<br />
\>\>\> group_adjacent(a,2)<br />
[(1,),(2,),(3,),(4,),(5,),(6,)]<br />
\>\>\> # Using slices<br />
\>\>\> from itertools import slice<br />
\>\>\> group_adjacent = lambda a, k: zip(*(islice(a,i,None,k) for i in range(k)))<br />
\>\>\> group_adjacent(a,3)<br />
[(1,2,3),(4,5,6)]<br />
\>\>\> group_adjacent(a,2)<br />
[(1,2),(3,4),(5,6)]<br />
\>\>\> group_adjacent(a,2)<br />
[(1,),(2,),(3,),(4,),(5,),(6,)]<br />

<br />

## Sliding windows (n-grams) using zip and iterators

\>\>\> from itertools import islice<br />
\>\>\> def n_grams(a, n):<br />
\.\.\.  z = (islice(a, i, None) for i in range(n))<br />
\.\.\.  return zip(*z)<br />
\.\.\.<br />
\>\>\> a = [1,2,3,4,5,6]<br />
\>\>\> n_grams(a, 3)<br />
[(1,2,3),(2,3,4),(3,4,5),(4,5,6)]<br />
\>\>\> n_grams(a, 2)<br />
[(1,2),(2,3),(3,4),(4,5),(5,6)]<br />
\>\>\> n_grams(a, 4)<br />
[(1,2,3,4),(2,3,4,5),(3,4,5,6)]<br />

<br />

## Inverting a dictionary using zip

\>\>\> m = {'a':1,'b':2,'c':3,'d':4}<br />
\>\>\> m.items()<br />
[('a',1),('c',3),('b',2),('d',4)]<br />
\>\>\> zip(m.values(), m.keys())<br />
[(1,'a'),(3,'c'),(2,'b'),(4,'d')]<br />
\>\>\> mi = dict(zip(m.values(), m.keys()))<br />
\>\>\> mi<br />
{'a':1,'b':2,'c':3,'d':4}<br />

<br />

## Flattening lists

\>\>\> a = [[1,2],[3,4],[5,6]]<br />
\>\>\> list(itertools.chain.from_iterable(a))<br />
[1,2,3,4,5,6]<br />
<br />
\>\>\> sum(a, [])<br />
[1,2,3,4,5,6]<br />
<br />
\>\>\> [x for l in a for x in l]<br />
[1,2,3,4,5,6]<br />
<br />
\>\>\> a = [[[1,2],[3,4]],[[5,6],[7,8]]]<br />
\>\>\> flatten = lambda x: [y for l in x for y in flatten(l)] if type(x) is list else [x]<br />
\>\>\> flatten(a)<br />
[1,2,3,4,5,6,7,8]<br />

<br />

## Generator expressions

\>\>\> g = (x ** 2 for x in xrange(10))<br />
\>\>\> next(g)<br />
0<br />
\>\>\> next(g)<br />
1<br />
\>\>\> next(g)<br />
4<br />
\>\>\> next(g)<br />
9<br />
\>\>\> sum(x ** 3 for x in xrange(10))<br />
2025<br />
\>\>\> sum(x ** 3 for x in xrange(10) if x % 3 == 1)<br />
408<br />

<br />

## Dictionary comprehensions

\>\>\> m = {x:x ** 2 for x in range(5)}<br />
\>\>\> m<br />
{0: 0,1: 1, 2: 4, 3: 9, 4: 16}<br />
<br />
\>\>\> m = {x:'A' + str(x) for x in range(10)}<br />
\>\>\> m<br />
{0:'A0',1:'A1',2:'A2',3:'A3',4:'A4',5:'A5',6:'A6',7:'A7',8:'A8',9:'A9'}<br />

<br />

## Inverting a dictionary using a dictionary comprehension

\>\>\> m = {'a': 1,'b': 2, 'c': 3, 'd': 4}<br />
\>\>\> m<br />
{'d': 4, 'a': 1, 'b': 2, 'c': 3}<br />
\>\>\> {v:k for k,v in m.items()}<br />
{1: 'a', 2: 'b', 3: 'c', 4: 'd'}<br />

<br />

## Named tuples (collections.namedtuple)

\>\>\> Point = collections.namedtuple('Point', ['x','y'])<br />
\>\>\> p = Point(x=1.0, y=2.0)<br />
\>\>\> p<br />
Point(x=1.0, y=2.0)<br />
\>\>\> p.x<br />
1.0<br />
\>\>\> p.y<br />
2.0<br />

<br />

## Inheriting from named tuples

\>\>\> class Point(collections.namedtuple('PointBase',['x','y'])):<br />
\.\.\.  __ slots__ = ()<br />
\.\.\.  def __add__(self, other):<br />
\.\.\.    return Point(x=self.x + other.x, y=self.y + other.y)<br />
\.\.\.<br />
\>\>\> p = Point(x=1.0, y=2.0)<br />
\>\>\> q = Point(x=2.0, y=3.0)<br />
\>\>\> p + q<br />
Point(x=3.0, y=5.0)<br />

<br />

## Sets and set operations

\>\>\> A = {1,2,3,3}<br />
\>\>\> A<br />
set([1,2,3])<br />
\>\>\> B = {3,4,5,6,7}<br />
\>\>\> B<br />
set([3,4,5,6,7])<br />
\>\>\> A | B<br />
set([1,2,3,4,5,6,7])<br />
\>\>\> A & B<br />
set([3])<br />
\>\>\> A - B<br />
set([1,2])<br />
\>\>\> B - A<br />
set([4,5,6,7])<br />
\>\>\> A ^ B<br />
set([1,2,3,4,5,6])<br />
\>\>\> (A ^ B) == ((A - B) | (B - A))<br />
True<br />

<br />


