## Make a Simple Random Password Generator in Python

 ## Table of Content
 
  **  1. **   [Context](#Context)   
  **  2.**   [Algorithm](#Algorithm ) </br>
  **  3. **   [Pre-requisite](#Pre-requisite)   </br>
  **  4.**   [Functions and operation we will use](#Functions and operation we will use) </br>
  **  6.**   [Output](#Output) </br>
  **  7.**   [Full  Code Here](#Full  Code Here) </br>
 
<iframe width="560" height="315" src="https://www.youtube.com/embed/nWmOrBjm0JY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</br>
# Context
Our passwords keep our valuable accounts safe and secured. The more these passwords are unpredictable , the more our account is secured. In general , a most secured password needs at least one uppercase and one lowercase letter , one digit and one special character and the password length should be at least 8. 

In terms of creating a password , we always try to create one that we can easily remember. 
>**The National Cyber Security Centre (NCSC) said 15% of the population used pets' names, 14% use a family member's name, and 13% pick a notable date. And 6% of people are still using "password" as all - or a part - of their password.**
( [ source : BBC NEWS](https://www.bbc.com/news/technology-56680790) )

So , in generating a totally random and unpredictable password , an algorithm can be helpful. In this blog , I will write a code for generating a random password in Python.
 * * *
# Algorithm
 |step by step|
|-------------|
| ** Step 1 : **  Take a user input of password's length.  |
| **  Step 2 :** Substract 4 from the length and store the result in a variable.** rest_index= length-4**|
| **  Step 3 :**  To make sure your password have at least  one uppercase , one lowercase letter, one digit and one character , you need to keep 4 space in the index. That's why we substracted 4 in step 2.  Now randomly select one Uppercase , one Lowercase , one digit , one special character and store them in a variable. **password+=radom uppercase+random lowercase + random digit + random special character**|
| **  Step 4 :** Now we will shuffle the position of the strings in password so that the index of them become unpredictable as well. **password=shuffle the position of all the strings**|
| **  Step 5 :** Now for the rest of the strings , we will execute a loop starting from 0 to length-4 (as we have figured four letter first). **password=shuffle the position of all the strings**|
| **  Step 6 :** Now in that loop we will choose one string randomly and we will randomly select would that be a uppercase or lowercase or digit or special charecter . **temp = random (Uppercase/ Lowercase/digit/special charecter); if temp=uppercase then pasword+=random uppercase **|
| **  Step 7 :** Now you can print the password. **print(pasword)**|
 
* * *
# Pre-requisite:

1. Python installed
2. Ide or Idle or run on shell . (I prefer Spyder ide )
3. Basic concept of how to execute code 

# Functions and operation we will use 

### **random - module :**
This module implements pseudo-random number generators for various distributions.</br>
 
- 
**random.choice(seq) : ** Return a random element from the non-empty sequence seq. </br>

- 
 **random.sample(population, k, *, counts=None) : **Return a k length list of unique elements chosen from the population sequence or set. Used for random sampling without replacement. </br>
</br>
Source: [Here is link](https://docs.python.org/3/library/random.html#bookkeeping-functions) 
### **String operations :**
This module implements pseudo-random number generators for various distributions.</br>

- 
**string.ascii_lowercase :**
The lowercase letters 'abcdefghijklmnopqrstuvwxyz'. </br>

- 
**string.ascii_uppercase: **
The uppercase letters 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'. This value is not locale-dependent and will not change.</br>

- 
**string.digits:**
The string '0123456789'. </br>

- 
**string.punctuation:**
String of ASCII characters which are considered punctuation characters in the C locale: !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~. </br>
 Source: [Here is link](https://docs.python.org/3/library/string.html) 
* * *

## Start coding 

- Import random module and string module in your code.

>```
import random as rand
import string
``` 

- take user input of password's length and initialize password string as empty. Substract four from the original length and store it in rest_index. (we will fill up 4 index with 4 fixed string )

>```
print("Enter a length of password at least 8     :")
length=int(input())
password="" 
rest_index=length-4
``` 

- Randomly choose one uppercase and one  lowercase letter , one digit and one special charecter with string and random module. then concat all 4 of them with password variable.
- Later shuffle the position of the string  with rand.sample() function and use join function to join them as string and then store it in password variable. 

>```
password+=rand.choice(string.ascii_uppercase)+rand.choice(string.ascii_lowercase)+ rand.choice(string.digits)+rand.choice(string.punctuation)
password=  ''.join((rand.sample(password,len(password)))) 
``` 

- Make a list of choices in variable** mainChoice** where **"U" = uppercase letter; "L" = lowercase letter; "N" = digit; "S" = special charecter;**
- We will execute a loop from 0 to rest_index (Here rest_index=length-4) and figure out other random string.
-To do that , we will randomly choose from the mainChoice list one string and in our if-else condition we will execute according to that.

>```
mainChoice=["U","L","N","S"]          
for x in range(0,rest_index):
    temp=rand.choice(mainChoice)
    if(temp=="U"):
        password+=rand.choice(string.ascii_uppercase)  
    if(temp=="L"):
        password+=rand.choice(string.ascii_lowercase)      
    if(temp=="N"):
        password+= rand.choice(string.digits)     
    if(temp=="S"):
        password+=rand.choice(string.punctuation) 
``` 

- Now we can print the generated password

>```
print(password)
``` 

- Now run the code and you will see the output like below :

### Output
```
Enter a length of password at least 8     :

8
Your password is :  J?9k]k8&
``` 


You can now copy and paste it in anywhere you like. It's random and fully unpredictable.

# Full  Code Here:


```
import random as rand
import string

print("Enter a length of password at least 8     :")
length=int(input())
password="" 
rest_index=length-4

password+=rand.choice(string.ascii_uppercase)+rand.choice(string.ascii_lowercase)+ rand.choice(string.digits)+rand.choice(string.punctuation)
password=  ''.join((rand.sample(password,len(password)))) 
mainChoice=["U","L","N","S"]          
for x in range(0,rest_index):
    temp=rand.choice(mainChoice)
    
    if(temp=="U"):
        password+=rand.choice(string.ascii_uppercase)
        
    if(temp=="L"):
        password+=rand.choice(string.ascii_lowercase)
         
    if(temp=="N"):
        password+= rand.choice(string.digits)
        
    if(temp=="S"):
        password+=rand.choice(string.punctuation)
         
print("Your password is : ", password)
``` 
