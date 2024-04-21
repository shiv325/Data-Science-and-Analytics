# NumPy

NumPy is a general-purpose array-processing Python library which provides handy methods/functions for working n-dimensional arrays. NumPy is a short form for "Numerical Python".

__Features__ :-
- Provides various computing tools such as comprehensive mathematical functions, and linear algebra routines
- Provides both the flexibility of Python and the speed of well-optimized compiled C code
- Its easy-to-use syntax makes it highly accessible and productive for programmers from any background
- A powerful N-dimensional array object
- Sophisticated (broadcasting) functions
- Tools for integrating C/C++ and Fortran code
- Useful linear algebra, Fourier transform, and random number capabilities
- Efficient multi-dimensional container of generic data
- Arbitrary data types can be defined which allows NumPy to seamlessly and speedily integrate with a wide variety of databases

__Why NumPy?__

NumPy revolutionized the way we handle numerical data in Python. It is created to address the limitations of traditional Python lists when it comes to numerical computing. It is developed by Travis Olliphant in 2005.

- Provides a powerful array object that is both efficient and flexible.
- Its primary goal is to facilitate complex mathematical and scientific operations by introducing array-oriented computing capabilities.
- NumPy’s design allows for seamless integration with other scientific libraries, enabling faster execution of numerical tasks.
- Provides fast and efficient array operations of homogeneous data.
- Perform typical numerical calculations on multidimensional arrays along with some other sophisticated functions.
- Provides ease working with linear algebra and carrying out complex calculations like Matrix inversion, Fourier Transfer, etc.
- Supports vectorized operations such as element-wise addition, substraction, etc which is not the case with basic lists.

As a result, NumPy has become a cornerstone in the Python ecosystem, essential for data manipulation, machine learning, and scientific research.

## Installation of Numpy Using PIP
Open your command prompt or terminal and run the following command:

    pip install numpy

## Import NumPy Module

    import numpy as np

## Arrays in NumPy
NumPy&#x2019s main object is the homogeneous multidimensional array.

- It is a table of elements (usually numbers), all of the same type, indexed by a tuple of positive integers.
- In NumPy, dimensions are called axes. The number of axes is rank.
- NumPy&#x2019s array class is called ndarray. It is also known by the alias array.

Example: We are creating a two-dimensional array that has the rank of 2 as it has 2 axes. The first axis(dimension) is of length 2, i.e., the number of rows, and the second axis(dimension) is of length 3, i.e., the number of columns. The overall shape of the array can be represented as (2, 3).

	import numpy as np 
	
	# Creating array object 
	arr = np.array( [[ 1, 2, 3], 
			 [ 4, 2, 5]] ) 
	
	# Printing type of arr object 
	print("Array is of type: ", type(arr)) 
	
	# Printing array dimensions (axes) 
	print("No. of dimensions: ", arr.ndim) 
	
	# Printing shape of array 
	print("Shape of array: ", arr.shape) 
	
	# Printing size (total number of elements) of array 
	print("Size of array: ", arr.size) 
	
	# Printing type of elements in array 
	print("Array stores elements of type: ", arr.dtype)
 Output =>

	Array is of type:  <class 'numpy.ndarray'>
	No. of dimensions:  2
	Shape of array:  (2, 3)
	Size of array:  6
	Array stores elements of type:  int64

## NumPy Array Creation
1. From a regular Python list or tuple using the array() function. The type of the resulting array is deduced from the type of the elements in the sequences.

  -     # Creating array from list with type float
        np.array([[1, 2, 4], [5, 8, 7]], dtype = 'float')
     Output =>
     
        [[1. 2. 4.]
         [5. 8. 7.]]
     
  -     # Creating array from tuple
        np.array((1 , 3, 2))
     Output =>
    
        [1 3 2]
2. Often, the element is of an array is originally unknown, but its size is known. Hence, NumPy offers several functions to create arrays with initial placeholder content. These minimize the necessity of growing arrays, an expensive operation. For example: np.zeros, np.ones, np.full, np.empty, etc.

To create sequences of numbers, NumPy provides a function analogous to the range that returns arrays instead of lists.

   -     # Creating a 3X4 array with all zeros 
         np.zeros((3, 4))
     Output =>

         [[0. 0. 0. 0.]
          [0. 0. 0. 0.]
          [0. 0. 0. 0.]]

   -     # Create a constant value array of complex type 
         np.full((3, 3), 6, dtype = 'complex')
      Output =>

         [[6.+0.j 6.+0.j 6.+0.j]
          [6.+0.j 6.+0.j 6.+0.j]
          [6.+0.j 6.+0.j 6.+0.j]]
    
   -     # Create an array with random values 
         e = np.random.random((2, 2))
      Output =>
    
         [[0.15471821 0.47506745]
          [0.03637972 0.15772238]]

3. __arange__ :- This function returns evenly spaced values within a given interval. Step size is specified.

       # Create a sequence of integers from 0 to 30 with steps of 5
       np.arange(0, 30, 5)
   Output =>

       [ 0  5 10 15 20 25]

