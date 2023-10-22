## Post #1
- Username: JesteR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 09, 2018 10:10 pm
- Post datetime: 2018-10-09T14:40:46+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

Hello world! This is my first post and I need your help!
--
Information regarding the .43 is quite limited being one of the only sites with any information I'm requesting your aid
[viewtopic.php?f=10&t=10401](http://forum.xentax.com/viewtopic.php?f=10&t=10401)
(Side note the converter found on the above thread doesn't appear to work on these .43 models)

After extracting assets from the game "Finn and Jake's Epic Quest" I've hit a bit of a problem; all of the models are in .43 format. I would like to port them over to sfm/vrchat but I'd need a way to convert the models into a decent file type such as a .obj or an .3ds and any help is of great assistance to the efforts!

The file attached contains .43 mesh files for the Ice King and the Flame King. Thank you for your time!
[Adventure Time 43.rar](https://xentaxbackup.github.io/file/14988_Adventure Time 43.rar)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-09T15:32:02+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

Format looks simple. You can find all the necessary info there, including the FVFsizes.



FlameKing_Mesh.jpg (116.65 KiB) Viewed 93 times
## Post #3
- Username: JesteR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 09, 2018 10:10 pm
- Post datetime: 2018-10-10T01:09:00+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

> Reply from Bigchillghost
>
> Format looks simple. You can find all the necessary info there, including the FVFsizes.
The attachment FlameKing_Mesh.jpg is no longer available
I'm having a hard time learning Hex2obj, could you guide me on how to convert these .43 files?
[I'mstupidplzhelp.png](https://xentaxbackup.github.io/file/14994_I'mstupidplzhelp.png)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-10T02:03:46+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

You're using the prams on the wrong file.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-10T03:19:40+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

This's the full structure of the format:



fullStruct.jpg (233.45 KiB) Viewed 76 times
## Post #6
- Username: JesteR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 09, 2018 10:10 pm
- Post datetime: 2018-10-13T15:48:27+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

> Reply from Bigchillghost
>
> This's the full structure of the format:
The attachment fullStruct.jpg is no longer available
I think I get how to use it now thanks to you! However I still lost on how to get the highlighted value
(Using the Ice king File)
[I'mLessStupidNowButStillPrettyStupidtho.png](https://xentaxbackup.github.io/file/15022_I'mLessStupidNowButStillPrettyStupidtho.png)
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-13T16:23:16+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

> Reply from JesteR
>
> 
I think I get how to use it now
Not really. 



Iceking_Meshl.jpg (121.26 KiB) Viewed 58 times


The UV start address is the vertex start offset plus the vertex size. For exmaple the vertex start offset of Iceking_Meshl is 0x10500, while vertex size is 0x10480, so the UV address should be 0x10500 + 0x10480 = 0x20980.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-14T11:57:05+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

Here's a Noesis python script to import the models:


 fmt_FaJEQ_43.rar
(730 Bytes) Downloaded 16 times


Bones are not supported coz there's no parenting info.
## Post #9
- Username: JesteR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 09, 2018 10:10 pm
- Post datetime: 2018-10-14T13:26:20+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

> Reply from Bigchillghost
>
> Here's a Noesis python script to import the models:
fmt_FaJEQ_43.rar
Bones are not supported coz there's no parenting info.
Thank you so much! I'm definitely giving you a shout out on the avatar map when It's finished!
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-10-15T01:38:28+00:00
- Post Title: [Req] Finn and Jake's Epic Quest: .43 file converter

your samples open with finale00's existing 43 Noesis script   
[https://himeworks.com/redirect.php?type ... Unity3D_43](https://himeworks.com/redirect.php?type=noesis&name=Unity3D_43)
linked from here
[http://himeworks.com/noesis-plugins/](http://himeworks.com/noesis-plugins/)

however it is rare to see .43 files these days unless you 
are using an old tool or script for unpacking Unity files.
most use "Asset Studio" or "UABE" to convert the data to usable on the fly.
