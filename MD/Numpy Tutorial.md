# Numpy
NumPy is a Python package which stands for ‘Numerical Python’. It is the core library for scientific computing, which contains a powerful n-dimensional array object

## Numpy Array
Numpy array is a powerful N-dimensional array object which is in the form of rows and columns.NumPy array can also be used as an efficient multi-dimensional container for generic data.
<img src="Img/MultiDimensional-Array.png"/>


```python
import numpy as np
```

### Single Dimentional Array


```python
single_dimentional = np.array([1,2,3,4,5,6])
print(single_dimentional)
```

    [1 2 3 4 5 6]
    

### Multi Dimentional Array


```python
multi_dimentional = np.array([[1,2,3],[4,5,6]])
print(multi_dimentional)
```

    [[1 2 3]
     [4 5 6]]
    


```python
print(single_dimentional[0])
```

    1
    


```python
print(multi_dimentional[0])
print(multi_dimentional[0][1])
```

    [1 2 3]
    2
    

## Numpy Array V/S List

We use python numpy array instead of a list because of the below three reasons:
1. Less Memory
2. Fast
3. Convenient

### Less Memory


```python
import sys

S = [i for i in range(1000)]
print(type(S),sys.getsizeof(S))

D = np.arange(1000)
print(type(D),sys.getsizeof(D))
```

    <class 'list'> 9024
    <class 'numpy.ndarray'> 4096
    

### Fast


```python
import time

size = 100

list1 = [i for i in range(size)]
list2 = [i for i in range(size)]

array1 = np.arange(size)
array2 = np.arange(size)

start= time.time()
result=[(x,y) for x,y in zip(list1,list2)]
print(type(list1),(time.time()-start)*1000)

start=time.time()
result= array1+array2
print(type(array1),(time.time()-start)*1000)
```

    <class 'list'> 0.0
    <class 'numpy.ndarray'> 0.0
    

## Numpy Operations 

### ndim
 To find the dimension of the array


```python
a = np.array([[1,2,3],[4,5,6]])
b = np.array([1,2,3])
print(a.ndim)
print(b.ndim)
```

    2
    1
    

### itemsize
 To calculate the byte size of each element


```python
a = np.array([(1,2,3)])
print(a.itemsize)
```

    4
    

### dtype
 To find the data type of the elements that are stored in an array.


```python
a = np.array([(1,2,3)])
print(a.dtype)
```

    int32
    

### size
  To find the size of the array.


```python
a = np.array([(1,2,3,4,5,6)])
print(a.size)
```

    6
    

### shape
To find the shape of an array


```python
a = np.array([(1,2,3,4,5,6)])
print(a.shape)
```

    (1, 6)
    

### reshape
Reshape is when you change the number of rows and columns which gives a new view to an object.
<img src="Img/Reshape.jpg"/>


```python
a = np.array([(8,9,10),(11,12,13)])
print("Array :",a)
print("Shape :",a.shape)
a=a.reshape(3,2)
print("After Reshaping",a)
```

    Array : [[ 8  9 10]
     [11 12 13]]
    Shape : (2, 3)
    After Reshaping [[ 8  9]
     [10 11]
     [12 13]]
    

### slicing


```python
a=np.array([(1,2,3,4),(3,4,5,6),(7,8,9,10)])
print(a[0,2])
```

    3
    


```python
print(a[0:,2])
```

    [3 5 9]
    


```python
print(a[0:2,1])
```

    [2 4]
    

### min


```python
print(a.min())
```

    1
    

### max


```python
print(a.max())
```

    10
    

### sum


```python
print(a.sum())
```

    62
    

<img src="https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/06/array-300x245.png"/>


```python
a = np.array([[8,9],[10,11],[12,13]])
print("Axis 0 :",a.sum(axis=0))
print("Axis 1 :",a.sum(axis=1))
```

    Axis 0 : [30 33]
    Axis 1 : [17 21 25]
    

### Array Arithmatic Operations

#### Addition


```python
x= np.array([(1,2,3),(3,4,5)])
y= np.array([(1,2,3),(3,4,5)])
print(x+y)
```

    [[ 2  4  6]
     [ 6  8 10]]
    

#### Subraction


```python
print(x-y)
```

    [[0 0 0]
     [0 0 0]]
    

#### Multiplication


```python
print(x*y)
```

    [[ 1  4  9]
     [ 9 16 25]]
    

#### Division


```python
print(x/y)
```

    [[1. 1. 1.]
     [1. 1. 1.]]
    


```python
print(x//y)
```

    [[1 1 1]
     [1 1 1]]
    

#### Horizontal and Vertical Stacking


```python
print(np.vstack((x,y)))
```

    [[1 2 3]
     [3 4 5]
     [1 2 3]
     [3 4 5]]
    


```python
print(np.hstack((x,y)))
```

    [[1 2 3 1 2 3]
     [3 4 5 3 4 5]]
    

#### ravel


```python
print(x.ravel())
```

    [1 2 3 3 4 5]
    

## Speacial Functions

Some of the speacial Functions of Numpy are
1. np.pi
2. np.sin(X)
3. np.tan(x)
4. np.exp(x) and etc...,
