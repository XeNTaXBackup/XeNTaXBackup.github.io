## Post #1
- Username: romaw
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 05, 2016 11:51 pm
- Post datetime: 2016-10-09T17:12:54+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

Hello everyone.
there are files of the game MasterRallye 2001 in the format - example 2dtree2-tga.dxt renaming nothing does not, plug-ins do not open in Photoshop
search nothing useful [https://www.google.com/search?hl=ru&sou ... ogle&gbv=2](https://www.google.com/search?hl=ru&source=hp&biw=&bih=&q=tga.dxt&btnG=%D0%9F%D0%BE%D0%B8%D1%81%D0%BA+%D0%B2+Google&gbv=2) 
DXTbmp nothing useful 
dxt2dss [viewtopic.php?f=18&t=1812&hilit=DXT2DDS&start=75](http://forum.xentax.com/viewtopic.php?f=18&t=1812&hilit=DXT2DDS&start=75) [http://wiki.xentax.com/index.php/Game_Tools#DXT2DDS](http://wiki.xentax.com/index.php/Game_Tools#DXT2DDS) fails to start error on win xp
[http://zenhax.com/viewtopic.php?f=9&t=2 ... dxt#p16510](http://zenhax.com/viewtopic.php?f=9&t=2927&p=16510&hilit=dxt#p16510) here the same file but it is not clear how to open...
Microsoft DirectX SDK nothing useful ...
[http://www.nvidia.com/object/real-time- ... .html#ref4](http://www.nvidia.com/object/real-time-ycocg-dxt-compression.html#ref4) nothing useful ... 
[https://sourceforge.net/directory/os:windows/?q=dxt](https://sourceforge.net/directory/os:windows/?q=dxt) nothing useful ... 
what else can you use to open the file?
[2dtree1-tga.rar](https://xentaxbackup.github.io/file/11774_2dtree1-tga.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-09T18:07:44+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

your sample is 128x128 rgba32 image with a 20 byte header, the 2nd integer might be format and the 4th and 5th integers are width and height   
if you can upload more varying samples i will assemble a Noesis python script.
## Post #3
- Username: romaw
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 05, 2016 11:51 pm
- Post datetime: 2016-10-11T11:46:54+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

> Reply from AceWell
>
> your sample is 128x128 rgba32 image with a 20 byte header, the 2nd integer might be format and the 4th and 5th integers are width and height   
if you can upload more varying samples i will assemble a Noesis python script.
archive texture has a size of 300 megabytes, attached in the first message has a link to the game and read me file

if you don't have access to utorrent, I can attachment to cloud disk
[https://yadi.sk/d/ESfHCfN8wdyPn](https://yadi.sk/d/ESfHCfN8wdyPn)

 there is still a file ".DX" with the 3d model in the attachment
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-11T22:49:02+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

here is the Noesis python script to open the dxt textures  


 tex_MasterRallye2001_dxt.zip
(688 Bytes) Downloaded 33 times



supports bgra32 image data
## Post #5
- Username: romaw
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 05, 2016 11:51 pm
- Post datetime: 2016-10-14T16:14:26+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

> Reply from AceWell
>
> here is the Noesis python script to open the dxt textures  
tex_MasterRallye2001_dxt.zip

supports bgra32 image data
but back in the format dxt?
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-14T20:02:11+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

the image data looks the same as a tga, it just has a custom header. you can use Noesis to open
the dxt texture you want to modify and export as tga then modify the texture and save it as tga
and overwrite the 18 byte tga header with the 20 byte dxt header from the original dxt file. (maybe)
## Post #7
- Username: romaw
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 05, 2016 11:51 pm
- Post datetime: 2016-10-15T15:21:12+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

> Reply from AceWell
>
> the image data looks the same as a tga, it just has a custom header. you can use Noesis to open
the dxt texture you want to modify and export as tga then modify the texture and save it as tga
and overwrite the 18 byte tga header with the 20 byte dxt header from the original dxt file. (maybe)
you do not understand,I exported the file to tga and edit in photoshop,but as back to the dxt format? no output my format
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-15T20:34:45+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

> Reply from romaw
>
> you do not understand,I exported the file to tga and edit in photoshop,but as back to the dxt format? no output my format
no you do not understand, there is no tga to dxt plugin to my knowledge.  
i say you how to take your modified image data and turn it back into the dxt format by hand.  
dxt is just tga with a custom header and file naming convention, just restore the original header and file name.

anyway, game modding is not my area, i just like converting from game formats and not to them
so i can not help you further here.
## Post #9
- Username: romaw
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 05, 2016 11:51 pm
- Post datetime: 2016-10-21T17:28:16+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

> Reply from AceWell
>
> romaw wrote:you do not understand,I exported the file to tga and edit in photoshop,but as back to the dxt format? no output my format
no you do not understand, there is no tga to dxt plugin to my knowledge.  
i say you how to take your modified image data and turn it back into the dxt format by hand.  
dxt is just tga with a custom header and file naming convention, just restore the original header and file name.

anyway, game modding is not my area, i just like converting from game formats and not to them
so i can not help you further here.
I found the Converter in the desired format,but the converted image doesn't open
[https://quickandeasysoftware.net/?s=.dxt](https://quickandeasysoftware.net/?s=.dxt) other format?


as it turned out it noesisv40953 does not open to convert the file after MISE_Image_Converter_1.1
but the game supports it, problem solved thank you all
## Post #10
- Username: kovaloid
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 01, 2017 12:30 pm
- Post datetime: 2017-12-01T05:55:52+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

AceWell, Hi!
I'm trying to get resources from this game too... (yeah, I know that the yard is almost 2018 XD)
Can you please look at .dx model format here, maybe it will look familiar to you and you'll be able to say something about it?

[https://www.dropbox.com/s/bsy8qkctxd5w2 ... M.zip?dl=1](https://www.dropbox.com/s/bsy8qkctxd5w2mx/France_M.zip?dl=1) - Sample level without textures
[https://www.dropbox.com/s/4dbj6fa8lesi4 ... a.zip?dl=1](https://www.dropbox.com/s/4dbj6fa8lesi4d2/Navara.zip?dl=1) - Car model with textures
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-01T23:29:29+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

i don't know about the dx models, i never looked at them, maybe post a thread in 2d/3d models to get more attention?
but all your texture samples work with my script posted above so all is good there.
## Post #12
- Username: romaw
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 05, 2016 11:51 pm
- Post datetime: 2018-11-19T16:00:57+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

> Reply from kovaloid
>
> AceWell, Hi!
I'm trying to get resources from this game too... (yeah, I know that the yard is almost 2018 XD)
Can you please look at .dx model format here, maybe it will look familiar to you and you'll be able to say something about it?

https://www.dropbox.com/s/bsy8qkctxd5w2 ... M.zip?dl=1 - Sample level without textures
https://www.dropbox.com/s/4dbj6fa8lesi4 ... a.zip?dl=1 - Car model with textures DirectX 8.1 SDK - Final Release I remember there were tools to convert some 3d format


now I have all new textures, if you're interested then write in the topic that I would share
## Post #13
- Username: Joel RD
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 05, 2019 1:35 am
- Post datetime: 2019-06-04T17:42:07+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

Still love this game, I'm interested to see what modification could be done
## Post #14
- Username: Joel RD
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 05, 2019 1:35 am
- Post datetime: 2019-06-04T17:48:08+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

> Reply from romaw ↑Tue Nov 20, 2018 12:00 am at Tue Nov 20, 2018 12:00 am
>
> 
kovaloid wrote:AceWell, Hi!
I'm trying to get resources from this game too... (yeah, I know that the yard is almost 2018 XD)
Can you please look at .dx model format here, maybe it will look familiar to you and you'll be able to say something about it?

https://www.dropbox.com/s/bsy8qkctxd5w2 ... M.zip?dl=1 - Sample level without textures
https://www.dropbox.com/s/4dbj6fa8lesi4 ... a.zip?dl=1 - Car model with textures DirectX 8.1 SDK - Final Release I remember there were tools to convert some 3d format


now I have all new textures, if you're interested then write in the topic that I would share

I would like them please!
## Post #15
- Username: romaw
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 05, 2016 11:51 pm
- Post datetime: 2019-06-04T18:04:01+00:00
- Post Title: game MasterRallye 2001  "filename"-tga.dxt

> Reply from Joel RD ↑Wed Jun 05, 2019 1:48 am at Wed Jun 05, 2019 1:48 am
>
> 
romaw wrote: ↑Tue Nov 20, 2018 12:00 am
kovaloid wrote:AceWell, Hi!
I'm trying to get resources from this game too... (yeah, I know that the yard is almost 2018 XD)
Can you please look at .dx model format here, maybe it will look familiar to you and you'll be able to say something about it?

https://www.dropbox.com/s/bsy8qkctxd5w2 ... M.zip?dl=1 - Sample level without textures
https://www.dropbox.com/s/4dbj6fa8lesi4 ... a.zip?dl=1 - Car model with textures DirectX 8.1 SDK - Final Release I remember there were tools to convert some 3d format


now I have all new textures, if you're interested then write in the topic that I would share


I would like them please!
hi, read this is tread [https://www.racedepartment.com/threads/ ... ic.156939/](https://www.racedepartment.com/threads/master-rallye-2001-old-game-nice-physic.156939/)
and [http://dgmag.in/forum/viewtopic.php?id=1901](http://dgmag.in/forum/viewtopic.php?id=1901) (Russian language)
full game with new texture over 4gb space disk , 
[https://www.old-games.ru/game/download/7124.html](https://www.old-games.ru/game/download/7124.html)
