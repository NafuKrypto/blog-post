## Python : Rename all filenames of a directory into lowercase

Going through files one by one and renaming them seems easy and doable. But this simple   task can become a nightmare when you need to do it on a bulk amount of files (imagine doing it on 50 files or 100 or more ) . Python scripts come really handy to solve tasks like this.

**Pre-requisite :**
1. Python 
2. some files in a directory

<iframe width="560" height="315" src="https://www.youtube.com/embed/5fclTlZLpTA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

I want to rename the files of the directory named **project**. The files in that directory are like below in the beginning:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628348877586/O99Tz6zr_m.png)
 
So here are the steps :

## start coding
 > I opened the directory named **"project"** and typed cmd and clicked enter on the address bar.  Then write the code given below and executed it .  

```
import os
before= os.listdir()

for file in os.listdir():
 
        os.rename(file, file.lower())  
``` 
> In order to check the files before and after version of renaming , execute the 2nd part of the code given here :


```

after = os.listdir()

print("File converted to lowercase")
for file1, file2 in zip(before, after):
    print(file1, " converted to ", file2)
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628350713081/f9uMXbrdg.png)

## Output files :


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628350864319/pd8PW6RfH.png)

> If you don't want to rename certain types of files, add an if clause before executing the os.rename() line like this :


```
if not file.endswith(".txt"):  
        os.rename(file, file.lower())
``` 
**Resources :**
https://pythonprogramming.altervista.org/rename-all-files-in-a-directory-with-python/