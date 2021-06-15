## Make your own Wikipedia in Bangla language with Python

There could be a lot of time where you had to access data from Wikipedia and parse it as necessary in your program. In Python, you can do it easily with a python library named **Wikipedia.** In this blog I will show you how can you get data from the wiki in Bangla language. If you can understand the code, you can access data in any language.

**What you must have?**

1. Python Installed.
2. Install Wikipedia library.  Run the command -

```
pip install wikipedia
``` 
3.Python Shell / IDE /IDLE (I prefer to work on Spyder)

 # Start coding 

1) After installing Wikipedia library , import it in your code.

```
import wikipedia 
``` 
2)Set language with wikipedia.set_lang(). You can set the language to English by replacing **"bn" to "en" or to any language.**

```
wikipedia.set_lang("bn")
``` 
3)Now, print the summary and pass the word that you want to know the details of .


```
print(wikipedia.summary("Space" ,sentences=1 ))

``` 


```
Output:
মহাকাশ বা মহাশূন্য বলতে পৃথিবীর বাইরে অবস্থিত এবং খ-বস্তুসমূহের মধ্যে প্রসারিত স্থানকে বোঝায়। মহাকাশ সম্পূর্ণরূপে ফাঁকা একটি শূন্যস্থান নয়। এটিতে খুবই কম ঘনত্বের কণা থাকে যাদের সিংহভাগই হাইড্রোজেন ও হিলিয়ামের প্লাজমা দিয়ে গঠিত। এছাড়াও মহাকাশে তড়িৎ-চুম্বকীয় বিকিরণ, চৌম্বক ক্ষেত্রসমূহ, নিউট্রিনো, মহাজাগতিক ধূলি ও মহাজাগতিক রশ্মিসমূহ বিদ্যমান। মহাকাশের ভূমিরেখা তাপমাত্রা ২.৭ kelvin (−২৭০.৪৫ °সে; −৪৫৪.৮১ °ফা), যা মহাবিস্ফোরণের পটভূমি বিকিরণ দ্বারা নির্ধারিত।  ছায়াপথসমূহের মধ্যবর্তী প্লাজমা মহাবিশ্বের প্রায় অর্ধেক ব্যারিয়নজাত (সাধারণ) পদার্থ গঠন করেছে; এটির সংখ্যা ঘনত্ব  প্রতি ঘনমিটারে একটি হাইড্রোজেন পরমাণু অপেক্ষাও কম এবং এটির তাপমাত্রা বহু লক্ষ কোটি কেলভিন। পদার্থের স্থানীয় কেন্দ্রীভূত রূপগুলি ঘনীভূত হয়ে নক্ষত্র ও ছায়াপথগুলি গঠন করেছে। গবেষণায় দেখা গেছে যে বেশিরভাগ ছায়াপথের ৯০% ভর একটি অজ্ঞাত রূপে বিদ্যমান, যার নাম দেওয়া হয়েছে তমোপদার্থ; এটি অন্যান্য পদার্থের সাথে তড়িৎ-চুম্বকীয় বলসমূহের সাহায্যে নয়, কিন্তু মহাকর্ষীয় বলের মাধ্যমে আন্তঃক্রিয়া সম্পাদন করে। পর্যবেক্ষণ থেকে অনুমান করা হয় যে পর্যবেক্ষণসম্ভব মহাবিশ্বের ভর-শক্তির সিংহভাগই হল তমোশক্তি নামের একপ্রকার শূন্যস্থান শক্তি,  যার প্রকৃতি এখনও ভালমতো বোঝা যায়নি। মহাবিশ্বের আয়তনের বেশিরভাগই আন্তঃছায়াপথ স্থান দ্বারা গঠিত, কিন্তু ছায়াপথ ও নক্ষত্রব্যবস্থাগুলি নিজেরাও প্রায় সম্পূর্ণরূপে শূন্যস্থান দিয়েই গঠিত।

``` 
**Full Code:**

```
import wikipedia 
wikipedia.set_lang("bn")
print(wikipedia.summary("Space" ,sentences=1))
 
``` 

```Issues I faced : The function here  "wikipedia.summary("Space" ,sentences=1)" doesn't print 1 sentence or the number of sentences I want to print in Bangla. But if you set your language to "en" or English it works perfectly fine. If anyone knows what's going on here , please let me know in the comment section. ``` 


**More of My Articles:**

1)  [I coded a Python program to sing the BTS song "Butter"](https://codengocool.hashnode.dev/i-coded-a-python-program-to-sing-the-bts-song-butter) 

2)  [bangla-text-to-bangla-speech-conversion-with-python](https://codengocool.hashnode.dev/bangla-text-to-bangla-speech-conversion-with-python) 

3) [dictionary-operation-according-to-user-input-in-python](https://codengocool.hashnode.dev/dictionary-operation-according-to-user-input-in-python) 

4) [python-play-an-audio-file-with-pygame](https://codengocool.hashnode.dev/python-play-an-audio-file-with-pygame) 

**Reference:**

 [wikipedia 1.4.0](https://pypi.org/project/wikipedia/) 
