## Generate binary, hexadecimal, octal from decimal in Python 
Part 1

**Decimal:** Decimals numbers are used widely which represents (0-9) numbers in the number system. Its base is 10. 

**Binary:** Binary is used for machines or computers as they only understand 0 or 1. Its base is 2.

**Octal and Hexa:** Octal and hexadecimal numbers are the group representation of binary numbers. If we group 3 binary digits, it represents one octal value and if we group 4 binary digits, it represents one hexadecimal value. For octal and hexadecimal values it's easier to understand binary symbols. octal's base is 8 and the hexadecimal number system's base is 16.

**What is Base?**

In a number system, the base represents how many unique digits a certain number system can have. If any number's base is 2, it means it has only two unique digits.

Today I will show you in my blog, how to convert from decimal to other number systems using python's built-in function.

**Conversion with python** 


```The built-in functions in python we will be using are : bin(),hex(),oct().These functions only takes decimal integer number and will return a string. ``` 

**Decimal to Binary**
```
print("Enter decimal input:")
dec= int(input())  
result_bin=bin(dec).replace("0b", "")  
print("Binary:")
print(result_bin)
``` 

```
Output:
Enter decimal input:

120

Binary:
1111000
``` 
**Decimal to Hexadecimal**
```
print("Enter decimal input:")
dec= int(input())  
result_hexa=hex(n).replace("0x", "")
print("\nHexa:")
print(result_hexa)
``` 

```
Output:
Enter decimal input:

120

Hexa:
78
``` 

**Decimal to Octal**
```
print("Enter decimal input:")
dec= int(input())  
result_oct=oct(n).replace("0o", "")
print("\nOctal:")
print(result_oct)
``` 

```
Output:
Enter decimal input:

120

Octal:
170
``` 

```Here, the built-in functions generate some prefixes such as "0b" in binary, "0x" in Hexa, and "0o" in octal. We are using replace() function to remove them while printing.``` 

I will show you in my next blog how you can generate these number systems from decimal without a built-in function.

Resources:
 [https://www.programiz.com/python-programming/examples/conversion-binary-octal-hexadecimal](Link) 


