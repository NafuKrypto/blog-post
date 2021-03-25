## Find Phone-number from text in Python

If you know a phone number pattern, you can easily find that from any text using python.
In Bangladesh, the pattern of a phone number is: +880-operator code-8 digit number

The total length of the phone number is 14 digits. So we will take text from the input which have a length of 14th and check if that's a number or not through a function.


```1.  Writing code for function **isPhonenumber() **and giving all the pattern checking attributes of the phone number and to return a boolean value accordingly.``` 


```
def isPhonenumber(text):
    if len(text) != 14:
        return False
    
    for i in range(0,1):
        if text[i] != "+":
            return False
        
    for i in range(1,3):
        if text[i]!="8":
            return False
        
    if text[3]!="0":
        return False
    
    if not text[4:14].isnumeric():
        return False
        
    return True
``` 


```2. Now, let's write the code to take input and pass that input as a chunk of 14th length through the function isPhonenumber().``` 


```
input_string = "Oporajita is a fine girl whose phone number is :+8801945273462.You can also call her on +8801626378890"
length=len(input_string)
for i in range(length):
    check = input_string[i:i+14]
    if isPhonenumber(check):
        print("Phone number is found: " +check)
print("Phone number checking is done")
``` 


```
Output:
Phone number is found: +8801945273462
Phone number is found: +8801626378890
Phone number checking is done
``` 
Resource: 

**From the book Automate the boring stuff with Python**
 