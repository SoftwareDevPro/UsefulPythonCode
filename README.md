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



