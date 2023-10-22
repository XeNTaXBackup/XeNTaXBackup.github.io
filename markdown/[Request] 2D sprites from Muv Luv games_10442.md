## Post #1
- Username: gta1211
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 14, 2011 2:30 am
- Post datetime: 2013-05-21T20:42:16+00:00
- Post Title: [Request] 2D sprites from Muv Luv games

Hi there !

I have a request to make, if you can take a look. Maybe you know visual novels games Muv Luv ( マブラヴ in Japanese ). Like all VN, there is a lot of CG images for background, special scenes etc... and a lot of sprites for characters, animated or not. I would like to extract those sprites from the game archive, but all I found was only a software to extract CG images. I guess if they can extract something from the game archive, I don't see why they couldn't do it for other files ( Well, I see what problems they can have, but I believe it's still possible to do, I think they just lack human ressources or time to do it ).

There is 2 main games released ( The third just came out few days ago in Japan ). The first, Muv Luv, is in fact two games in one, regrouping both Muv Luv Extra and Muv Luv Unlimited, released in 2003 on PC CD. The second is Muv Luv Alternative, released in 2006 on PC. Both games was released in 2011-2012 on Xbox 360, PS3 and Windows 7 in their all-age version. They are developed by [âge](http://en.wikipedia.org/wiki/%C3%82ge), a japanese publisher of adult video games and visual novels. 

Here is the infos I got so far :

- The games archive files are *.rio, *.rio.002, *.rio.003 ( For Alternative only ), supported by a *.rio.ici and *.rio.rbt ( For Extra/Unlimited only ).
- If I understood properly, the games were developed using Microsoft Foundation Class library, seeming to be commonly used in VN development. Some guys said it was because of that they couldn't extract all files. Don't ask me anything too complicated for this, even if I understand what it is I can't say for what it is used.
- The tool I used to extract the CG images out of the .rio is named alternativecvt.lzh. Obviously it works only with Alternative. There is another file, muvluvcvt.lzh, that can extract CG files from Extra/Unlimited, but I couldn't find it on the net and it seems to be only sold by a japanese enterprise which sell a commercial tools collection for ripping, named Westside ( Try google Westside CG Rip for more informations ). I put alternativecvt.lzh in file attachment ( In a .rar file as forum will not let me upload .lzh ).
- I suspect sprites from Extra/Unlimited to be simple images, but those of Alternative can be a little different, as the mouth and eyes of the characters move. Maybe Flash or something.

Unfortunately, I can't link you to any legal demo or anything, since there is no legal download available. I can provide you any information you want to know about any files, but you have to tell me what to do for hexadecimal search and stuff like this, at least in the outline.

I wish you can help me with that. I will really be grateful if so. If you are motivated by challenge, I think it can be a good one since nobody have ever extract sprites from these games ( Well, maybe on an obscure japanese site hidden somewhere, but I don't heard of anything on every english site speaking about Muv Luv/General VN ripping ).

Below are screens of any folder for the games, if you see anything useful.

+ [MuvLuv root](http://imageshack.us/a/img826/5666/muvluv.png)
+++++ [MuvLuv/backup](http://imageshack.us/a/img42/9044/muvluvbackup.png)
+++++ [MuvLuv/Manual](http://imageshack.us/a/img802/6793/muvluvmanual.png)
++++++++++ [MuvLuv/Manual/Images](http://imageshack.us/a/img14/5164/muvluvimages.png)
+++++ [MuvLuv/Plugins](http://imageshack.us/a/img823/2279/muvluvplugins.png)
+++++ [MuvLuv/Vmreg](http://imageshack.us/a/img809/649/muvluvvmreg.png)

+ [MuvLuvAlternative root](http://imageshack.us/a/img197/3761/muvluvalternative.png)
+++++ [MuvLuvAlternative/Manual](http://imageshack.us/a/img835/93/muvluvalternativemanual.png)
++++++++++ [MuvLuvAlternative/Manual/Images](http://imageshack.us/a/img577/93/muvluvalternativemanual.png)
+++++ [MuvLuvAlternative/Plugins](http://imageshack.us/a/img94/6337/muvluvalternativeplugin.png)
+++++ [MuvLuvAlternative/Vmreg](http://imageshack.us/a/img843/9384/muvluvalternativevmreg.png)

Again, thanks in advance, and I'm open for any question, here or by PM !


Waiting for good news,

See ya !
[alternativecvt.rar](https://xentaxbackup.github.io/file/6418_alternativecvt.rar)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-05-27T22:16:24+00:00
- Post Title: [Request] 2D sprites from Muv Luv games

i'll take a look using luigi's comscan... if it finds anything and i can decompress the data i'll try extracting the sprites from total eclipse.
## Post #3
- Username: gta1211
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 14, 2011 2:30 am
- Post datetime: 2013-05-28T17:11:51+00:00
- Post Title: [Request] 2D sprites from Muv Luv games

Thanks for the look !

I guess if you manage to extract Total Eclipse files, we will be able to extract Extra/Unlimited/Alternative ones the same way ? Besides, I don't have Total Eclipse, so I don't know if it works with the same files archives ( .rio ).
## Post #4
- Username: gta1211
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 14, 2011 2:30 am
- Post datetime: 2013-06-14T21:18:37+00:00
- Post Title: [Request] 2D sprites from Muv Luv games

Up !

Any news ? I checked the release date of Total Eclipse on PC and saw it wasn't released yet, are you waiting for the PC release or were you talking about PS360 files ?

While waiting for your try, I tried using Luigi's comscan on Extra .rio file ( If you are talking about Aluigi's Signsearch ), and... Well, I have to admit I don't understand anything. Here is what I only got on マブラヴ11.rio :

```
  --------------------------------------------
  09f60cb2 2565 anti-debug: Stack Segment register [..4]
  202c7fa5 2250 TEA1_DS [32.be.4]
```


EDIT : Here is for マブラヴ11.rio.002 :

```
  --------------------------------------------
  0f2db7f7 2565 anti-debug: Stack Segment register [..4]
  19aa127c 1038 padding used in hashing algorithms (0x80 0 ... 0) [..64]
  1d313a25 2250 TEA1_DS [32.be.4]
```


EDIT2 : And here is for マブラヴ11.exe. Other possibly-relevant files ( マブラヴ11.rio.ici and  マブラヴ11.rbt ) do not contain any known signature.

```
  --------------------------------------------
  000444f2 3050 compression algorithm seen in the game DreamKiller [32.le.12&]
```


EDIT3 : Tried to do it with Alternative files : マブラヴオルタネイティヴ.exe has nothing, Alternative.rio and Alternative.rio.002 seem to be too big ( 2Go+ each ), but I got this for Alternative.rio.003 :

```
  --------------------------------------------
  008c150e 3051 compression algorithm seen in the game DreamKiller [32.be.12&]
```


Although I was happy to see some known compression algorithm on one of the data archives, I tried to use Dreamkiller Aluigi's QuickBMS script with them, but it doesn't seem to work. Maybe I'm doing something wrong ( I hope so ).
## Post #5
- Username: gta1211
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 14, 2011 2:30 am
- Post datetime: 2013-07-21T19:56:39+00:00
- Post Title: [Request] 2D sprites from Muv Luv games

Up !

Any news Howfie ?
