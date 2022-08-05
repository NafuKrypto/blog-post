## Python Project : Text to HTML Converter

We will be converting text to HTML with **pytextile** module. The input text follows a certain syntax that generates HTML code with this module. 

Here, I will show how - **ordered list, unordered list, image link, bold text, & sign, normal text** works for the conversion using the module.  

### Pre-requisite:
+ Python Installed 
+ IDE or Shell ( I prefer Spyder)

<iframe width="560" height="315" src="https://www.youtube.com/embed/PJ18f7F9UF4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Step 1 :  Install Libraries
First , install [PyTextile](https://pypi.org/project/textile/) Module.

```
pip install textile
``` 
Python already comes with Tkinter. Still, if you think you are facing issues, you can install it manually.

```
pip install tk
``` 
### Step 2 :  Start coding by importing libraries
I have created a python file named text2html.py and imported the two libraries**(textile, and Tkinter)** I need. 

```
import textile
import tkinter as tk
``` 
### Step 3: Create an empty function and initialize the instance of Tk
After importing all libraries, now create a function and let it stay empty. We will come back to it later after we are done with our GUI implementation. I have named my function **convertToHtml()** in here.

We will also create the root of our application using the ```Tk``` class. This will act as our window for the application.

```
def convertToHtml():
    #fornow empty

root = tk.Tk()
``` 
### Step 4: Specify application
Now, we are going to specify the size of our window for our application.

```
root.geometry("250x170")
``` 
### Step 5: Create widgets and pack
We will need a Text widget, a button, and a Label. In this step, we will create them and pack them into the application window.
We will call our method ```convertToHtml()``` through the command parameter of the button widget.
```
  
# Create Text for input
T = tk.Text(root, height = 5, width = 52)
T.pack()
T.insert(tk.END,"""""" )

# Create button for result generation
b1 = tk.Button(root, text = "Submit", command=convertToHtml)
b1.pack() 

# Create label for result display
lbl = tk.Label(root, text = "")
lbl.pack() 
``` 
### Step 6: Add mainloop() method
Now, let's call the ```**mainloop() **``` method in our code so that our application runs.

```
root.mainloop()
``` 
### Step 7: Code to Convert Text to Html
 Now, go back to the beginning of the code and go to the method ```convertToHtml()``` .The main magic will happen here.

```T.get()``` takes the input from the user and stores it to ```inp``` variable. Then ```textile.textile()``` converts the text into HTML storing it in ```html```.

```lbl.config()``` holds the output result but we are also displaying it with the print() function. 

When button b1 is clicked , ```convertToHtml()``` method is called. 

```
 def convertToHtml():
    #fornow empty
    inp = T.get(1.0, "end-1c")
    html = textile.textile( inp )
    print("\nAfter converted to HTML: \n",html)
    lbl.config(text = "Converted Html : "+html) 
``` 
### Step 8 : Execute Your Code
After executing, You will see the following window opened up.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657686357994/i_ThunSLz.png align="left")
## Step 9 : Write on the console that opened 
You can just copy and paste the below part on the opened console's Text Input Box
```
Ordered List 
# One
# Two
# Three

Unordered List
* One
* Two
* Three
Image Link
"Freedom":https://images.unsplash.com/photo-1519834785169-98be25ec3f84?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NXx8c3VjY2Vzc3xlbnwwfHwwfHw%3D&w=1000&q=80

Normal Text 

Just Like that

Bold Text 

*This is bold*

Adding &

She &amp; Her

```
Then click Submit and some output will generate in both the console and in the IDE or shell. Copy the text generated as output from the environment. For the input above I have got output like below :

## Output
The output that is generated is our HTML syntax that can create an HTML page. 
```
<p>Ordered List
        <ol>
                <li>One</li>
                <li>Two</li>
                <li>Three</li>
        </ol></p>

        <p>Unordered List
        <ul>
                <li>One</li>
                <li>Two</li>
                <li>Three<br />
Image Link<br />
<a href="https://images.unsplash.com/photo-1519834785169-98be25ec3f84?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NXx8c3VjY2Vzc3xlbnwwfHwwfHw%3D&w=1000&q=80">Freedom</a></li>
        </ul></p>

        <p>Normal Text </p>

        <p>Just Like that</p>

        <p>Bold Text </p>

        <p><strong>This is bold</strong></p>

        <p>Adding &</p>

        <p>She &amp; Her</p>

```


### Step 9: HTML page test with the output
Create a .html file in any folder. In my case, I have created test.html and then paste the output in that file. Click save and open the file on your browser. The html page is you are looking it just got generated from your code which holds - ordered list , unordered list , Image Link , Normal text , Bold text and adding & .


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659423751222/Pmtv3mCTx.png align="left")

### Full Code:
```
import textile
import tkinter as tk

def covertToHtml():
    #fornowempty
    inp=T.get(1.0,"end-1c")
    html=textile.textile(inp)
    print("\nAfter converted to HTML: \n",html)
    lbl.config(text="Converted Html : "+html)

root=tk.Tk()
root.geometry("250x170")

# Create Text for input
T=tk.Text(root,height=5,width=52)
T.pack()
T.insert(tk.END,"""""")

# Create button for result generation
b1=tk.Button(root,text="Submit",command=covertToHtml)
b1.pack()

# Create label for result display
lbl=tk.Label(root,text="")
lbl.pack()

root.mainloop()

```
## Link 
1. [PyTextile](https://wiki.python.org/moin/PyTextile#CA-0b0cc4b248d24332f3a2465f8cd24c1550fc37f2_1) 
 
<a href="https://www.buymeacoffee.com/nafisaalamS" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 10px !important  ;width: 50px !important ;"></a>


 