## Make Simple QR code with Python

### Table of Contents
1.    Overview
2.   Pre-requisite
3.   Input
4.   Code
5.   Output
***
## Overview
A QR code consists of squares in a square grid on a background that stores information. The QR code is read by an imaging device and interprets the image into human accessible data. 

In python you can easily make a basic QR code generator which you can use later in your  projects. In this blog , we will see how we can make a very simple and basic QR code generator. We won't dive into any complex coding. So , we will take a simple text and convert it into a QR code.
***
##   Let's start

```To watch the video below, set 1080p quality in YouTube settings. Otherwise console looks a little blur.``` 

<iframe width="760" height="415" src="https://www.youtube.com/embed/TPB2EozIbz0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
+ ### **Pre-requisite**

 1. Python installed

 2. Install pure python qr code generator like below :

>```
pip install qrcode[pil]
``` 

+ ###  Input 
 "Codengocool is really cool" - this text will be our input in the QR code generator.

+ ### **Code**

>```
import qrcode
img=qrcode.make("Codengocool is really cool")
img.save("basic.png")
```
 
```In the make() method we parse the input which could be text or number or anything else that we want to convert in a QR code.``` 

```The save parameters saves the image into a supported image file for example : png, jpg, jpeg etc. To save in svg format follow  [this link](https://pypi.org/project/qrcode/).``` 

```Scan the QR code from output section to see for yourself the extracted result. ``` 


+ ### **Output**

![basic.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633163169461/y7v4lMuAv.png)

+ ### Reference
  1. [Wiki](https://en.wikipedia.org/wiki/QR_code#Standards) 
  2.  [qrcode](https://pypi.org/project/qrcode/) 

 