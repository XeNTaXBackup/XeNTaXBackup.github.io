## Post #1
- Username: ghostx2015
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-07-14T13:40:22+00:00
- Post Title: 300 Heroes Noesis Script (PC)

Noesis Script for 300 Heroes《300英雄》



prev.png (716.41 KiB) Viewed 962 times


Website: [http://300.jumpw.com/](http://300.jumpw.com/)
Download: [http://300.jumpw.com/download.html](http://300.jumpw.com/download.html)

```
#by chrrox
goto 0x32
get FILES long
for i = 0 < FILES
getdstring NAME 0x104
get OFFSET long
get ZSIZE long
get SIZE long
getdstring NULL 0x20
clog NAME OFFSET ZSIZE SIZE
next i

```

[fmt_300_Heroes_X.7z](https://xentaxbackup.github.io/file/16473_fmt_300_Heroes_X.7z)
## Post #2
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2019-07-15T10:17:45+00:00
- Post Title: 300 Heroes Noesis Script (PC)

I have mobile game "300 Battle Glamorous Heroes" by same developer jumpw.com.
I extracted the game and found on model folder .x2 and .pkm
Its possible to get the model?

Its example files
[https://sta.sh/01j36u1rx610](https://sta.sh/01j36u1rx610)
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-07-19T16:57:47+00:00
- Post Title: 300 Heroes Noesis Script (PC)

unknown.png (249.83 KiB) Viewed 866 times

I got the files decrypted the model format is different but it does not look hard I should be able to make a script for it tonight.
Character List
[https://pastebin.com/shZS9zXD](https://pastebin.com/shZS9zXD)
## Post #4
- Username: Mrscouter
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 22, 2012 4:41 am
- Post datetime: 2019-08-07T05:00:19+00:00
- Post Title: 300 Heroes Noesis Script (PC)

Do you know if the animations for the models are stored inside the character .x files or somewhere else? It seems to be the former but I can't tell for sure.
## Post #5
- Username: Seamoroar1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 24, 2018 12:17 am
- Post datetime: 2019-08-12T08:34:33+00:00
- Post Title: 300 Heroes Noesis Script (PC)

Can you send 300 Battle Glamorous Heroes scripts? Please
## Post #6
- Username: Seamoroar1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 24, 2018 12:17 am
- Post datetime: 2019-08-13T07:38:11+00:00
- Post Title: 300 Heroes Noesis Script (PC)

> Reply from Mrscouter ↑Wed Aug 07, 2019 1:00 pm at Wed Aug 07, 2019 1:00 pm
>
> 
Do you know if the animations for the models are stored inside the character .x files or somewhere else? It seems to be the former but I can't tell for sure.

It exists in the .X file.
## Post #7
- Username: Seamoroar1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 24, 2018 12:17 am
- Post datetime: 2019-08-13T07:38:31+00:00
- Post Title: 300 Heroes Noesis Script (PC)

> Reply from chrrox ↑Sat Jul 20, 2019 12:57 am at Sat Jul 20, 2019 12:57 am
>
> 
unknown.pngI got the files decrypted the model format is different but it does not look hard I should be able to make a script for it tonight.
Character List
https://pastebin.com/shZS9zXD

Can you send 300 Battle Glamorous Heroes scripts? Please
## Post #8
- Username: Mrscouter
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 22, 2012 4:41 am
- Post datetime: 2019-09-15T02:56:02+00:00
- Post Title: 300 Heroes Noesis Script (PC)

Is there a way to play the animations within Noesis using the original script or is another one needed?
## Post #9
- Username: eyeoflie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 26, 2019 6:33 am
- Post datetime: 2020-08-17T20:01:13+00:00
- Post Title: 300 Heroes Noesis Script (PC)

> Reply from Seamoroar1 ↑Tue Aug 13, 2019 3:38 pm at Tue Aug 13, 2019 3:38 pm
>
> 
Mrscouter wrote: ↑Wed Aug 07, 2019 1:00 pm
Do you know if the animations for the models are stored inside the character .x files or somewhere else? It seems to be the former but I can't tell for sure.


It exists in the .X file.

Are you sure about that?, i'm tring extract model with animation by using this script but unsuccessfully, i did this steps:
1. Dowload game
2. Used scrip jor jmp files
3. Puted .py script into noesis
4. Opened for example 020.x file, i see Alphonse Elric
5. Press extract
6. Done, trying open with 3ds max 2014 and doesn't see anything, opening with blender and see only fbx model without anims
7. Where i did mistake???
## Post #10
- Username: AngleLeX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 08, 2020 11:04 am
- Post datetime: 2020-10-02T11:26:23+00:00
- Post Title: 300 Heroes Noesis Script (PC)

uhhh.I think..........
You Kown,300 Heroes was had a Special tools,which in chinese web.
In there its call to:补丁
That can "extract" model with action.
And then, I have a question,300 Heroes had a Mobile game:"300 Battle Glamorous Heroes"
The model's suffix  is :".x2", is variety of 300 Heroes model.  
Now I try to extract that,but I don't kown how to do,I  ask to Chrrox.but he  not respeak.
## Post #11
- Username: 萌豚燃
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 27, 2022 10:05 am
- Post datetime: 2022-01-27T03:30:58+00:00
- Post Title: 300 Heroes Noesis Script (PC)

thankyou
## Post #12
- Username: AzureBerylBlue
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 08, 2021 4:36 am
- Post datetime: 2022-04-16T23:43:41+00:00
- Post Title: 300 Heroes Noesis Script (PC)

Would it be possible to fix this Noesis plugin so that all models export to reference pose? (A-pose) Or does the reference pose not exist in those model files?
