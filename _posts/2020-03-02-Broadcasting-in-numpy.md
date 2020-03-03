# BROADCASTING in NUMPY
>**Broadcasting** describes how arithmetic works between arrays of different shapes. It can be a powerful feature, but one that can cause confusion, even for experienced users. The simplest example of broadcasting occurs when combining a scalar value with an array:

In [79]: arr = np.arange(5)

In [80]: arr 

Out[80]: array([0, 1, 2, 3, 4])

In [81]: arr * 4 

Out[81]: array([ 0,  4,  8, 12, 16]) 

Here we say that the scalar value 4 has been broadcast to all of the other elements in the multiplication operation. For example, we can demean each column of an array by subtracting the column means. In this case, it is very simple:

In [82]: arr = np.random.randn(4, 3)

In [83]: arr.mean(0)  

Out[83]: array([-0.3928, -0.3824, -0.8768])

In [84]: demeaned = arr - arr.mean(0)

In [85]: demeaned 

Out[85]: array([[ 0.3937,  1.7263,  0.1633],
                [-0.4384, -1.9878, -0.9839],
                [-0.468 ,  0.9426, -0.3891],
                [ 0.5126, -0.6811,  1.2097]])

In [86]: demeaned.mean(0) 

Out[86]: array([-0.,  0., -0.]) 

See Figure for an illustration of this operation. Demeaning the rows as a broadcast operation requires a bit more care. Fortunately, broadcasting potentially lower dimensional values across any dimension of an array (like subtracting the row means from each column of a two-dimensional array) is possible as long as you follow the rules. 

