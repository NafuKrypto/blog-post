## Calculate the execution time of your code in Python

Measuring execution time in code can give proper insights into coding performance. For this purpose,
we will use the time module from Python. The function we will be using is also called **time()**.
**time.time() **-> returns the time in seconds 

First, we will see, how long the for loop takes to execute and then use the same technique for function.

## Loop Execution Time
### Step 1 : Install module
If you have already installed Python, then there is no need to install the time module. It is part of Python's standard library.
### Step 2: Start Coding

- The **start_time** variable holds the initial time 
- The **end_time** holds the time when for loop ends 
- And the subtraction of these two values gives us the exact amount of time the for loop took to execute
- As the time.time() function returns the value in seconds, the result of the subtraction for this small code could be a very small value. That's why we are multiplying 1000 and converting it to ms.

```
import time
sum=0
start_time=time.time()
for i in range (10000):
    sum+=i

end_time=time.time()

print("Time required: ",(end_time-start_time)*1000, "ms")

``` 

```
Output:
Time required:  1.024484634399414 ms
``` 
## Function execution time
If you want to find out, your certain function's execution time on your code, then the following way can be helpful. 

The reason this time we are taking **start_time ** value before **sum=0** is we are calculating execution time for the whole function, not for some part of the function.
```
import time

def exec_time(n):
    start_time=time.time()
    sum=0
    for i in range (n):
        sum+=i
    end_time=time.time()
    return end_time-start_time

calc_time=exec_time(10000)*1000

print("Time required: ", calc_time , "ms")
``` 

```
Output :
Time required:  1.028299331665039 ms
``` 
## Reference :
1. [StackOverflow](https://stackoverflow.com/questions/42522650/cant-install-time-module)
2. [W3Resource](https://www.w3resource.com/python-exercises/python-basic-exercise-57.php)
