## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-01-29T16:38:24+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

Hello. I need help with unpacking and repacking archives in this game. Can someone look at this files and create quick bms script or tool/unpacker? Please 
In "p" files there are content of the game (like textures)
In "h" files there are file names

I uploaded files for analysis to this post.




[The Cave - files for analysis.zip](https://xentaxbackup.github.io/file/6155_The Cave - files for analysis.zip)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-29T16:52:59+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

[viewtopic.php?f=10&t=9737](http://forum.xentax.com/viewtopic.php?f=10&t=9737)
[viewtopic.php?f=10&t=8631](http://forum.xentax.com/viewtopic.php?f=10&t=8631)

[http://aluigi.altervista.org/papers/bms ... legend.bms](http://aluigi.altervista.org/papers/bms/others/brutal_legend.bms)

PS: Did you not try search?
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-01-29T16:58:40+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

> Reply from Ekey
>
> viewtopic.php?f=10&t=9737
viewtopic.php?f=10&t=8631

http://aluigi.altervista.org/papers/bms ... legend.bms

Thank you. I'll try this ^^

I searched with wrong method ;p
## Post #4
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-01-29T17:03:12+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

File format is similar to the format of game "Stacking".
Also like format of game "Costume Quest", with some modifications.
## Post #5
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2013-01-29T22:57:03+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

> Reply from Ekey
>
> viewtopic.php?f=10&t=9737
viewtopic.php?f=10&t=8631

http://aluigi.altervista.org/papers/bms ... legend.bms

PS: Did you not try search?
These files seem to have a small difference, none of the above methods worked.
## Post #6
- Username: delutto
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-01-30T09:13:05+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

Double_Fine_Unpacker
Test Version
[](http://savepic.org/2670276.jpg)


 Double_Fine_Unpacker.rar
(206.09 KiB) Downloaded 191 times
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-01-30T16:28:33+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

I searched in the internet for the tools to this game and I found new version of Double Fine tool that can support files from The Cave. We can unpack/repack files or strings with text to translate. Enjoy 

Example unpacking command: C:\Users\ikskoks>C:\Users\ikskoks\Desktop\DoubleFineTool\DoubleFineTool.exe -u "
D:\The Cave\Win\Packs\Loc_enUS.~h" C:\Users\ikskoks\Desktop\DoubleFineTool

DoubleFineTool.exe - name of the tool
-u - unpacking option
"D:\The Cave\Win\Packs\Loc_enUS.~h" - path to the "h" file
C:\Users\ikskoks\Desktop\DoubleFineTool - a folder where files will be unpacked

EDIT: Download also available here --> < link expired >
[DoubleFineTool.zip](https://xentaxbackup.github.io/file/6157_DoubleFineTool.zip)
## Post #8
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-01-31T16:52:10+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

Hi guys,
Has anybody tried to edit game fonts? I tried, but without success. Game will not show letters, only white squares (like missing characters). I have used Scaleform 3.x and 4.x for generating GFx, but result is the same.

UPDATE:
Got it! Problem was in one byte. After generating GFx file, one byte was "0x03" (maybe a Scaleform version??), but original GFx file has "0x02" there. So I changed it back to 0x02 and voilà, fonts are showing   

Highlighted byte is THAT   byte:
## Post #9
- Username: jackyjy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:16 pm
- Post datetime: 2013-02-01T06:23:44+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

> Reply from ikskoks
>
> I searched in the internet for the tools to this game and I found new version of Double Fine tool that can support files from The Cave. We can unpack/repack files or strings with text to translate. Enjoy 

Example unpacking command: C:\Users\ikskoks>C:\Users\ikskoks\Desktop\DoubleFineTool\DoubleFineTool.exe -u "
D:\The Cave\Win\Packs\Loc_enUS.~h" C:\Users\ikskoks\Desktop\DoubleFineTool

DoubleFineTool.exe - name of the tool
-u - unpacking option
"D:\The Cave\Win\Packs\Loc_enUS.~h" - path to the "h" file
C:\Users\ikskoks\Desktop\DoubleFineTool - a folder where files will be unpacked

EDIT: Download also available here --> DOWNLOAD DOUBLE FINE TOOL

Sadly it still can't unpack XBOX360 version file.
## Post #10
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-02-01T06:50:47+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> Hi guys,
Has anybody tried to edit game fonts? I tried, but without success. Game will not show letters, only white squares (like missing characters). I have used Scaleform 3.x and 4.x for generating GFx, but result is the same.

UPDATE:
Got it! Problem was in one byte. After generating GFx file, one byte was "0x03" (maybe a Scaleform version??), but original GFx file has "0x02" there. So I changed it back to 0x02 and voilà, fonts are showing   

Highlighted byte is THAT   byte:
Hello, merlinsvk.
Could you tell me how to use the Scaleform 3.x or 4.x to generate the GFx?
I want to translate the game to my own language, already know how to unpack/pack the *.P files.
Could you help me, please?
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-01T10:30:23+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

yeah x360 support would be great  PC is zlib but X360 is lzx
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-01T12:46:10+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

> Reply from Rjack
>
> 
Hello, merlinsvk.
Could you tell me how to use the Scaleform 3.x or 4.x to generate the GFx?
I want to translate the game to my own language, already know how to unpack/pack the *.P files.
Could you help me, please?
Scaleform Gfx it's default Flash SWF with changed header CWS to GFX
## Post #13
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-01T13:25:47+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

> Reply from Rjack
>
> 
Could you tell me how to use the Scaleform 3.x or 4.x to generate the GFx?

Scaleform SDK can be used from Adobe Flash, while you editing fonts in flash file, but it's not necessary. I'm using it from command line like: 
```
gfxexport englishfonts.swf
```


Then I change that one byte and pack new .gfx to .~p archive.

That's all.
## Post #14
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-02-01T15:02:16+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

merlinsvk
Does not work the way. White squares instead of letters.
How to change font in SWF-file in Adobe Flash?
## Post #15
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-02-01T15:12:03+00:00
- Post Title: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> Rjack wrote:
Could you tell me how to use the Scaleform 3.x or 4.x to generate the GFx?


Scaleform SDK can be used from Adobe Flash, while you editing fonts in flash file, but it's not necessary. I'm using it from command line like: Code: Select allgfxexport englishfonts.swf

Then I change that one byte and pack new .gfx to .~p archive.

That's all.
Thanks for your replying. But I have one more question.
What should I do if I want to use another font? Should I change the font name?
Sorry, I'm not good at Adobe Flash.
## Post #16
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-01T15:42:37+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from Haoose
>
> 
Does not work the way. White squares instead of letters.

That's because of that one byte. At least it was my case.


> Reply from Haoose
>
> How to change font in SWF-file in Adobe Flash?

I open up englishfonts.fla (decompiled .swf with Sothink SWF Decompiler), then:

1. Click to Font Embedding...


2. Then you see all fonts in that .fla file (I've used other fonts, cause didn't find original Chauvet and Tasha Quest).
You can add individual alphabet characters, or select whole predefined ranges. Click OK.




3. And now we need to publish it to generate .swf file.



4. These are settings I'm using. 



So we now have edited .swf file, which we will export to .gfx with scaleform gfxexport.
## Post #17
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-01T15:51:50+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from Rjack
>
> 
What should I do if I want to use another font? Should I change the font name?

I also used other fonts. Just edited their names and installed them as Chauvet and Tasha Quest. Maybe it's not needed to do it this complicated way. I have not tested it with subtituted fonts (like that we have in Windows normally, Arial etc.)
## Post #18
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-02-01T17:58:38+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> 

I open up englishfonts.fla (decompiled .swf with Sothink SWF Decompiler), then:

Could you take a look at my englishfonts.swf? 
[https://www.dropbox.com/s/3qs3dq4eaf44b ... hfonts.swf](https://www.dropbox.com/s/3qs3dq4eaf44btn/englishfonts.swf)

I used Sothink SWF Decompiler to decompile it, but I got nothing but a 14.5KB ~englishfonts.fla.
I don't know which part I did wrong.
## Post #19
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-01T18:08:23+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Everything is fine
## Post #20
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-02-01T18:11:04+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Rjack, Costume Quest? =)
## Post #21
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-02-01T18:15:35+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> Everything is fine
Could you send me a copy of the decompiled .fla, please?
## Post #22
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-02-01T18:17:27+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from Haoose
>
> Rjack, Costume Quest? =)
Yes, I have been working on this game for a long time.
## Post #23
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-02-01T18:19:47+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> Haoose wrote:
Does not work the way. White squares instead of letters.
That's because of that one byte. At least it was my case.
Can make a video tutorial how to replace the font?
Replace seemingly correct, but I get the squares, or the game crashes.
Fonts I already have for this game. But I want to understand how to make such fonts as they are used in many games.

> Reply from Rjack
>
> Yes, I have been working on this game for a long time.
I too...
## Post #24
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-01T18:24:26+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from Haoose
>
> 
Replace seemingly correct, but I get the squares, or the game crashes.

Have you changed that byte in .gfx file back to 0x02?
## Post #25
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-02-01T18:36:33+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> Have you changed that byte in .gfx file back to 0x02?
Of course replaced
## Post #26
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-01T22:45:01+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Can anyone pls help me to fix aluigi script for Cave X360? At least struct of the file and sizes of the chunks i can do the rest.

```
http://aluigi.altervista.org/papers/bms/others/brutal_legend.bms
```


I can also send files if anyone is interst to help. Please anyone ?
## Post #27
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-02T11:02:39+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from Haoose
>
> Of course replaced
I probably know why it shows only squares, and it's also an answer for Rjack's question.

> Reply from Rjack
>
> 
What should I do if I want to use another font? Should I change the font name?

We can use other fonts, but their names must be "Chauvet" and "Tasha Quest". I've tried substitute them with Arial and Trebuchet, but only squares showed up.



So guys, change names of your desired fonts in some TTF/OTF font editor (like Fontlab Studio or Hi-Logic FontCreator) and install them to your OS like Chauvet and Tasha Quest. After opening .fla file, Flash will use them automatically.
## Post #28
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-02-02T11:39:13+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> 
So guys, change names of your desired fonts in some TTF/OTF font editor (like Fontlab Studio or Hi-Logic FontCreator) and install them to your OS like Chauvet and Tasha Quest. After opening .fla file, Flash will use them automatically.

thanks, merlinsvk. Those three files you send me that all can be edited with Adobe flash cs5.5.
Unfortunately, after I repacked .~p, I still got many squares.  
I had change the fonts name and install them, and change the byte to 0x02.
My GFx version is 4.0.
## Post #29
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-02T12:16:41+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Yeah, but you are working on Costume Quest, maybe there is another problem that must be solved.
## Post #30
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-02-03T04:35:28+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> Yeah, but you are working on Costume Quest, maybe there is another problem that must be solved.
You are right. I can change the font of The Cave with the same way. It just dose not work on Costume Quest.
## Post #31
- Username: SileniusLegard
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jul 25, 2010 7:00 am
- Post datetime: 2013-02-03T07:06:39+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Err, sorry... but, where are the text files? Haha

I just can't find them among so many files... : S
Thanks.
## Post #32
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-02-03T09:44:51+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

SileniusLegard
RgB_Stuff.~h/~p - cave_enus.stringtable
## Post #33
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-03T23:14:30+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Ok guys, another "problem". How to change the font size? New font is approx. 4x higher than original. (our grandparents will be happy to play without their eyeglasses   )

Original font (that squares ako OK, this time)



And my new font
## Post #34
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-02-04T05:41:10+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

You need find smaller font  
Or decrease its yourself in font editor.
## Post #35
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2013-02-04T07:54:04+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> Ok guys, another "problem". How to change the font size? New font is approx. 4x higher than original. (our grandparents will be happy to play without their eyeglasses   )

You didn't find the original font?

Other possible solution. When you have the .swf file, open with [SWiX](http://www.swixkit.com/) (free), open the new and the original .swf, and find this/these line(s): "<DefineFont3 ". Then change the Ascent/Descent/Leading values based on the originals.
Then save, and gfxexport.
## Post #36
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-04T09:24:39+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from Thief1987
>
> You need find smaller font  
Or decrease its yourself in font editor.

Another font will probably solve it. As a quick test I tried some thin font and it looks quite good.

> Reply from evin
>
> 
You didn't find the original font?

Other possible solution. When you have the .swf file, open with SWiX (free), open the new and the original .swf, and find this/these line(s): "<DefineFont3 ". Then change the Ascent/Descent/Leading values based on the originals.
Then save, and gfxexport.

Ascend/... values are the same, but it's just my bad choice of font.

Thanks for your responses
## Post #37
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-02-04T11:41:49+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Can make a video tutorial how to replace the font? Please =)
## Post #38
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-05T09:26:22+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Which part of replacing?
## Post #39
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-02-05T20:18:11+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> Which part of replacing?
ttf to gfx =)
## Post #40
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-02-05T22:58:55+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Heh, that's on my screenshots. 

1. Open .fla
2. Embed font (modify alphabete)
3. Publish .swf
-----------------------
4. Convert to .gfx
5. Hex edit one byte (in case of The Cave)
6. Pack Gfx_Man.~p archive
## Post #41
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-29T17:44:06+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Can anyone help me out with repack files on X360 please? I have everything in place i know compression is LZX i put files on the end of the archive and keep size multiple 2048, but i guess there is something im missgin, game is running fine, but instead of text im getting "Unknow Linecode", any help woul be great 

Thx
## Post #42
- Username: ivanovjohn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 11, 2014 5:41 pm
- Post datetime: 2014-09-11T10:48:31+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Hi  Please help, it is possible to give command   in   cmd   DoubleFineTool.exe –u Loc_enUS.~h "11"       (where 11 Unpacked data path)
Doesn't work to unpack  
Explain as the line looks
## Post #43
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-09-11T11:51:56+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

That command is good. What does your command line writes?
## Post #44
- Username: ivanovjohn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 11, 2014 5:41 pm
- Post datetime: 2014-09-12T07:20:20+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> That command is good. What does your command line writes?
command line writes

DoubleFineTool.exe –u Loc_enUS.~h "11"

Dont work:
DoubleFineTool.exe –u Loc_enUS.~h "11"
DoubleFineTool.exe –u ~h Loc_enUS.~h 11
??????
[Безымянный.png](https://xentaxbackup.github.io/file/7799_Безымянный.png)
## Post #45
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-09-12T09:05:04+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Try 
```
DoubleFineTool.exe –u "Loc_enUS.~h" "11"
```

But it's weird, because it should work anyway.

And than you can make a batch file (.bat or .cmd) with this command and see if there is any difference.
## Post #46
- Username: ivanovjohn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 11, 2014 5:41 pm
- Post datetime: 2014-09-12T09:19:38+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from merlinsvk
>
> Try Code: Select allDoubleFineTool.exe –u "Loc_enUS.~h" "11"
But it's weird, because it should work anyway.

And than you can make a batch file (.bat or .cmd) with this command and see if there is any difference.

As the team in cmd correctly has to look
write as at you looks
## Post #47
- Username: sigmagamma
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 05, 2022 12:53 am
- Post datetime: 2022-02-04T17:43:30+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

Hi, I'm looking for some information on translating Stacking, and came upon this post. There were some details here suggesting people may be able to help (assuming anyone from the time of the original thread is still here) - I'm seeing some of the same issues and using some of the same tools.

For one I have no idea how to convert a font to the GFX format. I got as far as creating an SWF file with the font using Adobe Animate, and then using gfxexport to convert it. A file gets created alright, but it seems to be somewhat different than the original game file. I saw the comment about changing a byte but I'm not sure which byte (the image is gone by now) and judging by the differences compared to the original file I'm not sure that's the issue - yet.
[https://drive.google.com/file/d/1qgTDaO ... sp=sharing](https://drive.google.com/file/d/1qgTDaOXiNSxzC45wZdOpYVteVvuJFRDj/view?usp=sharing)
[https://drive.google.com/file/d/1EBH7vC ... sp=sharing](https://drive.google.com/file/d/1EBH7vCxB0bkoCg6bJUHYmTL89pDsSeCl/view?usp=sharing)

The game itself shows squares for the Hebrew characters as well as the English characters - Since the font contains both the best case scenario is that I didn't create the gfx file correctly. So what's the correct way to go about creating the gfx file?

Something else that may be an issue has to do with the text itself. 
I'm following the (google translate of) the instructions here:
[https://sites.google.com/site/jpmodfile ... e/stacking](https://sites.google.com/site/jpmodfiles/localize/stacking)

Texttool seems to be doing it's job, but after repacking I'm observing weird signs in the packed file using Double Fine Explorer. I can't be sure at this point that's actually an issue with the game due to the font issue, but that's usually a a sign of something going wrong with Hebrew letters. 
It also occurs to me it may be a problem with Double Fine Explorer and not with the game itself.
[https://drive.google.com/file/d/158ThGQ ... sp=sharing](https://drive.google.com/file/d/158ThGQ4m5cpiUVMISg2RK23rQ8J5wAuG/view?usp=sharing)

Any help would be appreciated 

- Sigmagamma
## Post #48
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-04T23:27:37+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> So what's the correct way to go about creating the gfx file?
There are some tools for creating and editing GFX files like JPEXS Free Flash Decompiler.
Maybe you can try it first. But I'm not sure if it's a correct way in this case.

Also for viewing end editing binary files you can use some hex editor like Hex Workshop.
It will allow you to change this version byte to the one you need.
If GFX is similar to SWF, then version byte should be the one at offset 0x03, right after signature.


As for text issue, you can double check your encoding. I'm not sure if Stacking uses UTF-8 or something else.


Edit: Also check this article
[http://wiki.xentax.com/index.php/Macrom ... leform_GFX](http://wiki.xentax.com/index.php/Macromedia_Flash_SWF_/_Scaleform_GFX)
## Post #49
- Username: sigmagamma
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 05, 2022 12:53 am
- Post datetime: 2022-02-08T19:07:52+00:00
- Post Title: Re: [PC] The Cave - *.~h and *.~p archives

> Reply from ikskoks ↑Sat Feb 05, 2022 7:27 am at Sat Feb 05, 2022 7:27 am
>
> 
There are some tools for creating and editing GFX files like JPEXS Free Flash Decompiler.
Maybe you can try it first. But I'm not sure if it's a correct way in this case.

Thanks ikskoks! it was.
