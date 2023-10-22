## Post #1
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2014-07-02T16:57:00+00:00
- Post Title: Sniper Elite 3 Text Files

Hi, I found the SE3 text files. How do I edit the file? I used the Asura Text Editor, but does not seem to some texts.
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-07-15T05:57:53+00:00
- Post Title: Sniper Elite 3 Text Files

Try this: [https://www.sendspace.com/file/mml37s](https://www.sendspace.com/file/mml37s)

For .asr file (i'm not sure about it's working!):
Drag asr to export exe.
Drag txt to import exe.

For .en file:
Use Evin tool to unpack en file. [viewtopic.php?f=33&t=8902](http://forum.xentax.com/viewtopic.php?f=33&t=8902)
Drag the folder to export exe.
Drag txt to import exe.
Repack en file.
## Post #3
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2014-07-16T09:22:38+00:00
- Post Title: Sniper Elite 3 Text Files

> Reply from swuforce
>
> Try this: https://www.sendspace.com/file/dgq79u

For .asr file:
Drag asr to export exe.
Drag txt to import exe.

For .en file:
Use Evin tool to unpack en file. viewtopic.php?f=33&t=8902
Drag the folder to export exe.
Drag txt to import exe.
Repack en file.
Thanks for the tool. I extracted texts, but game shuts down after the importing texts.
## Post #4
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-07-16T22:08:24+00:00
- Post Title: Sniper Elite 3 Text Files

I think the problem is a value, that i can't change correctly.
Try to use only for .en files.

Update: This value somehow related to the size, but i dont know how. I change it by the difference of the original and edited file. Looks like its ok now, but im not sure it will work in the entire game.

Ok i think i get it. The HTXT file format is something like

```
uint32(4)  - Filesize
uint32(4)  - Version
uint32(4)  - Null
uint32(4)  - Number of strings
uint32(4)  - File hash?
uint32(4)  - Text string size [-Number of strings*8]
uint32(4)  - Language id

for each string
    uint32(4)  - String hash?
    uint32(4)  - String Length [*2]
    char(x)    - Unicode string (null terminated)

char(x)    - Filename
byte(x)    - Padding(4)
uint32(4)  - Text ids size
char(x)    - Text ids (null separated)
```
## Post #5
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-07-20T09:45:32+00:00
- Post Title: Sniper Elite 3 Text Files

> Reply from connortg12
>
> swuforce wrote:Try this: https://www.sendspace.com/file/dgq79u

For .asr file:
Drag asr to export exe.
Drag txt to import exe.

For .en file:
Use Evin tool to unpack en file. viewtopic.php?f=33&t=8902
Drag the folder to export exe.
Drag txt to import exe.
Repack en file.
Thanks for the tool. I extracted texts, but game shuts down after the importing texts.

I updated the tool, try it now.
But i'm still not sure it gonna work.
## Post #6
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2014-07-20T12:53:26+00:00
- Post Title: Sniper Elite 3 Text Files

Thank you! It's working.
## Post #7
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2014-07-20T15:20:41+00:00
- Post Title: Sniper Elite 3 Text Files

> Reply from swuforce
>
> connortg12 wrote:swuforce wrote:Try this: https://www.sendspace.com/file/dgq79u

For .asr file:
Drag asr to export exe.
Drag txt to import exe.

For .en file:
Use Evin tool to unpack en file. viewtopic.php?f=33&t=8902
Drag the folder to export exe.
Drag txt to import exe.
Repack en file.
Thanks for the tool. I extracted texts, but game shuts down after the importing texts.

I updated the tool, try it now.
But i'm still not sure it gonna work.

How do I edit the text in this .en file?
<link removed due forum rules violation>
## Post #8
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2014-07-24T15:15:14+00:00
- Post Title: Sniper Elite 3 Text Files

I updated my text tool. (I didn't wrote into the tool, laziness:), but this compatible backward. Sniper Elite2, AvP2010 etc.)
[SniperElite3Text.zip](https://xentaxbackup.github.io/file/7603_SniperElite3Text.zip)
## Post #9
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-08-31T13:28:59+00:00
- Post Title: Sniper Elite 3 Text Files

Hi all! I have a prolem with DDS font (Sniper Elite 2). I opend origin DDS file and save with this setting: DXT5_NM        XY   8 bpp | using DXT5. Game working normal, but when I edited DDS file and save with setting: DXT5_NM        XY   8 bpp | using DXT5, text isn't display. Here is origin DDS file in hex:


When I view in IranView:  display with red color
When I view in Photoshop:  display with black white color

Thanks in advance!
## Post #10
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2014-08-31T17:42:34+00:00
- Post Title: Sniper Elite 3 Text Files

Try to use XnView. Save .dds file as .png edit then open with XnView. Save as .dds and repack. I'm using this method and no problem.
## Post #11
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-09-01T00:15:05+00:00
- Post Title: Sniper Elite 3 Text Files

> Reply from connortg12
>
> Try to use XnView. Save .dds file as .png edit then open with XnView. Save as .dds and repack. I'm using this method and no problem.

Thanks! For your help!
## Post #12
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-09-11T15:45:43+00:00
- Post Title: Sniper Elite 3 Text Files

I translate Sniper Elite2 (*.en) Big problem, my text must equal origin text, It's hard! How to solve it? Thanks.
## Post #13
- Username: Lajti
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 15, 2011 6:20 am
- Post datetime: 2014-12-09T20:25:19+00:00
- Post Title: Sniper Elite 3 Text Files

You can try to use my editor:
[viewtopic.php?f=10&t=8888&p=89585&hilit ... ite#p89585](http://forum.xentax.com/viewtopic.php?f=10&t=8888&p=89585&hilit=sniper+elite#p89585)

Meanwhile I creating the tools for SE3, but I don't know when will be it finished, I have to solve some problem (game patching is continuous, and always need to update my tools, and maybe create a patching tool between two patches; testing the translate, etc.).
## Post #14
- Username: Lajti
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 15, 2011 6:20 am
- Post datetime: 2015-11-19T14:26:14+00:00
- Post Title: Sniper Elite 3 Text Files

Hi guys!

I finished my Sniper Elite III text editor. Also, I packed the 3, V2 and NZA editors into one package (old editors no longer available):
[http://lajti.hu/se_translator](http://lajti.hu/se_translator)
The editors treat the .en files well and not character limited.
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-20T19:24:11+00:00
- Post Title: Sniper Elite 3 Text Files

> Reply from Lajti
>
> Hi guys!

I finished my Sniper Elite III text editor. Also, I packed the 3, V2 and NZA editors into one package (old editors no longer available):
http://lajti.hu/se_translator
The editors treat the .en files well and not character limited.

Support also big endian ? Can you please share structure ?
## Post #16
- Username: Lajti
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 15, 2011 6:20 am
- Post datetime: 2015-11-20T21:33:05+00:00
- Post Title: Re: Sniper Elite 3 Text Files

> Reply from michalss
>
> Lajti wrote:Hi guys!

I finished my Sniper Elite III text editor. Also, I packed the 3, V2 and NZA editors into one package (old editors no longer available):
http://lajti.hu/se_translator
The editors treat the .en files well and not character limited.

Support also big endian ? Can you please share structure ?

I apologize, but I don't know (big endian probably not). I just compare existing different language files and tried out how it works. If you would like, you can try put only one letter in the editor, save, and see the different
## Post #17
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-03-18T13:20:43+00:00
- Post Title: Re: Sniper Elite 3 Text Files

how to edit fonts? in sniper elite 3?
File00000.RSFL
File00001.FNFO
File00002.RSCF
## Post #18
- Username: Lajti
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 15, 2011 6:20 am
- Post datetime: 2016-09-01T19:37:48+00:00
- Post Title: Re: Sniper Elite 3 Text Files

> Reply from stapheen
>
> how to edit fonts? in sniper elite 3?
File00000.RSFL
File00001.FNFO
File00002.RSCF

Sorry for the (very) late answer. Try to download the Asura Engine Extractor, edit the Fonts.asr, then export/save the desired font.dds.
Get Photoshop and nvidia dds photoshop plugin. After edit, save the dds with this format: 8L (8bpp luminance) No MIP.
## Post #19
- Username: Lajti
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 15, 2011 6:20 am
- Post datetime: 2016-09-01T19:55:31+00:00
- Post Title: Re: Sniper Elite 3 Text Files

Hi everyone!

I created a packer/unpacker for the Nazi Zombie Army 2 and Nazi Zombie Army Trilogy games. Also, completely reworked the editors to packers/unpackers and include an editor for the first Sniper Elite game.
The editor for the first SE is very old, and not working well some special cases. I don't plan to reprogram it.
All other editors reprogrammed for a simple exporter/importer, so they much more easy to use. Read the included readme file.
[http://lajti.hu/se_un_packer](http://lajti.hu/se_un_packer)
## Post #20
- Username: Lajti
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 15, 2011 6:20 am
- Post datetime: 2017-02-19T09:21:46+00:00
- Post Title: Re: Sniper Elite 3 Text Files

Hi everyone,
I'm working on the Sniper Elite 4 un-repacker. If it reach the public state, I will publish it (please don't ask, when).

Lajti
## Post #21
- Username: InKviZ
- Rank: advanced
- Number of posts: 51
- Joined date: Mon Sep 29, 2014 12:57 am
- Post datetime: 2017-03-19T10:48:48+00:00
- Post Title: Re: Sniper Elite 3 Text Files

Who can help me with editing fonts to Sniper Elite V2 I have to redraw just one letter.
## Post #22
- Username: larryberry
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 10, 2017 2:10 pm
- Post datetime: 2017-06-10T06:27:09+00:00
- Post Title: Re: Sniper Elite 3 Text Files

> Reply from swuforce
>
> Try this: https://www.sendspace.com/file/mml37s

For .asr file (i'm not sure about it's working!):
Drag asr to export exe.
Drag txt to import exe.

For .en file:
Use Evin tool to unpack en file. viewtopic.php?f=33&t=8902
Drag the folder to export exe.
Drag txt to import exe.
Repack en file.

Thanks for providing this tool.
## Post #23
- Username: coffi45
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 31, 2018 7:42 pm
- Post datetime: 2018-09-01T13:43:37+00:00
- Post Title: Re: Sniper Elite 3 Text Files

This link is dead - [https://www.sendspace.com/file/mml37s](https://www.sendspace.com/file/mml37s)
Is there an working translator for any sniper elite?
## Post #24
- Username: Lajti
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 15, 2011 6:20 am
- Post datetime: 2018-11-08T11:27:21+00:00
- Post Title: Re: Sniper Elite 3 Text Files

> Reply from coffi45
>
> This link is dead - https://www.sendspace.com/file/mml37s
Is there an working translator for any sniper elite?
[http://lajti.hu/se_translator.php](http://lajti.hu/se_translator.php)
## Post #25
- Username: muserigtc
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Jul 16, 2016 9:44 pm
- Post datetime: 2018-11-08T12:52:11+00:00
- Post Title: Re: Sniper Elite 3 Text Files

> Reply from Lajti
>
> 
http://lajti.hu/se_translator.php

I try to Extract Text for game Nazi Zombie Army Trilogy.. But tools has not responding and not extract anymore.. File .en extension...
## Post #26
- Username: Lajti
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 15, 2011 6:20 am
- Post datetime: 2018-11-08T15:14:57+00:00
- Post Title: Re: Sniper Elite 3 Text Files

> Reply from muslimcyberbjb
>
> Lajti wrote:
http://lajti.hu/se_translator.php

I try to Extract Text for game Nazi Zombie Army Trilogy.. But tools has not responding and not extract anymore.. File .en extension...

I'm working on a new tool, please wait. 1-2 months, sorry for the delay.
## Post #27
- Username: TROPATONY
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 08, 2021 5:26 pm
- Post datetime: 2022-05-06T11:09:30+00:00
- Post Title: Re: Sniper Elite 3 Text Files

> Reply from michalss ↑Sat Nov 21, 2015 3:24 am at Sat Nov 21, 2015 3:24 am
>
> 
Lajti wrote:Hi guys!

I finished my Sniper Elite III text editor. Also, I packed the 3, V2 and NZA editors into one package (old editors no longer available):
http://lajti.hu/se_translator
The editors treat the .en files well and not character limited.

Where can I download this Sniper Elite III text editor?
## Post #28
- Username: TROPATONY
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 08, 2021 5:26 pm
- Post datetime: 2022-05-06T11:25:34+00:00
- Post Title: Re: Sniper Elite 3 Text Files

Hi!  Where can I find this Sniper Elite III text editor. Does the app still exist? I want to try to translate sniper elite v2 and sniper elite III into my language.