4. __linspace__ :- It returns evenly spaced values within a given interval.

       # Create a sequence of 10 values in range 0 to 5 
       np.linspace(0, 5, 10)
   Output =>
     
       [0.         0.55555556 1.11111111 1.66666667 2.22222222 2.77777778 3.33333333 3.88888889 4.44444444 5.        ]

6. __Reshaping Array__ :- We can use reshape method to reshape an array. The original size of the array remains unchanged.

       # Reshaping 3X4 array to 2X2X3 array 
       arr = np.array([[1, 2, 3, 4], 
		               [5, 2, 4, 2], 
		               [1, 2, 0, 1]]) 

       newarr = arr.reshape(2, 2, 3) 
       print ("Original array:\n", arr) 
       print("---------------") 
       print ("Reshaped array:\n", newarr)
   Output =>
     
       Original array:
       [[1 2 3 4]
        [5 2 4 2]
        [1 2 0 1]]
       ---------------
       Reshaped array:
       [[[1 2 3]
         [4 5 2]]
        [[4 2 1]
         [2 0 1]]]

7. __Flatten Array__: We can use flatten method to get a copy of the array collapsed into one dimension. It accepts order argument. The default value is &#x2018C&#x2019 (for row-major order). Use &#x2018F&#x2019 for column-major order.

       # Flatten array 
       arr = np.array([[1, 2, 3], [4, 5, 6]]) 
       flat_arr = arr.flatten() 

       print ("Original array:\n", arr) 
       print ("Flattened array:\n", flat_arr)
   Output =>

       Original array:
       [[1 2 3]
        [4 5 6]]
       Flattened array:
       [1 2 3 4 5 6]

> *Note* : The type of array can be explicitly defined while creating the array.

## NumPy Array Indexing

1. __Slicing__ :- Just like lists in Python, NumPy arrays can be sliced. As arrays can be multidimensional, you need to specify a slice for each dimension of the array.
2. __Integer Array Indexing__ :- In this method, lists are passed for indexing for each dimension. One-to-one mapping of corresponding elements is done to construct a new arbitrary array.
3. __Boolean Array Indexing__ :- This method is used when we want to pick elements from the array which satisfy some condition.

       # Python program to demonstrate indexing in numpy 
       import numpy as np 
  
       # An exemplar array 
       arr = np.array([[-1, 2, 0, 4], 
   		       	[4, -0.5, 6, 0], 
                       [2.6, 0, 7, 8], 
                       [3, -7, 4, 2.0]]) 
  
       # Slicing array 
       temp = arr[:2, ::2] 
       print ("Array with first 2 rows and alternate columns(0 and 2):\n", temp)
  
       # Integer array indexing example 
       temp = arr[[0, 1, 2, 3], [3, 2, 1, 0]]
       print ("\nElements at indices (0, 3), (1, 2), (2, 1), (3, 0):\n", temp) 
  
       # Boolean array indexing example 
       cond = arr > 0 # cond is a boolean array 
       temp = arr[cond] 
       print ("\nElements greater than 0:\n", temp)
   Output =>

       Array with first 2 rows and alternatecolumns(0 and 2):
       [[-1.  0.]
        [ 4.  6.]]

       Elements at indices (0, 3), (1, 2), (2, 1),(3, 0):
       [ 4.  6.  0.  3.]

       Elements greater than 0:
       [ 2.   4.   4.   6.   2.6  7.   8.   3.   4.   2. ]

## NumPy Basic Operations
Vectorization is the ability of NumPy by which we can perform operations on entire arrays rather than on a single element.
- __Operations on a Single NumPy Array__ :- We can use overloaded arithmetic operators to do element-wise operations on the array to create a new array. In the case of +=, -=, *= operators, the existing array is modified.

      # Python program to demonstrate basic operations on single array 
      import numpy as np 

      a = np.array([1, 2, 5, 3]) 

      # Add 1 to every element 
      print ("Adding 1 to every element:", a+1) 

      # Subtract 3 from each element 
      print ("Subtracting 3 from each element:", a-3) 

      # Multiply each element by 10 
      print ("Multiplying each element by 10:", a*10) 

      # Square each element 
      print ("Squaring each element:", a**2) 

      # Modify existing array 
      a *= 2
      print ("Doubled each element of original array:", a) 

      # Transpose of array 
      a = np.array([[1, 2, 3],
                    [3, 4, 5],
                    [9, 6, 0]]) 

      print ("\nOriginal array:\n", a) 
      print ("Transpose of array:\n", a.T)
  Output =>

      Adding 1 to every element: [2 3 6 4]
      Subtracting 3 from each element: [-2 -1  2  0]
      Multiplying each element by 10: [10 20 50 30]
      Squaring each element: [ 1  4 25  9]
      Doubled each element of original array: [ 2  4 10  6]

      Original array:
      [[1 2 3]
       [3 4 5]
       [9 6 0]]
      Transpose of array:
      [[1 3 9]
       [2 4 6]
       [3 5 0]]

