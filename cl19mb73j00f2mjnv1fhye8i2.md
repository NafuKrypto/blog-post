## Build Your Own Voice Recorder and Audio Player in Python

Building your own voice recorder can give you a lot of advantages. You can custom your generated audio clips as per what channel, subtype, frequency is needed for the audio. When we are working with raw data in Machine Learning, we may need to customize the data for training purposes. In that case, this piece can help you to teach how you can manipulate the audio files. 

Also, it could be a fun project for you if you are a beginner or trying to grow with python. 

In this blog, we will learn how we can record our own voice, save it in a usable format and play it with Python.

<iframe width="700" height="315" src="https://www.youtube.com/embed/43LWxq9ja2g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Step 1:  Set Up Environments
- **Install a Python version** (3.7 version is preferable, other versions are also ok ) and download a suitable IDE.
- **Install Libraries **

>``` Usually, sounddevice  module provides bindings for the PortAudio library and a few convenience functions to play and record NumPy arrays containing audio signals.``` 

```
pip install sounddevice
``` 

>```we will use scipy module to write a NumPy array as a WAV file.``` 

```
pip install scipy
``` 

>```Here we will use wavio.write  to write  a numpy array to a WAV file, optionally using a specified sample width.``` 

```
pip install wavio
``` 
>```We will read our .wav file using soundfile module. In some Python version released after 3.7 does not have any soundfile module. In that case, you can use pysoundfile module or try working on 3.7 version.``` 

```
pip install SoundFile
``` 

>```colorama module is just for coloring our text on the console.``` 

```
pip install colorama
``` 
### Step 2: Import Libraries
 
```
import sounddevice as sd
from scipy.io.wavfile import write
import wavio as wv
import soundfile as sf
from colorama import init, Fore, Back, Style
``` 
### Step 3: Set up the duration of recording and frequency

We are setting our frequency at 44100 Hz which is the sample rate of the recording. You can also set the frequency at 48000.

The duration variable means after starting the recorder it will record for 3s. If you want to record more than 3s or less, you just have to set the duration as you want. 

```
# Sampling frequency
freq = 44100

# Recording duration
duration = 3
``` 
### Step 4: Set User Choice
The input () function is displaying a prompt and asks for the user's choice to continue. Here, we are using ```Style.BRIGHT+ Fore.GREEN + "\nSpeak Now..."```  to change ```"Speak Now "```  color into Green on the console. Instead of using ```print(Style.BRIGHT+ Fore.GREEN + "\nSpeak Now...") ``` you can also just use ```print("\nSpeak Now...")```. It will be same for the rest of the print function.

```
input("\nPRESS ENTER TO RECORD YOUR VOICE...")
print(Style.BRIGHT+ Fore.GREEN + "\nSpeak Now...")

``` 
### Step 5: Recording with given duration
Using ```sounddevice``` module to record voice data in the NumPy array. For that, we are using ```sd.rec()```. It is basically storing the recorded sound in NumPy array into the recording variable.

Here you can set ```channels =1 or channels =2```. The changing value will decide if the Numpy array should be 1D or 2D. So it kind of depends on your requirement.

```
# Start recorder with the given values
# of duration and sample frequency
recording = sd.rec(int(duration * freq),
        samplerate=freq, channels=1)

# Record audio for the given number of seconds
sd.wait()
``` 
### Step 6: Write file using the User name
After the recording is done, you can type your name or any name you want, and the file will be saved in your local storage in .wav format. 

If you don't need to ensure the subtype has to be``` PCM_16``` then you can comment out the 2 lines after ```wv.write()```.

```
#taking input of speakers name
print(Style.BRIGHT + Fore.GREEN +"\n\nEnter speaker's name : ")
input_label = input()
speaker_name=input_label+".wav"
wv.write(speaker_name, recording, freq, sampwidth=2)

data, samplerate = sf.read(speaker_name)
sf.write(speaker_name, data, samplerate, subtype='PCM_16')

print(Style.BRIGHT + Fore.GREEN +"\nDone.......")
``` 
### Step 7: Play the audio with user choice  
Again, ```input()``` will take the user's choice to continue to listen to the recorded voice.

