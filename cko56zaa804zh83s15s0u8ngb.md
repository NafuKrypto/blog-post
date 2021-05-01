## Bangla Text to Bangla Speech Conversion with Python

There are a lot of ways that exist which can help to convert a text into a speech. I have recently work with gTTS python library to perform the task and so I will share it today in this blog.

**Pre-requisite:**

1. Need to install  [Python](https://www.python.org/downloads/)
2. Install  [Python IDE](https://learnpython.com/blog/how-to-install-python-spyder-ide/) 
3. Installed gTTS API

**How to install gTTS**

Normally to install gTTS all you have to do is write this one line in your terminal:

```
pip install gTTS
``` 
But when I was working with this, only installing this way didn't help me. The gTTS module wasn't working. The installation worked perfectly but while importing, it was throwing an error. So to avoid that,I have to add two more lines to my terminal :

```
pip install gTTS--upgrade

pip install gTTS-token --upgrade
``` 

**Conversion text to speech**

 1. After fulfilling the pre-requisite, open your python IDE. Import two modules named gtts and os in your code. 
```
from gtts import gTTS
import os
``` 
The gtts module will let you convert the text into audio. The os module will get the current working directory and save your audio file there.
    
2.Then add the text you want to convert and also add in which language you want to convert.
     
```
text="থাকবো নাকো বদ্ধ ঘরে"

language = 'bn'
``` 
3.Now pass the text and the language to convert it to audio through Google Translator. Also, save the output.

```
output = gTTS(text=text, lang=language,slow=False)

output.save("output.mp3")
``` 
 **Output**
<iframe width="500" height="45" src="https://www.youtube.com/embed/Ku47289Mvao" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen ></iframe>

The output above given will be saved in the directory where your python script is remaining.I couldn't share my mp3 file here. So I uploaded the output file in youtube.

**The full code is below:**

```
from gtts import gTTS
import os

text="থাকবো নাকো বদ্ধ ঘরে"

language = 'bn'

output = gTTS(text=text, lang=language,slow=False)

output.save("output.mp3")
``` 


Reference:

 [https://pypi.org/project/gTTS/](Link) 
 
[https://www.thepythoncode.com/article/convert-text-to-speech-in-python](Link) 
 







