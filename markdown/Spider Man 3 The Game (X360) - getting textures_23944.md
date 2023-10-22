## Post #1
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-25T15:28:15+00:00
- Post Title: Spider Man 3 The Game (X360) - getting textures

Hi everyone

I want to get textures from game archive. This is game for xbox 360 and TextureFinder doesn't working normally. So could anyone help me? How to understand where texture beginning, where it's ending and what size it got?

sample here:
[https://mega.nz/file/oA1UwJba#3p_Nvf7T9 ... hrhfJ1nVDo](https://mega.nz/file/oA1UwJba#3p_Nvf7T92VaTI_yUJiNHkpQ0btjCdFXLhrhfJ1nVDo)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-25T20:23:29+00:00
- Post Title: Spider Man 3 The Game (X360) - getting textures

What is the name of the game this archive is from?
## Post #3
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-25T22:39:27+00:00
- Post Title: Spider Man 3 The Game (X360) - getting textures

Spider Man 3 The Game. 

Extention of archives is *XEPACK. 

There is solved solution for getting textures from pc version of this game, but nobody can did it with xbox version of game. People who can write script also got stuck. And I decided to get textures without scripts...

Do you have any ideas how to find pieces of textures in this hex code?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-26T06:00:12+00:00
- Post Title: Spider Man 3 The Game (X360) - getting textures

> Do you have any ideas how to find pieces of textures in this hex code?
Yeah, you could use rawtex or texture finder for this task [viewtopic.php?t=15540](https://forum.xentax.com/viewtopic.php?t=15540)

> How to understand where texture beginning, where it's ending and what size it got?
In most cases you need to guess it or just reverse engineer file format to get this information.
You  can get more info on this topic here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)


Btw, there is a script from aluigi that is partially working with your sample
[https://aluigi.altervista.org/bms/apkf.bms](https://aluigi.altervista.org/bms/apkf.bms)
## Post #5
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-26T17:37:16+00:00
- Post Title: Spider Man 3 The Game (X360) - getting textures

> Reply from ikskoks ↑Wed May 26, 2021 2:00 pm at Wed May 26, 2021 2:00 pm
>
> 
Yeah, you could use rawtex or texture finder for this task viewtopic.php?t=15540

Thanks for the answer! I tried all programms from this link. Texfinder and rawtex was closer than others. But there are artifacts on texture:


And here is the same texture but from PC version of game opened with texturefinder:


Do you have any ideas what it could be? (I read a lot of information about endianness and I'm already swapped Big-endian to Little-endian. I have no idea what I need to do next).


> Reply from ikskoks ↑Wed May 26, 2021 2:00 pm at Wed May 26, 2021 2:00 pm
>
> 
Btw, there is a script from aluigi that is partially working with your sample
https://aluigi.altervista.org/bms/apkf.bms

Yeah, we corresponded about that. Luigi helped me with this script but it extracts only names of files. So after extraction I got empty files without extension and coverage was only 4%.

There is working script for extracting files from PC game directory. Files from PC and XBOX looking similar and I have an idea that script could be edited for work correctly with xbox files.

I don't have anought experience in it. So do you have an ideas how to edit script or maybe you know someone who good in this?
## Post #6
- Username: PaHaNchickT
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-26T19:12:14+00:00
- Post Title: Spider Man 3 The Game (X360) - getting textures

> Do you have any ideas what it could be?

It could be some kind of xbox swizzling method.
There was a documentation with detailed explanation available few years back [viewtopic.php?t=10857](https://forum.xentax.com/viewtopic.php?t=10857)
but I think it can be lost now according to the replies in the topic.

There are also these pieces of code that can explain algorithm 
[https://github.com/indirivacua/RAGE-Con ... zzling.pas](https://github.com/indirivacua/RAGE-Console-Texture-Editor/blob/master/Console.Xbox360.Swizzling.pas)
[https://github.com/SamuelCFW/GTA-V-Cons ... zzling.pas](https://github.com/SamuelCFW/GTA-V-Console-Texture-Editor/blob/master/gtav_texture_editor/Console.Xbox360.Swizzling.pas)

But I'm not really familiar with xbox graphics stuff, so I can't help with that.

> So do you have an ideas how to edit script or maybe you know someone who good in this?
No, sorry. Aluigi is one of the best people to deal with such complicated scripts, so if he can't handle it I don't know who can.
## Post #7
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-05-26T20:07:59+00:00
- Post Title: Spider Man 3 The Game (X360) - getting textures

> Reply from ikskoks ↑Thu May 27, 2021 3:12 am at Thu May 27, 2021 3:12 am
>
> 
Do you have any ideas what it could be?

It could be some kind of xbox swizzling method.
There was a documentation with detailed explanation available few years back viewtopic.php?t=10857
but I think it can be lost now according to the replies in the topic.

There are also these pieces of code that can explain algorithm 
https://github.com/indirivacua/RAGE-Con ... zzling.pas
https://github.com/SamuelCFW/GTA-V-Cons ... zzling.pas

But I'm not really familiar with xbox graphics stuff, so I can't help with that.
So do you have an ideas how to edit script or maybe you know someone who good in this?
No, sorry. Aluigi is one of the best people to deal with such complicated scripts, so if he can't handle it I don't know who can.

Oh, looks like something new! I never heard about this "swizzling method". Big thanks for you, it could help me to move on!
