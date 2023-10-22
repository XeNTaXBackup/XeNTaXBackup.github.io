## Post #1
- Username: ValarMorghulis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 23, 2015 9:07 pm
- Post datetime: 2015-08-19T13:10:26+00:00
- Post Title: [PC CBT] Soul Worker

Hello everyone!
I'd like to rip Soul Worker's models but I don't know how. If you need the CBT client, here you go (2,98GB):
[Part 0](http://down.hangame.co.jp/nstor/jp/purple/setup/j_sw/EXE/SW-Setup.exe) | [Part 1](http://down.hangame.co.jp/nstor/jp/purple/setup/j_sw/EXE/SW-Setup-1.bin) | [Part 2](http://down.hangame.co.jp/nstor/jp/purple/setup/j_sw/EXE/SW-Setup-2.bin) | [Part 3](http://down.hangame.co.jp/nstor/jp/purple/setup/j_sw/EXE/SW-Setup-3.bin) | [Part 4](http://down.hangame.co.jp/nstor/jp/purple/setup/j_sw/EXE/SW-Setup-4.bin) | [Part 5](http://down.hangame.co.jp/nstor/jp/purple/setup/j_sw/EXE/SW-Setup-5.bin)
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-08-21T18:54:45+00:00
- Post Title: [PC CBT] Soul Worker

Hi
Here are a tool (not main) and an importer for models from this game.
How use:
- v unpacker is inside zip
- install Blender version 249 and Python version 2.6.6. (don't use portable, only installed)
- click Blender249.blend
- check console window for this lines:
"Compiled with Python version 2.6.2."
"Checking for installed Python... got it"
- in Blender Text Window press alt+p and select *.model file
- animation is not supported
- script was tested only on skinned meshes
[Blender249[SoulWorkerOnine][model][2015-08-21].zip](https://xentaxbackup.github.io/file/9609_Blender249[SoulWorkerOnine][model][2015-08-21].zip)
## Post #3
- Username: ValarMorghulis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 23, 2015 9:07 pm
- Post datetime: 2015-08-22T14:35:12+00:00
- Post Title: [PC CBT] Soul Worker

> Reply from Szkaradek123
>
> Hi
Here are a tool (not main) and an importer for models from this game.
How use:
- v unpacker is inside zip
- install Blender version 249 and Python version 2.6.6. (don't use portable, only installed)
- click Blender249.blend
- check console window for this lines:
"Compiled with Python version 2.6.2."
"Checking for installed Python... got it"
- in Blender Text Window press alt+p and select *.model file
- animation is not supported
- script was tested only on skinned meshes
Thanks a lot, you're a genius!
I just have one little problem. Where can I download Blender 2.49's setup compatible with Python 2.6.6 (for Windows x64)?
I tried Blender 2.49 portable, Blender 2.49 (Py25), Blender 2.49a and Blender 2.49b... none of these worked...

EDIT: Nevermind, problem solved. Thanks a lot!
## Post #4
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2018-02-27T15:27:31+00:00
- Post Title: [PC CBT] Soul Worker

Hey Guys can anyone help me with something? I cannot open the blender file it allways crashes and after i finaly got the  specified tools it still crashed. why?
## Post #5
- Username: Bronya
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 25, 2018 2:51 am
- Post datetime: 2018-05-01T13:35:13+00:00
- Post Title: [PC CBT] Soul Worker

This problem i get when i pressed alt+p  :   Python script error : check the console    .   What can i do ?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-01T15:29:09+00:00
- Post Title: [PC CBT] Soul Worker

> Reply from Bronya
>
> What can i do ?you could attach (or upload) a .model sample so that someone could check this.

In your blender console window it must read:
"Checking for installed Python... got it"

else you've to install python. The version installed with blender is too "light" for the Soul Worker py script, I suppose.
## Post #7
- Username: jayd00
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 10, 2014 8:30 am
- Post datetime: 2018-09-25T06:55:43+00:00
- Post Title: [PC CBT] Soul Worker

can someone update this script for blender 2.79? please?


[](https://postimg.cc/wRpN0FP2)

I got this error in blender 2.79
I already copied the "newGameLib" folder where blender.exe is located, but I read that this have to deal with Blender because this script is made for blender 2.49 and the API has changed in blender 2.79

I'm using windows 10 x64, could someone help me updating this script? thank you!
## Post #8
- Username: kotaxzz1
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 21, 2015 1:44 am
- Post datetime: 2019-01-31T07:39:25+00:00
- Post Title: [PC CBT] Soul Worker

i got this error when try importing Character/Player model file. Cutscene or NPC model load fine with texture applied.

Compiled with Python version 2.6.1.
Checking for installed Python... got it!
Traceback (most recent call last):
  File "starter.py", line 333, in Parser
    modelParser(filename,g)
  File "starter.py", line 160, in modelParser
    mesh.draw()
  File "D:\BurningSoulWorker\blender-2.49b-windows\newGameLib\myLibraries\meshLib.py", line 614, in draw
    self.addfaceUV(self.mesh,self)
  File "D:\BurningSoulWorker\blender-2.49b-windows\newGameLib\myLibraries\meshLib.py", line 372, in addfaceUV
    face.mat=mesh.matIDList[ID]
ValueError: expected int argument in [0,15]

the files : [https://drive.google.com/open?id=1JeXqo ... Yeq9rvXPYf](https://drive.google.com/open?id=1JeXqommxGpPeewM-8NqDdeYeq9rvXPYf)
