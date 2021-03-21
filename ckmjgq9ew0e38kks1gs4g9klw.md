## Dictionary operation according to user input in Python

Dictionaries in python store a collection of data like Lists. The difference between a dictionary and a list is you need to store the values with keys which will be separated by a (:)colon.

Example:

**dict ={'Language': 'Python', 'Version': '3.7.4', 'Paradigm': 'Multiparadigm'}**

Here, keys are -'Language', 'Version', 'Paradigm' and values are - 'Python', '3.7.4', 'Multiparadigm'

In this blog today we will see:
1. How to take input of a dictionary from the user 
2. The length of input will be given by the user
3. And we will run a search operation on that.

**1. Take Dictionary inputs **

```
print("Enter the number of values you want to take:")
x=int(input())
dict_str={}
print("Dictionary input:")
for y in range (1,x+1):
    str_in= input() #we are taking the keys and values together by separating them by a space
    key , value =str_in.split()
    dict_str[key]=value
print("\n")
print(dict_str)
``` 

```
Output:

Enter the number of values you want to take:

3
Dictionary input:

Language Python

Version 3.7.4

Paradigm Multiparadigm

{'Language': 'Python', 'Version': '3.7.4', 'Paradigm': 'Multiparadigm'}

``` 

**1. A search query on dictionary**

After the above lines of python codes are executed add the below lines with them
```
print("\nEnter a key :")
query = input()
if query in dict_str:
    print(query +"="+dict_str[query])
elif query not in dict_str:
    print("Not found")
``` 

```
Output:
Enter a key:
Version
Version=3.7.4
``` 
```
Output:
Enter a key:
Type
Not found
``` 


The code above would run fine in the IDE but in order to run it in the python shell, you may need to execute the lines one by one or chunk by chunk in some places.   [Here](https://www.tutorialsteacher.com/python/python-interective-shell)  is a resource you can go through for better knowledge.





Reference:
[w3School](https://www.w3schools.com/python/python_dictionaries.asp) 
