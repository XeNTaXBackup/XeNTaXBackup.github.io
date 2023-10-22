## Post #1
- Username: Ren07
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Oct 12, 2014 2:05 am
- Post datetime: 2017-09-01T00:39:48+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

Hello.
Does anybody know how to edit LSB files? I need your help.
Thank you.
[Life is Strange Before the Storm Sample.7z](https://xentaxbackup.github.io/file/13270_Life is Strange Before the Storm Sample.7z)
## Post #2
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2017-09-01T01:29:23+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

It XORed.
I'll make the converter a little later.
## Post #3
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-09-01T06:04:52+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from Haoose
>
> It XORed.
I'll make the converter a little later.
what about font? add new characters...
## Post #4
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2017-09-01T11:33:25+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

Here is mine .lsb decrypter: [https://yadi.sk/d/mkCZ5Q4J3MWrYk](https://yadi.sk/d/mkCZ5Q4J3MWrYk)
Requirement: Python 3
## Post #5
- Username: sjh00
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 01, 2017 7:21 pm
- Post datetime: 2017-09-01T11:45:29+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> Here is mine .lsb decrypter: https://yadi.sk/d/mkCZ5Q4J3MWrYk
Requirement: Python 3

I want to change the font.How can I unpack and repack resources.assets.
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-09-01T12:35:48+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> Here is mine .lsb decrypter: https://yadi.sk/d/mkCZ5Q4J3MWrYk
Requirement: Python 3

Can you please also make import...... I dont want to work on it if somebody else already started..
## Post #7
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2017-09-01T13:44:45+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from michalss
>
> flatz wrote:Here is mine .lsb decrypter: https://yadi.sk/d/mkCZ5Q4J3MWrYk
Requirement: Python 3

Can you please also make import...... I dont want to work on it if somebody else already started..

I can do it but maybe later (if someone else won't do it before me), I'm at work at the moment.
## Post #8
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2017-09-01T16:56:09+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> Here is mine .lsb decrypter: https://yadi.sk/d/mkCZ5Q4J3MWrYk
Requirement: Python 3

What about Unicode?
## Post #9
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2017-09-01T17:26:13+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

Texts are encoded using UTF-8, the tool should support it without any changes.
## Post #10
- Username: ferdinand
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 02, 2017 3:45 am
- Post datetime: 2017-09-01T19:50:48+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> Here is mine .lsb decrypter: https://yadi.sk/d/mkCZ5Q4J3MWrYk
Requirement: Python 3

how do you use it? Quick BMS with?
## Post #11
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2017-09-01T21:35:21+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

Just updated a tool to support both encoding and decoding of subtitles and just raw binaries (used for scripts). All texts uses UTF-8 encoding and *nix new lines. Here is an updated version of a tool (arguments were changed, see usage):
[https://yadi.sk/d/_GkpByQw3MXjag](https://yadi.sk/d/_GkpByQw3MXjag)
I've also made an executable bundle for Windows as well as included a source code.

All texts are stored in subtitles, english texts are duplicated in scripts too but they shouldn't be changed (no reason to do that at all).
## Post #12
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-09-03T06:19:13+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

good, but when i want to use this tool... i get this eror in cmd 

C:\Users\listool>listool.exe
Error loading Python DLL: C:\Users\listo
ol\python35.dll (error code 193)

python35.dll (error code 193)
who can help me about that?
## Post #13
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2017-09-03T08:57:41+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

Seems your folder doesn't have other files from archive (listool.7z), you should extract all files to the folder.
## Post #14
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2017-09-03T11:42:50+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

I've modified Engine's source code to log used fonts, here is the list of them:

Dudu (resources.assets, named as TurotialButtonFont there)
Helveti (sharedassets1.assets)
HelvetiItalic (sharedassets1.assets)
FixedSys (sharedassets1.assets, it's probably not needed for us because I think it's used for debugging purposes)
BMcE (sharedassets0.assets)
## Post #15
- Username: sjh00
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 01, 2017 7:21 pm
- Post datetime: 2017-09-03T14:37:20+00:00
- Post Title: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> I've modified Engine's source code to log used fonts, here is the list of them:

Dudu (resources.assets, named as TurotialButtonFont there)
Helveti (sharedassets1.assets)
HelvetiItalic (sharedassets1.assets)
FixedSys (sharedassets1.assets, it's probably not needed for us because I think it's used for debugging purposes)
BMcE (sharedassets0.assets)

Thanks a lot! It's very helpful.
## Post #16
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-09-03T14:39:36+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

thank you about font but this error already are in my cmd
sorry about my bad english
## Post #17
- Username: rex2630
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 04, 2017 1:37 am
- Post datetime: 2017-09-03T17:38:49+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

Hi. I doing translation. How can i change font in game? Thanks for reply.
## Post #18
- Username: Darkness9898
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 10, 2017 12:25 am
- Post datetime: 2017-09-05T15:44:20+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> Just updated a tool to support both encoding and decoding of subtitles and just raw binaries (used for scripts). All texts uses UTF-8 encoding and *nix new lines. Here is an updated version of a tool (arguments were changed, see usage):
https://yadi.sk/d/_GkpByQw3MXjag
I've also made an executable bundle for Windows as well as included a source code.

All texts are stored in subtitles, english texts are duplicated in scripts too but they shouldn't be changed (no reason to do that at all).
I did not understand how to use software. I run a listool and nothing happens ... I'm grateful for the explanation
## Post #19
- Username: paiduser
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 06, 2017 7:38 pm
- Post datetime: 2017-09-06T12:13:53+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from Ren07
>
> Hello.
Does anybody know how to edit LSB files? I need your help.
Thank you.

can u send the rest of the localization file?
the subtitles in my game are in Russian
## Post #20
- Username: muserigtc
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Jul 16, 2016 9:44 pm
- Post datetime: 2017-09-06T14:32:29+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

Its work it for me... In Translation to Indonesian Language.
## Post #21
- Username: Darkness9898
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 10, 2017 12:25 am
- Post datetime: 2017-09-06T16:08:23+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from muslimcyberbjb
>
> 


Its work it for me... In Translation to Indonesian Language.
Tell me please how you unpacked and packed .lsb files
## Post #22
- Username: paiduser
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 06, 2017 7:38 pm
- Post datetime: 2017-09-06T18:25:12+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

if someone please can send the lsb files of english
## Post #23
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-09-08T07:45:14+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from Darkness9898
>
> 
Tell me please how you unpacked and packed .lsb files
[http://zenhax.com/viewtopic.php?p=26174#p26174](http://zenhax.com/viewtopic.php?p=26174#p26174)
## Post #24
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2017-09-09T20:49:54+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

Font rebuilder is almost finished, here are some examples of cyrillic fonts and russian texts (using google translation, fonts here are just for testing):

[](http://postimg.org/image/ekok9k3mt/)
[](http://postimg.org/image/sfmus0y1x/)
[](http://postimg.org/image/4tr8jl55x/)
[](http://postimg.org/image/52ot9ihyd/)
[](http://postimg.org/image/b66dtf885/)
[](http://postimg.org/image/l27gt2e05/)
## Post #25
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-09-09T21:12:15+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> Font rebuilder is almost finished, here are some examples of cyrillic fonts and russian texts (using google translation, fonts here are just for testing):
Try this font
## Post #26
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2017-09-09T21:19:42+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from makcar
>
> flatz wrote:Font rebuilder is almost finished, here are some examples of cyrillic fonts and russian texts (using google translation, fonts here are just for testing):
Try this font
Nice, thank you. I've searched this font but with no luck.  Do you have HelvetiHand/HelvetiHandItalic with cyrillic characters too? If so, would you mind to share them too?
## Post #27
- Username: arashwave
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 20, 2017 1:35 am
- Post datetime: 2017-09-19T17:40:06+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> makcar wrote:flatz wrote:Font rebuilder is almost finished, here are some examples of cyrillic fonts and russian texts (using google translation, fonts here are just for testing):
Try this font
Nice, thank you. I've searched this font but with no luck.  Do you have HelvetiHand/HelvetiHandItalic with cyrillic characters too? If so, would you mind to share them too?

Hi
Thanks for your lsb encoder and decoder. You said you finished the font rebuilder. Can you put it in this forum? we really need your font rebuilder. thanks again
## Post #28
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2017-09-19T20:21:42+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from arashwave
>
> Thanks for your lsb encoder and decoder. You said you finished the font rebuilder. Can you put it in this forum? we really need your font rebuilder. thanks again
I'm not planning to release it until our guys release russian localization, not sure if it will be just a single episode or all episodes at once.
## Post #29
- Username: arashwave
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 20, 2017 1:35 am
- Post datetime: 2017-09-20T09:59:58+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> arashwave wrote:Thanks for your lsb encoder and decoder. You said you finished the font rebuilder. Can you put it in this forum? we really need your font rebuilder. thanks again
I'm not planning to release it until our guys release russian localization, not sure if it will be just a single episode or all episodes at once.

Can you at least tell us how to change the fallback font? We really need your help. Thanks
## Post #30
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-09-21T04:57:40+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

hey guys! please dont help to arashwave and relaxfun in this forum... they translate games for money! i mean, they using our help to get money! thats a robby! this guys do that for money!
## Post #31
- Username: arashwave
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 20, 2017 1:35 am
- Post datetime: 2018-01-02T18:37:05+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from GHOST DEAD
>
> hey guys! please dont help to arashwave and relaxfun in this forum... they translate games for money! i mean, they using our help to get money! thats a robby! this guys do that for money!

We are translating thousands of thousands line to a language that no one is trying to translate it. We use free tools to make something biger. It's like making video games with free game enginer ( games such as Hellblade senua's sacrifice, Bioshock Infinite, Batman arkham knight, 
PLAYERUNKNOWN'S battleground and etc. They all made by Unreal engine which is a free engine. And it's not robbery at all.
## Post #32
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2018-03-26T08:43:51+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

Fonts repacker/text encoder: [https://yadi.sk/d/_GkpByQw3MXjag](https://yadi.sk/d/_GkpByQw3MXjag) (works on Windows 10 at least)
Extract font layouts and textures (in .dds format) using public tools (UnityEx, for example) into proper directories (see needed names in config.ini), put .ttf fonts that you want to use (also see config.ini) and run generate command using crafted config.ini, then grab newly generated layouts/textures and put them back into archives using the same tool.
## Post #33
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-26T10:56:43+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> Fonts repacker/text encoder: https://yadi.sk/d/_GkpByQw3MXjag (works on Windows 10 at least)
Extract font layouts and textures (in .dds format) using public tools (UnityEx, for example) into proper directories (see needed names in config.ini), put .ttf fonts that you want to use (also see config.ini) and run generate command using crafted config.ini, then grab newly generated layouts/textures and put them back into archives using the same tool.

dude... font repacker? good... but game using ttf font like real character...
and in unity engine, when a character cant find in main font, font will turn in Arial and we can change this Font name in a hex editor ( from exe file, find arial and repalce with another)
some enginers know what i said about shadres files

good luck and many thanks for this great work
## Post #34
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2018-03-26T11:33:35+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

GHOST DEAD
Yea, I know about this method too but I don't prefer methods that needs executable modifications.
## Post #35
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-26T14:02:08+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz
>
> GHOST DEAD
Yea, I know about this method too but I don't prefer methods that needs executable modifications.

so... I have some version from this game
tool just can work on steam release...
can't work on cracked or edition versions
i tested but some version doesnt have some shareassets files or name are Different in other version...
## Post #36
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2018-03-26T21:45:09+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from GHOST DEAD
>
> i tested but some version doesnt have some shareassets files or name are Different in other version...
It's not a problem, just find assets that are needed for your specific game release, could be done easily. My config.ini is just a sample file, you may modify it for your needs as you want, there are a tons of parameters that could be tweaked. In theory it's even not LIS specific tool and you may use it for everything else (the only problem is layout format for that game).
## Post #37
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-27T04:01:28+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

no dude....  You didn't understand what i meant
i found all  needed files...
but i get  this error in CMD or .bat file
errorr picture: [https://pasteboard.co/HdMzgkH.png](https://pasteboard.co/HdMzgkH.png)
## Post #38
- Username: DeathScreen213
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 15, 2019 5:38 pm
- Post datetime: 2019-05-25T19:59:10+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

LIFE IS STRANGE: BEFORE THE STORM with dlc Farewell.
All fonts in one texture. It's in the Data\StreamingAssets\Bundles\UI\__F3C14028.bytes
Here is the binary font (40 bytes for one character) and texture for who need to translate this game.
[All_Fonts](https://cdn.discordapp.com/attachments/562128641648099328/581933717451177984/All_fonts.zip)
P/s: sorry for my bad english.
## Post #39
- Username: nguyentu22995
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 04, 2020 5:54 pm
- Post datetime: 2020-01-04T10:07:55+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

I downloaded the listool and extracted it. But when I run the program, nothing happens. Please help me 
I use windows 10.
## Post #40
- Username: thisrock84
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 02, 2019 8:20 pm
- Post datetime: 2021-05-16T18:50:57+00:00
- Post Title: Re: [PC] Life is Strange: Before the Storm (*.lsb)

> Reply from flatz ↑Sat Sep 02, 2017 5:35 am at Sat Sep 02, 2017 5:35 am
>
> 
Just updated a tool to support both encoding and decoding of subtitles and just raw binaries (used for scripts). All texts uses UTF-8 encoding and *nix new lines. Here is an updated version of a tool (arguments were changed, see usage):
https://yadi.sk/d/_GkpByQw3MXjag
I've also made an executable bundle for Windows as well as included a source code.

All texts are stored in subtitles, english texts are duplicated in scripts too but they shouldn't be changed (no reason to do that at all).

Thank you so much, it worked!
