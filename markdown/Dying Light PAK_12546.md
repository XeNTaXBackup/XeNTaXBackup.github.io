## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-27T15:24:09+00:00
- Post Title: Dying Light PAK

Hi All,

Having some trouble to repack files(game does not start after that) from DL game just came out. It looks like normal zip, but .....
Or game checking CRC not sure in this case...

```
38234344/DL_paks.rar
```


rest dw link is in my signature....
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-27T15:48:20+00:00
- Post Title: Dying Light PAK

i guess there is some check crc or something... I cannot figure it out.. Ekey is good for this things???
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-27T16:23:05+00:00
- Post Title: Dying Light PAK

[http://aluigi.altervista.org/papers/bms/zip.bms](http://aluigi.altervista.org/papers/bms/zip.bms)

works fine
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-27T16:48:04+00:00
- Post Title: Dying Light PAK

well how do you repack mate ? To make sure game still works.. Extract never was a problem...
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-27T20:44:16+00:00
- Post Title: Dying Light PAK

You already know the answer to this question > QuickBMS readme > Section 3 - for reimporting files.
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-01-27T20:50:10+00:00
- Post Title: Dying Light PAK

Anyone gonna support the CSB files as well?
## Post #7
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-01-28T02:33:57+00:00
- Post Title: Dying Light PAK

repacked using QuickBMS, but still show me "The game cannot start because your game data appear to be corrupted!"
## Post #8
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2015-01-28T08:21:36+00:00
- Post Title: Dying Light PAK

Yes, game executable checks PAK files. Therefore, either you modify engine.dll to skip executable check, or try that
[http://blog.gib.me/2011/09/09/fixzip-mo ... ngine-dll/](http://blog.gib.me/2011/09/09/fixzip-modifying-dead-island-pak-files-without-hacking-the-engine-dll/)
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-28T09:58:24+00:00
- Post Title: Dying Light PAK

> Reply from rengareng
>
> Yes, game executable checks PAK files. Therefore, either you modify engine.dll to skip executable check, or try that
http://blog.gib.me/2011/09/09/fixzip-mo ... ngine-dll/

Is there any chance to mod engine.dll ? How also what is that check, is it CRC ? Gona try that zipfix as well
## Post #10
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2015-01-28T10:02:17+00:00
- Post Title: Dying Light PAK

You don't need to repack the .pak archives. 

C:\Users\USERNAME\Documents\DyingLight\out\Data\

That's where you can place the files you modified and it'll override the packed version.

Here's a small test I did with the .scr (script?) file that controls the intro movies in order to skip those.
[http://www39.zippyshare.com/v/v03RbV8c/file.html](http://www39.zippyshare.com/v/v03RbV8c/file.html)
(I'd really like if the debug mode could be re-activated - which would also have a way to skip the intro logos amongst other useful features. - but sadly debugconf.scr seems entirely ignored so I guess it's locked down as it was with Gunslinger and other more recent Chrome Engine games although hopefully as with those games someone can write a program to re-enable it.)

Would be nice to get into engine_PC.rpack as well and/or optimized_dx11.mp since one of those most likely has the chromatic aberration files and then perhaps disabling that effect will finally be possible. 
(There's nothing I've found in the .pak files - they are just zip containers by the way so I just open them with WinRar - that work with editing out that effect although some files references a "aberration" effect but editing those break the lighting so it has to be done elsewhere and the two above files both contain references to it so it's probably one of them.)

(Rick / Gibbed's unpacker didn't work as it was probably intended for Chrome Engine 5 and this game uses version 6)
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-28T12:07:36+00:00
- Post Title: Dying Light PAK

> Reply from jbeckman
>
> You don't need to repack the .pak archives. 

C:\Users\USERNAME\Documents\DyingLight\out\Data\

That's where you can place the files you modified and it'll override the packed version.

Here's a small test I did with the .scr (script?) file that controls the intro movies in order to skip those.
http://www39.zippyshare.com/v/v03RbV8c/file.html
(I'd really like if the debug mode could be re-activated - which would also have a way to skip the intro logos amongst other useful features. - but sadly debugconf.scr seems entirely ignored so I guess it's locked down as it was with Gunslinger and other more recent Chrome Engine games although hopefully as with those games someone can write a program to re-enable it.)

Would be nice to get into engine_PC.rpack as well and/or optimized_dx11.mp since one of those most likely has the chromatic aberration files and then perhaps disabling that effect will finally be possible. 
(There's nothing I've found in the .pak files - they are just zip containers by the way so I just open them with WinRar - that work with editing out that effect although some files references a "aberration" effect but editing those break the lighting so it has to be done elsewhere and the two above files both contain references to it so it's probably one of them.)

(Rick / Gibbed's unpacker didn't work as it was probably intended for Chrome Engine 5 and this game uses version 6)

I have try this of course ... It does not work for DataEN.pak files for others it might work but for texts pak it does not ..  RPACK i have start do some reseach allready based of Ricks and someone else research
## Post #12
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2015-01-28T14:27:49+00:00
- Post Title: Dying Light PAK

Oh I see, how strange that it doesn't work with the language files.

I guess the game also won't load other .pak files so you could build on the existing data with say Data04.pak
(And while Data03.pak is just a placeholder for future patches I guess it also gets checked by the game for validation.)
## Post #13
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-01-29T02:58:57+00:00
- Post Title: Dying Light PAK

> Reply from rengareng
>
> Yes, game executable checks PAK files. Therefore, either you modify engine.dll to skip executable check, or try that
http://blog.gib.me/2011/09/09/fixzip-mo ... ngine-dll/

IT WORKED! for DataEn.pak file.
thanks!
## Post #14
- Username: InKviZ
- Rank: advanced
- Number of posts: 51
- Joined date: Mon Sep 29, 2014 12:57 am
- Post datetime: 2015-01-31T10:38:39+00:00
- Post Title: Dying Light PAK

Hi guys! How to unpack and pack DataEn.pak Tried as written here: [http://blog.gib.me/2011/09/09/fixzip-mo ... ngine-dll/](http://blog.gib.me/2011/09/09/fixzip-modifying-dead-island-pak-files-without-hacking-the-engine-dll/) But I can not. Tell me how to do it.
## Post #15
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2015-05-18T22:09:06+00:00
- Post Title: Dying Light PAK

I need to get my hands on font files. Does anyone know where they are located, and how can I edit them?
## Post #16
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2020-01-01T11:39:13+00:00
- Post Title: Re: Dying Light PAK

Unfortunately CRCFIX is no longer working, and neither is the DLL modification. Does anyone know how to fix modified files?