```
input("\nPRESS ENTER TO PLAY VOICE ... ")
# Extract data and sampling rate from file
data, fs = sf.read(speaker_name, dtype='float32')
sd.play(data, fs)
status = sd.wait()  # Wait until file is done playing
``` 
### Step 8 :  Printing audio analysis
```sf.SoundFile()``` module opens a sound file. If a file is opened with mode 'r' (the default) or 'r+', no sample rate, channels or file format need to be given because the information is obtained from the file. We are accessing the information of the audio file with object ```ob```
```
ob = sf.SoundFile(speaker_name)

print(Style.BRIGHT  + Fore.GREEN +"\n.....Audio Details.....")
print(Style.BRIGHT  + Fore.GREEN +'\nSample rate: {}'.format(ob.samplerate))
print(Style.BRIGHT  + Fore.GREEN +'Channels: {}'.format(ob.channels))
print(Style.BRIGHT  + Fore.GREEN +'Subtype: {}'.format(ob.subtype))
``` 
### Output 
After executing, the following output will be visible in the console. And in your working folder, you will see a .wav file is generated. In my case, it is ```barbie.wav``` and it contains 3-sec clip.

```
PRESS ENTER TO RECORD YOUR VOICE...

Speak Now...


Enter speaker's name :
barbie

Done.......

PRESS ENTER TO PLAY VOICE ...

.....Audio Details.....

Sample rate: 44100
Channels: 1
Subtype: PCM_16
``` 


### Full Code

```
import sounddevice as sd
from scipy.io.wavfile import write
import wavio as wv
import soundfile as sf
from colorama import init, Fore, Back, Style

# Sampling frequency

freq = 44100

# Recording duration

duration = 3
init(autoreset=True)

input("\nPRESS ENTER TO RECORD YOUR VOICE...")
print(Style.BRIGHT+ Fore.GREEN + "\nSpeak Now...")

# Start recorder with the given values of duration and sample frequency

recording = sd.rec(int(duration * freq),
        samplerate=freq, channels=1)

# Record audio for the given number of seconds

sd.wait()

#taking input of speakers name

print(Style.BRIGHT + Fore.GREEN +"\n\nEnter speaker's name : ")
input_label = input()
speaker_name=input_label+".wav"
wv.write(speaker_name, recording, freq, sampwidth=2)

data, samplerate = sf.read(speaker_name)
sf.write(speaker_name, data, samplerate, subtype='PCM_16')

print(Style.BRIGHT + Fore.GREEN +"\nDone.......")

input("\nPRESS ENTER TO PLAY VOICE ... ")

# Extract data and sampling rate from file

data, fs = sf.read(speaker_name, dtype='float32')
sd.play(data, fs)
status = sd.wait()  # Wait until file is done playing
ob = sf.SoundFile(speaker_name)

print(Style.BRIGHT  + Fore.GREEN +"\n.....Audio Details.....")
print(Style.BRIGHT  + Fore.GREEN +'\nSample rate: {}'.format(ob.samplerate))
print(Style.BRIGHT  + Fore.GREEN +'Channels: {}'.format(ob.channels))
print(Style.BRIGHT  + Fore.GREEN +'Subtype: {}'.format(ob.subtype))

``` 

### Reference 
1. [soundfile](https://pysoundfile.readthedocs.io/en/latest/)
2. [GeeksForGeeks](https://www.geeksforgeeks.org/create-a-voice-recorder-using-python/)
2. [codegrepper](https://www.codegrepper.com/code-examples/python/change+text+color+python)
3. [Pysoundfile](https://pysoundfile.readthedocs.io/en/latest/)
4. [Sounddevice](https://pypi.org/project/sounddevice/)