- __NumPy – Unary Operators__ :- Many unary operations are provided as a method of ndarray class. This includes sum, min, max, etc. These functions can also be applied row-wise or column-wise by setting an axis parameter.

      # Python program to demonstrate unary operators in numpy
      import numpy as np
  
      arr = np.array([[1, 5, 6], 
                      [4, 7, 2], 
                      [3, 1, 9]]) 
  
      # Maximum element of array 
      print ("Largest element is:", arr.max()) 
      print ("Row-wise maximum elements:", arr.max(axis = 1)) 
  
      # Minimum element of array 
      print ("Column-wise minimum elements:", arr.min(axis = 0)) 
  
      # Sum of array elements 
      print ("Sum of all array elements:", arr.sum()) 
  
      # Cumulative sum along each row 
      print ("Cumulative sum along each row:\n", arr.cumsum(axis = 1))
  Output =>

      Largest element is: 9
      Row-wise maximum elements: [6 7 9]
      Column-wise minimum elements: [1 1 2]
      Sum of all array elements: 38
      Cumulative sum along each row:
      [[ 1  6 12]
       [ 4 11 13]
       [ 3  4 13]]
  
- __NumPy – Binary Operators__ :- These operations apply to the array elementwise and a new array is created. You can use all basic arithmetic operators like +, -, /,  etc. In the case of +=, -=, = operators, the existing array is modified.

      # Python program to demonstrate binary operators in Numpy 
      import numpy as np 

      a = np.array([[1, 2], 
                    [3, 4]]) 
      b = np.array([[4, 3], 
                    [2, 1]]) 

      # Add arrays 
      print ("Array sum:\n", a + b) 

      # Multiply arrays (elementwise multiplication) 
      print ("Array multiplication:\n", a*b) 

      # Matrix multiplication 
      print ("Matrix multiplication:\n", a.dot(b))
  Output =>

      Array sum:
      [[5 5]
       [5 5]]
      Array multiplication:
      [[4 6]
       [6 4]]
      Matrix multiplication:
      [[ 8  5]
       [20 13]]

> _Note_ : All the operations we did above using overloaded operators can be done using ufuncs like np.add, np.subtract, np.multiply, np.divide, np.sum, etc.

  - __Introduction to NumPy’s ufuncs__ :- NumPy provides familiar mathematical functions such as sin, cos, exp, etc. These functions also operate elementwise on an array, producing an array as output.

        # Python program to demonstrate universal functions in numpy 
        import numpy as np 

        # Create an array of sine values 
        a = np.array([0, np.pi/2, np.pi]) 
        print ("Sine values of array elements:", np.sin(a)) 

        # Exponential values 
        a = np.array([0, 1, 2, 3]) 
        print ("Exponent of array elements:", np.exp(a)) 

        # Square root of array values 
        print ("Square root of array elements:", np.sqrt(a))
    Output =>
    
        Sine values of array elements: [  0.00000000e+00   1.00000000e+00   1.22464680e-16]
        Exponent of array elements: [  1.           2.71828183   7.3890561   20.08553692]
        Square root of array elements: [ 0.          1.          1.41421356  1.73205081]

- __NumPy Sorting Arrays__ :- There is a simple np.sort() method for sorting Python NumPy arrays.

      # Python program to demonstrate sorting in numpy 
      import numpy as np 

      a = np.array([[1, 4, 2], 
                    [3, 4, 6],
                    [0, -1, 5]]) 

      # Sorted array 
      print ("Array elements in sorted order:\n", np.sort(a, axis = None)) 

      # Sort array row-wise 
      print ("Row-wise sorted array:\n", np.sort(a, axis = 1)) 

      # Specify sort algorithm 
      print ("Column wise sort by applying merge-sort:\n", np.sort(a, axis = 0, kind = 'mergesort')) 

      # Example to show sorting of structured array 
      # Set alias names for dtypes 
      dtypes = [('name', 'S10'), ('grad_year', int), ('cgpa', float)] 

      # Values to be put in array 
      values = [('Hrithik', 2009, 8.5), ('Ajay', 2008, 8.7), 
                ('Pankaj', 2008, 7.9), ('Aakash', 2009, 9.0)] 
			
      # Creating array 
      arr = np.array(values, dtype = dtypes) 
      print ("\nArray sorted by names:\n", np.sort(arr, order = 'name')) 
			
      print ("Array sorted by graduation year and then cgpa:\n", np.sort(arr, order = ['grad_year', 'cgpa']))
  Output =>

      Array elements in sorted order:
      [-1  0  1  2  3  4  4  5  6]
      Row-wise sorted array:
      [[ 1  2  4]
       [ 3  4  6]
       [-1  0  5]]
      Column wise sort by applying merge-sort:
      [[ 0 -1  2]
       [ 1  4  5]
       [ 3  4  6]]

      Array sorted by names:
      [('Aakash', 2009, 9.0)
       ('Ajay', 2008, 8.7)
       ('Hrithik', 2009, 8.5)
       ('Pankaj', 2008, 7.9)]
      Array sorted by graduation year and then cgpa:
      [('Pankaj', 2008, 7.9)
       ('Ajay', 2008, 8.7)
       ('Hrithik', 2009, 8.5)
       ('Aakash', 2009, 9.0)]
