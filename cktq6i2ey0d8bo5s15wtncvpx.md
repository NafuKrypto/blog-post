## Animated QR code Generator with Python and segno

### Table of Contents
1.  Context  
2. Pre-requisite
3. Modules you need to install 
4. Start coding
5. Output 
6. Reference
***
<iframe width="800" height="400" src="https://www.youtube.com/embed/_EKqvroqU5k" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Context
QR code contains data in a machine readable form. You can represent almost any form of data into a QR code **for example :** text , contact information , urls , image , sms , number , gif , pdf , wifi joining info etc.

But the black and white QR code is a little bit boring. We can always custom our QR code in Python easily. Adding an animation on it would be really fun and an out of the box concept.
***
## Pre-requisite
1. Python installed.
2. Knowledge on how to work with command prompt.
3. A gif file to work with (just download it from google).
***

## Modules you need to install
*    **Install segno :** </br>
 I am guessing you have already installed python. So in this step we need to install segno in our environment . Run the below command on your command prompt.</br>

>``` To install segno from PyPi :```

  
>```
 $  pip install segno
``` 
>**OR  **
                                
>``` from conda-forge```

  
>```
$ conda install -c conda-forge segno
``` 

* **Install  qrcode-artistic plug-in:** </br>
  We will use this plugin to create animated QR codes. You can also use this plugin to create a static QR code with a background image.


>```To use the plug-in ,run in your promt``` 

>```
 $ pip install qrcode-artistic
``` 

*  **Install  Pillow (PIL):** </br>
PIL is a python imaging library and segno plugin converts the QR code into PIL image or into a QR code with image background.

>```
 $ pip install pillow
``` 

***

## Start coding

* **Input** </br>
>Input Text To convert in QR Code : **Codengocool** </br>
>Input GIF To add in QR Code :
>![pubg.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1631620064866/F6OvSrlqV.gif)
>```This is the gif with which I want to generate my QR code. This file will go as input file. ``` 

*  **Code** </br>
>First open your python command prompt from your address bar where you have stored your input file. 
>Add the below lines :
>```
  import segno
  qr_code=segno.make("Codengocool",error="h")
  qr_code.to_artistic(background="pubg.gif",target="pubg1.gif",scale=8)
``` 
>``` segno.make() file takes the input text or url or any other input to genrate that into a QR  ``` 
>```The name of my input file is pubg. So  background="your_file_name.gif" and target="out_file_name.gif". And scale="the output image's bit depth" ``` 

***

##  Output

After executing the third line of code , the output file will generate. Here is the one that the above code generated:

![pubg1.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1631620045719/KW5b0O_Qa.gif)

***

## Reference
1.   [segno](https://pypi.org/project/segno/) 
2.  [Gif taken from this link](https://www.google.com/url?sa=i&url=https%3A%2F%2Ftenor.com%2Fsearch%2Fpubg-gifs&psig=AOvVaw34rbTZu6SN-QpyuAb2sW4H&ust=1631706148345000&source=images&cd=vfe&ved=0CAwQjhxqFwoTCNDwmp2x_vICFQAAAAAdAAAAABAD) 
3.  [qr-artistic](https://pypi.org/project/qrcode-artistic/ )
4.  [Artistic QR Code](https://segno.readthedocs.io/en/latest/artistic-qrcodes.html )