## How to Reverse List and Print without brackets and commas in Python

Lists are one kind of datatypes that is used to store various items in a single variable. Lists in   usually look like this :

 list=[1,2,3,4,5]

**Reverse a List**

There are multiple ways to reverse a list.
1. with reversed() function
2. with reverse() function
3. using slicing

The problem arises when we try to print it after done with reversing. The given example below will show you how you can print a reversed list without the brackets or commas of the original list.

###    **Reverse with reversed() function**

```The reversed() function returns an iterator that can access the elements in reverse order.``` 

```
List_1 = [1, 2, 4, 3, 5] 
a=reversed(List_1)
print(*a)
``` 
```
Output:
5 3 4 2 1
 ``` 
###    **Reverse with reverse() function**

``` The reverse() function won't return any value but will update the existing elements of the list.``` 

```
list_2=[4,5,6,7,8,9]
list_2.reverse()
print(*list_2, sep=" ")
``` 
```
Output:
9 8 7 6 5 4
 ``` 

```Without the separator, the answer is also the same.```
 

###    **Reverse using slice**

```In Python, variable[::-1] means, the elements of the list will be gone through starting from last and it will step backward one step at a time.``` 


```
list_3 = [3,4,5,6,7]
reversed_list = list_3[::-1]
print(*reversed_list)
``` 

```
Output
7 6 5 4 3
``` 



