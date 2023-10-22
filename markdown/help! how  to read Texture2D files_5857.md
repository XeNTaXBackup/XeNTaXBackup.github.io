## Post #1
- Username: zozi
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 15, 2010 12:59 am
- Post datetime: 2011-01-20T11:03:38+00:00
- Post Title: help! how  to read Texture2D files?

this file :

 NHNLogo.zip
(1.57 KiB) Downloaded 51 times


NHNLogo.Texture2D   i don't know what's this   
but I know it must be a TGA image   
may you  help me,please?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-20T11:54:58+00:00
- Post Title: help! how  to read Texture2D files?

this thing?

```
|\|-|\|
```


not much of a logo  

[http://www.nhnusainc.com/usa/index.nhn](http://www.nhnusainc.com/usa/index.nhn)
## Post #3
- Username: zozi
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 15, 2010 12:59 am
- Post datetime: 2011-01-20T12:03:22+00:00
- Post Title: help! how  to read Texture2D files?

> Reply from WRS
>
> this thing?
Code: Select all|\|-|\|

not much of a logo  

http://www.nhnusainc.com/usa/index.nhn

yes it's NHN's logo. but how to view and edit it ?
you mean it's not enough , need another file(s) ?

sorry my English is very poor . I'm chinese.
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-20T15:10:20+00:00
- Post Title: help! how  to read Texture2D files?

zozi, where did you get this file? From what game/title/app?
## Post #5
- Username: zozi
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 15, 2010 12:59 am
- Post datetime: 2011-01-21T03:44:55+00:00
- Post Title: help! how  to read Texture2D files?

from the game TERA ,unpack one of his .GPK files, use a tool named Unreal Package Extractor.

this is the tool [http://www.gildor.org/downloads](http://www.gildor.org/downloads)

and this is the .gpk files of TERA:
[S1UI_Chat2.zip](https://xentaxbackup.github.io/file/3827_S1UI_Chat2.zip)
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-21T04:19:12+00:00
- Post Title: help! how  to read Texture2D files?

> Reply from zozi
>
> from the game TERA ,unpack one of his .GPK files, use a tool named Unreal Package Extractor.

this is the tool http://www.gildor.org/downloads

and this is the .gpk files of TERA:for *.gpk files you should use umodel from [here](http://www.gildor.org/downloads), yes I know it called Unreal Model Viewer, but it can unpack/convert all you need, instead of Unreal Package Extractor

So, just put *.gpk file, umodel.exe and sdl.dll in one folder and run cmd command:

```
umodel.exe -export -game=tera -all your_file.gpk
```
and you get all *.tga you need
## Post #7
- Username: zozi
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 15, 2010 12:59 am
- Post datetime: 2011-01-21T06:04:37+00:00
- Post Title: help! how  to read Texture2D files?

thanks a lot!
now I can make beautiful wallpaper use the TERA's images  

but...it seems like only export picture files ...

and I even wanna to repack it ...  

how do you think about it?
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-21T06:34:30+00:00
- Post Title: help! how  to read Texture2D files?

Umodel can import textures, 3d models and animation from tera, and other unreal-like games.

Packing resources back into gpk impossible.
## Post #9
- Username: zozi
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 15, 2010 12:59 am
- Post datetime: 2011-01-21T06:47:12+00:00
- Post Title: help! how  to read Texture2D files?

What a pity..
however , thank you very much
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-21T06:55:35+00:00
- Post Title: help! how  to read Texture2D files?

Maybe you can find more information [here](http://www.gildor.org/smf/index.php/board,30.0.html)
## Post #11
- Username: zozi
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 15, 2010 12:59 am
- Post datetime: 2011-01-21T07:28:11+00:00
- Post Title: help! how  to read Texture2D files?

thx. I'm learning...
