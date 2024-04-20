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

#### __*Note*__: The type of array can be explicitly defined while creating the array.
