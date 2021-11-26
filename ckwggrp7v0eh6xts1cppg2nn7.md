## Replace for loops with Vectorization in Python


### Overview 
When it comes to execute code repeatedly , we tend to use for-loop. A bunch of times when we need  to use nested loops , our code could run slower. In deep learning, if you are thinking about iterating through a huge dataset with for loop , that could cost a huge amount of time. Thus, for-loop can be a huge bottleneck sometimes and can result in running a code for ages.

Now , the question arises what could be the easier replacement then? The answer is vectorization and we should check it by comparing them with real examples.
<iframe width="560" height="315" src="https://www.youtube.com/embed/WcBbM45I-vQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
***
### Things that will be covered 
2. What is Vectorization?
3. for-loop vs vectorization
4. Why NumPy(vectorization process) is faster than loop ?
5. details of functions/mudules used in the code
***
### What is Vectorization?
Vectorization is a method to make code efficient without for-loops. In deep learning , code gets much faster if we vectorized our code. And to achieve that goal , we use functions defined by various modules. We perform operations with these functions to reduce the execution and runtime.
***
###  Start coding 
>We will create two variables with each having a one-dimensional array.

 ```
import time
import numpy as np

#randomly generating 1000000 digits and storing them in one dimensional array array1
array1=np.random.rand(1000000) 
#randomly generating 1000000 digits and storing them in one dimensional array array2
array2=np.random.rand(1000000) 
``` 
>### For-loop Example:
  Now with array1 and array2's values , we will create a third array calls array3 which will be a 2-dimensional array. The third array will store the product of array1 and array2. 

```
array3=0
tic=time.time()           #counting initial time
for i in range(1000000):
 array3+=array1[i]*array2[i]
toc = time.time()          #counting final time
print("array3: "+str(array3))
#for_loop execution time=final time -initial time
print("\nFor loop exec time :"+str(1000*(toc-tic))+" ms") 

``` 
>### Output

``` 
array3: 250177.2599928903  

For loop exec time :650.6094932556152 ms

``` 

>### Vectorization Example:  
Let's try the same example from before by replacing the loop and checking the execution time.

```
array3=0
tic=time.time() #counting initial time
#replacing for-loop with np.dot 
array3=np.dot(array1,array2)
toc = time.time() #counting final time
print("array3: "+str(array3))
#vectorized execution time=final time -initial time
print("\nVectorized exec time :"+str(1000*(toc-tic))+" ms")
``` 
>### Output

```
array3: 250177.25999289122

Vectorized exec time :4.674673080444336 ms
```
###  Note

```Here , from these solutions , we can see that , for-loop takes (650.61/4.67)=139.32 times more to execute than vectorizations.```

###  Why NumPy(vectorization process) is faster than loop ?
NumPy uses the parallelism technique to work faster with arrays. So it can run operations on them at once. Also, NumPy arrays are homogeneous and only contain objects of one type. In addition , vectorized operations in NumPy are optimized with C.

On the other hand, for-loop can't work parallelly instead it iterates every element one by one. In Python, there is no way to predict the datatype beforehand in a for loop as stored data can be heterogeneous if it's a list. So every time iterating, the interpreter has to figure out the datatype. As a result, the loop is slower in Python.

###  Functions and libraries used 

-  np.random.rand(): creates an array of specified shape and fills it with random values.

-  time.time() : returns the time as a floating-point number expressed in seconds since the epoch, in UTC

- np.dot(): returns product value of two arrays

###  Full-Code :

``` 
import time
import numpy as np

#randomly generating 1000000 digits and storing them in one dimensional array array1
array1=np.random.rand(1000000) 
#randomly generating 1000000 digits and storing them in one dimensional array array2
array2=np.random.rand(1000000) 
array3=0
tic=time.time()           #counting initial time
for i in range(1000000):
 array3+=array1[i]*array2[i]
toc = time.time()          #counting final time
print("array3: "+str(array3))
#for_loop execution time=final time -initial time
print("\nFor loop exec time :"+str(1000*(toc-tic))+" ms") 
array3=0
tic=time.time() #counting initial time
#replacing for-loop with np.dot() 
array3=np.dot(array1,array2)
toc = time.time() #counting final time
print("array3: "+str(array3))
#vectorized execution time=final time -initial time
print("\nVectorized exec time :"+str(1000*(toc-tic))+" ms")

``` 

### Reference
1.  [numpy](https://www.reddit.com/r/Python/comments/jorq7/how_numpy_is_faster_in_computation/) 
2. [numpy](https://www.nature.com/articles/s41586-020-2649-2/figures/1) 
3. [numpy.dot](https://numpy.org/doc/stable/reference/generated/numpy.dot.html)
 




