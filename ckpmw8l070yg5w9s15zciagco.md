## Python: play an audio file with pygame

Some days ago , I was working on a project where I needed to play an audio file that my program generated. So in order to that, I used a library named pygame. It helped me to play the audio file.

**What is Pygame?**

Pygame module is used in the video game development. It supports to program games and multimedia applications in Python. 

**Environment Prep: **


1. Install  [Python](https://www.python.org/downloads/) . It is better to install a version 3.7.7 or greater than that.

2. Install Pygame. Run the commands written below on your command prompt.

```
pip install pygame
``` 

```In our code, we will use the mixer module from pygame. ``` 

**Solution step by step :**

My input file is output.mp3. Keep the .mp3 file and your .py file under the same folder.

**Input:**
<iframe width="500" height="45" src="https://www.youtube.com/embed/Ku47289Mvao" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen ></iframe>

1) First we will load the external library.

```
from pygame import mixer 

``` 
2) Then we will initialize the mixer module. In order to do that, we will use **mixer.init()**

```
mixer.init()

``` 
3) Now load the audio file that you want to play. We will use mixer.music.load("audioname.mp3).

```
mixer.music.load('output.mp3')

```
4) Play the audio with mixer.music.play()


```
mixer.music.play()
``` 
Full code Here:

```
from pygame import mixer  

mixer.init()
mixer.music.load('output.mp3')
mixer.music.play()
``` 

 
**Reference:**

1. https://www.pygame.org/wiki/about
2. https://pypi.org/project/pygame/
3. https://www.geeksforgeeks.org/python-playing-audio-file-in-pygame/
4. https://www.pygame.org/wiki/GettingStarted
5. https://www.pygame.org/docs/ref/mixer.html








