## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-09T08:14:33+00:00
- Post Title: Tales of Crestoria Tools

File formats are similar to Star Ocean, but I still wanted to open a new thread, since they are different games and I will be managing the tools separately.

Decompress / Extract Files
All the files seem to be compressed. Use this tool for decompressing first : [TOCDec Tool](http://www.mediafire.com/file/wrdguiic65fwdlh/TOCDec.rar/file) Drag and drop a folder on to the exe file and it will try to decompress all the files inside.

If the file you want is in a mpk container (character/monster stuff), use the attached bms script in this post below to extract them.

3D Models
The tool supports models (.asf). I will need some time to work on animations. You can still load some SOA animations on to these models. The skeleton structure appears to be similar.



How to use
- Select the model file (.asf) you want to load.
- Use Offset :  Will be unchecked by default, you probably won't need it. If the meshes are misaligned with the skeleton try checking it.

SOA animations ONLY
- Select the animation file (.apk) you want to load.
- If the file contains multiple animations, you will see arrows to go to the next/previous animation.
- Animate Position :  Will be unchecked by default. It is easier to preview the animations this way. You can check this before exporting if you need to have position keys in the animation.

- Export NEXS :  Exports the model in a custom format to be loaded in Noesis. Supports animations. Noesis import script : [Nexs Script](https://www.mediafire.com/file/exu7446rh5qzr64/fmt_Nexs.py/file)
- Export IQE :  Exports the model in IQE format. How to open/convert IQE: [IQE Guide](http://forum.xentax.com/viewtopic.php?p=138153#p138153) New script with secondary uv support : [IQE Script](http://forum.xentax.com/viewtopic.php?p=143565#p143565)
Note  : Models will be exported into the folder Export.

Download :  [https://www.mediafire.com/file/slnyl8fd ... 1.rar/file](https://www.mediafire.com/file/slnyl8fdt60ospz/TOCViewer_U1.rar/file)

Textures
Finally a tool for extracting images from asf/aif files: [TOCImgEx Tool](http://www.mediafire.com/file/0onlmxpvoj0hyxe/TOCImgEx.rar/file) Drag and drop the file on to the exe. You can open the extracted ktx with Mali Texture Compression Tool or PVRTextool.
[toc_mpk_unp.rar](https://xentaxbackup.github.io/file/18110_toc_mpk_unp.rar)
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-05-09T10:22:22+00:00
- Post Title: Tales of Crestoria Tools

Thank you for developing and sharing the tool!
It's working fine!
[toc.png](https://xentaxbackup.github.io/file/18111_toc.png)
## Post #3
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2020-05-12T03:16:42+00:00
- Post Title: Tales of Crestoria Tools

Thank you so much for the tools!!

I noticed a few of the models had UV issues.
The ones I've noticed so far are cp3007_01a, cp1604_01a, and cp1202_01a
If you don't have those files, I can send them to you if you're willing to look into it.

Thanks!
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-12T08:27:24+00:00
- Post Title: Tales of Crestoria Tools

> Reply from anime663 ↑Tue May 12, 2020 11:16 am at Tue May 12, 2020 11:16 am
>
> 
I noticed a few of the models had UV issues.
Thanks for reporting, fixed it now. I will include it in the next release.
## Post #5
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-13T12:00:44+00:00
- Post Title: Tales of Crestoria Tools

einherjar007 send me this Tales of Crestoria rar.rar file  do I  need something else with this because I do not have it.
## Post #6
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-05-13T13:35:02+00:00
- Post Title: Tales of Crestoria Tools

> Reply from blacknight411 ↑Wed May 13, 2020 8:00 pm at Wed May 13, 2020 8:00 pm
>
> 
einherjar007 send me this Tales of Crestoria rar.rar file  do I  need something else with this because I do not have it.

you just decompress the rar file.
## Post #7
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-13T16:20:28+00:00
- Post Title: Tales of Crestoria Tools

I drag the rar file in  decompress  and  have error problem.
## Post #8
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-13T16:54:00+00:00
- Post Title: Tales of Crestoria Tools

ok find the problem delete the last words
## Post #9
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-14T03:37:33+00:00
- Post Title: Tales of Crestoria Tools

how  to  export the model  and texture to noesis.
## Post #10
- Username: RedToaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 13, 2020 8:17 am
- Post datetime: 2020-05-16T08:28:03+00:00
- Post Title: Tales of Crestoria Tools

Awesome work on the tools!

However I found that weapon model - wp0201_01a - to have broken UVs
And a few characters with broken UV bits but a user already mentioned them in the topic!
## Post #11
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2020-05-17T20:17:06+00:00
- Post Title: Tales of Crestoria Tools

Just here to thank you for the tool, looking forward to the full game being released. ^-^

Hope the UV map issue is sorted, only come across one model with issues, but otherwise everything else works perfectly fine. Also thank you for the Star Ocean tool, appreciate that one greatly.
## Post #12
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2020-05-23T00:33:23+00:00
- Post Title: Tales of Crestoria Tools

That's an amazing tool but how would I get the character models from the game?
## Post #13
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2020-05-23T11:32:30+00:00
- Post Title: Tales of Crestoria Tools

Its self explanatory really, you gotta extract the files, which you can't do at the moment due to the beta ending. So you gotta wait for the full game to release next month (I believe).
## Post #14
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2020-05-23T12:44:16+00:00
- Post Title: Tales of Crestoria Tools

> Reply from Andelx ↑Sat May 23, 2020 7:32 pm at Sat May 23, 2020 7:32 pm
>
> 
Its self explanatory really, you gotta extract the files, which you can't do at the moment due to the beta ending. So you gotta wait for the full game to release next month (I believe).

Okay. I’ll wait for the full game to come out. I’m hoping to get the character models from Tales of Zestiria and Tales of Berseria in that game.
## Post #15
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-24T06:30:57+00:00
- Post Title: Tales of Crestoria Tools

Some of the characters  has  export hair problems.
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-24T07:30:18+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from blacknight411 ↑Sun May 24, 2020 2:30 pm at Sun May 24, 2020 2:30 pm
>
> 
Some of the characters  has  export hair problems.

"Problems" doesn't tell me enough  What is the problem related to? Maybe a screenshot or some more description in general.
## Post #17
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2020-05-24T09:51:16+00:00
- Post Title: Re: Tales of Crestoria Tools

The issue he is talking about is that some hairs from my experience don't port with proper UV maps. I found a few models with the problem, here is one of them. (Estelle from ToV)

[https://mega.nz/file/SQUHUCjY#eX6bipyib ... 8rp59jbzkg](https://mega.nz/file/SQUHUCjY#eX6bipyibMNRiDEwD4iATi1lyNJifLva08rp59jbzkg)
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-24T10:05:42+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from Andelx ↑Sun May 24, 2020 5:51 pm at Sun May 24, 2020 5:51 pm
>
> 
The issue he is talking about is that some hairs from my experience don't port with proper UV maps.
Thanks. I already fixed that UV issue, just haven't released it yet.
## Post #19
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2020-05-24T19:11:39+00:00
- Post Title: Re: Tales of Crestoria Tools

I thought as much, just felt I would clarify. ^-^
## Post #20
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-25T04:13:06+00:00
- Post Title: Re: Tales of Crestoria Tools

I,am  looking for Machina do anyone have her.
## Post #21
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2020-05-25T17:39:40+00:00
- Post Title: Re: Tales of Crestoria Tools

If she isn't in the beta files, then nobody will have her, just wait until the game is released and extract the files from that.
## Post #22
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-06-02T20:26:56+00:00
- Post Title: Re: Tales of Crestoria Tools

Any progress on the animation files?
## Post #23
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-03T11:07:08+00:00
- Post Title: Re: Tales of Crestoria Tools

Updated the first post with a link to the new version. Just fixes the uv issue that was reported.

> Reply from andree ↑Wed Jun 03, 2020 4:26 am at Wed Jun 03, 2020 4:26 am
>
> 
Any progress on the animation files?

Probably not anytime soon. It isn't too hard, but I am working on other formats atm. Maybe some time later.
## Post #24
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-06-04T23:31:24+00:00
- Post Title: Re: Tales of Crestoria Tools

Ok problem is some mesh will not export in blender like pmd,pmx. If you just export the hair mesh you get a error.
## Post #25
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2020-06-29T12:38:19+00:00
- Post Title: Re: Tales of Crestoria Tools

What I do is that I extract the nexs file in Noesis and convert it to generic_item.mesh.ascii (need plugin for Noesis) then take the generic_item.mesh.ascii file you created, convert it to fbx, and then you can load it in blender and it'll work fine. Probably an easier way to get the files into blender but that's the method that I found.
## Post #26
- Username: ElementalLight
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 12, 2017 5:06 pm
- Post datetime: 2020-07-17T02:46:02+00:00
- Post Title: Re: Tales of Crestoria Tools

Hi there first of all thank you for making these tools it is a great asset to be able to view the files in crestoria but as a general question upon the full release they removed alot of files from the download but these are still able to be found on the download server 
i.e Dhaos ( [https://gl-prod-asset.crestoria.channel ... 107_01.aif](https://gl-prod-asset.crestoria.channel.or.jp/Android/UI/IMAGE/ch_vp_full_0107_01.aif) ) but the decoder is unable to be ran on the file it just gives an error is there any way that these files can be ran through the decoder?
## Post #27
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-07-17T04:40:17+00:00
- Post Title: Re: Tales of Crestoria Tools

mpk.bms error
[1.png](https://xentaxbackup.github.io/file/18488_1.png)
## Post #28
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-07-17T04:49:32+00:00
- Post Title: Re: Tales of Crestoria Tools

mpk file
[cm2201_02a.zip](https://xentaxbackup.github.io/file/18489_cm2201_02a.zip)
## Post #29
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-07-17T05:56:32+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from bymutou ↑Fri Jul 17, 2020 12:40 pm at Fri Jul 17, 2020 12:40 pm
>
> 
mpk.bms error

need use TOCDec Tool.
Put the mpk file in the folder and drag it to TOCDec.
## Post #30
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-07-17T09:26:31+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from einherjar007 ↑Fri Jul 17, 2020 1:56 pm at Fri Jul 17, 2020 1:56 pm
>
> 
bymutou wrote: ↑Fri Jul 17, 2020 12:40 pm
mpk.bms error


need use TOCDec Tool.
Put the mpk file in the folder and drag it to TOCDec.

thank you
## Post #31
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-17T10:16:05+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from ElementalLight ↑Fri Jul 17, 2020 10:46 am at Fri Jul 17, 2020 10:46 am
>
> 
but the decoder is unable to be ran on the file it just gives an error is there any way that these files can be ran through the decoder?
Works fine. First TOCDec, then TOCImgEx.
## Post #32
- Username: ElementalLight
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 12, 2017 5:06 pm
- Post datetime: 2020-07-17T15:22:50+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from akderebur ↑Fri Jul 17, 2020 6:16 pm at Fri Jul 17, 2020 6:16 pm
>
> 
ElementalLight wrote: ↑Fri Jul 17, 2020 10:46 am
but the decoder is unable to be ran on the file it just gives an error is there any way that these files can be ran through the decoder?

Works fine. First TOCDec, then TOCImgEx.

alright managed to get it working aswell it seems when i dragged the aif to the decoder for some reason it wouldn't work and needs to be a folder drag or something but i did get it working glad to know it was just me being dumb
## Post #33
- Username: shirokarasu
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 27, 2020 3:51 pm
- Post datetime: 2020-07-19T03:44:11+00:00
- Post Title: Re: Tales of Crestoria Tools

Excuse me,
Tools can`t open latest 3Dmodel & texture...
## Post #34
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-07-22T15:58:06+00:00
- Post Title: Re: Tales of Crestoria Tools

Is there anyone nice could kindly share me with the game file? Not the .apk but the data file that contains models.
Due to the political issue, I am not able to have access to this game but I really want it! 
Thanks in advance,guys! 
---------------------------------------------------------------------------------------------------------------------------------------------

Fixed! Thanks for einherjar007 sending me the files!!!
## Post #35
- Username: shirokarasu
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 27, 2020 3:51 pm
- Post datetime: 2020-07-23T20:17:34+00:00
- Post Title: Re: Tales of Crestoria Tools

I used TOCDec to Character folder
↓
I used Quickbms with toc_mpk_unp.bms to these files.
↓
I used TOCImgEx and ToC viewer
but I can`t open latest 3D models and textures...
displayed error !
Is there anything wrong with this procedure ?
## Post #36
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2020-07-23T21:49:50+00:00
- Post Title: Re: Tales of Crestoria Tools

Did anyone extract all the characters files from Tales of Crestoria? I’m looking for the characters from Tales of Zestiria and Tales of Berseria.
## Post #37
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-23T22:17:59+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from shirokarasu ↑Fri Jul 24, 2020 4:17 am at Fri Jul 24, 2020 4:17 am
>
> 
Is there anything wrong with this procedure ?
It is easy to understand based on output files you get in every step. If you get "_unpack.mpk" files, you did TOCDec right. If you get asf/aif files, you did bms right. After this if you can't load the asf/aif files, pm me one and I will take a look.
## Post #38
- Username: shirokarasu
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 27, 2020 3:51 pm
- Post datetime: 2020-07-24T06:35:35+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from akderebur ↑Fri Jul 24, 2020 6:17 am at Fri Jul 24, 2020 6:17 am
>
> 
shirokarasu wrote: ↑Fri Jul 24, 2020 4:17 am
Is there anything wrong with this procedure ?

It is easy to understand based on output files you get in every step. If you get "_unpack.mpk" files, you did TOCDec right. If you get asf/aif files, you did bms right. After this if you can't load the asf/aif files, pm me one and I will take a look.

I found out why the 3D model files could not be opened.
The all decoding seemed to be successful.
It seems that each file and folder name has to be "exactly the same" to open 3D models.
and yet  I couldn`t  open texture files(ktx) with PVRTexTool.
I couldn`t decode texture files with TOCImgEx ?
## Post #39
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-07-31T08:13:19+00:00
- Post Title: Re: Tales of Crestoria Tools

Really appreciate your lovely tool!
I'm doing rendering while I found that wp3003_01a.asf doesn't have UVs. I try to exported it into.iqe and .nexs but still go nowhere.
Would you mind taking a look for this at your convenience?
Thanks!
## Post #40
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-01T12:34:23+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from Kanbara ↑Fri Jul 31, 2020 4:13 pm at Fri Jul 31, 2020 4:13 pm
>
> 
Could you mind taking a look for this at your convenience?
I will take a look when I have the time.
## Post #41
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-08-01T12:37:27+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from akderebur ↑Sat Aug 01, 2020 8:34 pm at Sat Aug 01, 2020 8:34 pm
>
> 
Kanbara wrote: ↑Fri Jul 31, 2020 4:13 pm
Could you mind taking a look for this at your convenience?

I will take a look when I have the time.

Thanks for you relies!
No worries, just take your time
## Post #42
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-10-09T16:46:04+00:00
- Post Title: Re: Tales of Crestoria Tools

Had you started working on the animation formats yet?
## Post #43
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-23T02:53:21+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from einherjar007 ↑Sat May 09, 2020 6:22 pm at Sat May 09, 2020 6:22 pm
>
> 
Thank you for developing and sharing the tool!
It's working fine!

How can add Textures to a Model via Noesis?I convert  .kts files to png and dds files,but they don't work.
## Post #44
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-10-24T14:22:12+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from kaimuangel ↑Fri Oct 23, 2020 10:53 am at Fri Oct 23, 2020 10:53 am
>
> 
How can add Textures to a Model via Noesis?I convert  .kts files to png and dds files,but they don't work.

This is a preview image of other 3D software, not Noesis. Please check the texture settings as they differ depending on the software.
For image files, you can convert ktx to png with PVRtextool. I tested it with the latest files as of now and everything worked fine.
## Post #45
- Username: Goodmen675
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 15, 2020 11:22 am
- Post datetime: 2020-10-24T21:56:07+00:00
- Post Title: Re: Tales of Crestoria Tools

I put the mpk in a folder then tried decoding it, but it wouldn't work. I don't know why this is happening.
## Post #46
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-10-25T01:35:50+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from Goodmen675 ↑Sun Oct 25, 2020 5:56 am at Sun Oct 25, 2020 5:56 am
>
> 
I put the mpk in a folder then tried decoding it, but it wouldn't work. I don't know why this is happening.

It worked when I tried it yesterday. So there should be no problem with the latest file.
It may not work if the path to the folder contains 2byte characters or Unicode.
## Post #47
- Username: CElledge
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 11, 2020 7:55 pm
- Post datetime: 2020-10-27T01:50:56+00:00
- Post Title: Re: Tales of Crestoria Tools

Look I need help. I read this forum through and through. I saw peoples problems and tried to relate them to my own and work my way through them. In the end I just cannot figure this out. Would someone PLEASE be willing to help me step by step beginning to end. I am trying to extract the 3d models and textures so I can animate them and so on so forth. I don't care if you help me through this or my discord at CElledge#1103. Thank you if you read this. Also could you please let me know what resources I needed to download. Because I had to google the BMS tool myself. So I don't even know if everything I need is on this forum.
## Post #48
- Username: Goodmen675
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 15, 2020 11:22 am
- Post datetime: 2020-10-27T03:39:38+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from einherjar007 ↑Sun Oct 25, 2020 9:35 am at Sun Oct 25, 2020 9:35 am
>
> 
Goodmen675 wrote: ↑Sun Oct 25, 2020 5:56 am
I put the mpk in a folder then tried decoding it, but it wouldn't work. I don't know why this is happening.


It worked when I tried it yesterday. So there should be no problem with the latest file.
It may not work if the path to the folder contains 2byte characters or Unicode.

Is there a particular 3rd party program that needs to be used because I can't open the bms file; maybe that's my problem.  I would like to know all the necessary program and files that'll help me get these models.
## Post #49
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-10-27T09:47:32+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from Goodmen675 ↑Tue Oct 27, 2020 11:39 am at Tue Oct 27, 2020 11:39 am
>
> 
Is there a particular 3rd party program that needs to be used because I can't open the bms file

Quickbms
## Post #50
- Username: Goodmen675
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 15, 2020 11:22 am
- Post datetime: 2020-10-28T01:02:45+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from akderebur ↑Tue Oct 27, 2020 5:47 pm at Tue Oct 27, 2020 5:47 pm
>
> 

Quickbms

Okay, I got quickbms, so how do I use it to extract the models?
## Post #51
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-10-28T02:45:12+00:00
- Post Title: Re: Tales of Crestoria Tools

1.mpk decrypt(TOCDec Tool)
2.mpk extract(quickbms,toc_mpk_unp.bms)
3.open the model(TOCViewer) , extract the texture(TOCImgEx Tool)

so easy.
*Please note that it may not work if the file path contains 2byte characters or Unicode.
## Post #52
- Username: Goodmen675
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 15, 2020 11:22 am
- Post datetime: 2020-10-28T04:34:30+00:00
- Post Title: Re: Tales of Crestoria Tools

The Result
[Screenshot (174).png](https://xentaxbackup.github.io/file/18915_Screenshot (174).png)
## Post #53
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-10-28T05:02:36+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from Goodmen675 ↑Wed Oct 28, 2020 12:34 pm at Wed Oct 28, 2020 12:34 pm
>
> 
The Result

I don't know the exact thing, but I see the message "The directory name is invalid."
You need to put the mpk file in a folder and drag and drop the folder into TOCDec. If you drag and drop *.mpk directly, it will not work.
## Post #54
- Username: Goodmen675
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 15, 2020 11:22 am
- Post datetime: 2020-10-28T19:19:33+00:00
- Post Title: Re: Tales of Crestoria Tools

I recognize my issue now; that's because I thought the bms file had the models in it when isn't the case.  All I need to know now is where can I get the mpk files?
## Post #55
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-10-29T01:29:09+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from Goodmen675 ↑Thu Oct 29, 2020 3:19 am at Thu Oct 29, 2020 3:19 am
>
> 
I recognize my issue now; that's because I thought the bms file had the models in it when isn't the case.  All I need to know now is where can I get the mpk files?

Since this is a mobile game, you need a device or emulator that can get the data. The emulator can be started with the 64-bit version of bluestacks. 
And since this game keeps the data in the root directory, rooting is also required.
Device and rooting are not the specialty of this forum, so please check for yourself.
## Post #56
- Username: Atlus
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 31, 2021 5:52 pm
- Post datetime: 2021-05-21T04:26:17+00:00
- Post Title: Re: Tales of Crestoria Tools

Any progress of the updating of the tools that support animations?
## Post #57
- Username: Atlus
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 31, 2021 5:52 pm
- Post datetime: 2021-05-26T11:35:14+00:00
- Post Title: Re: Tales of Crestoria Tools

Any update please????   

also support for tales of berseria and zesteria please
## Post #58
- Username: itinerare
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 29, 2021 1:28 am
- Post datetime: 2021-06-28T18:36:22+00:00
- Post Title: Re: Tales of Crestoria Tools

Hello! I've been trying to grapple with the game's .ipk files and encountering difficulty... the utility here extracts one of what I'm guessing are several textures, given both that more appear in-game and the size of the .ipk is much larger than the current texture output (which isn't the case for textures extracted from the game's .aif files). Presumably it can be done, as I've seen what have to be the contents of a few of the .ipk files around, but none of my searching has turned up any leads as to how. If anyone has any insight it would be much appreciated!
## Post #59
- Username: DobleC
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 17, 2021 4:21 pm
- Post datetime: 2021-07-17T10:16:33+00:00
- Post Title: Re: Tales of Crestoria Tools

I've exported one weapon texture and model, the model looks perfect, but I don't know how to apply the textures to it, I don't know if I'm exporting them wrong or if exporting the model breaks the uvs, any help?

[Screenshots](https://imgur.com/a/1O55NSk)
## Post #60
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-07-17T11:22:38+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from DobleC ↑Sat Jul 17, 2021 6:16 pm at Sat Jul 17, 2021 6:16 pm
>
> 
I've exported one weapon texture and model, the model looks perfect, but I don't know how to apply the textures to it, I don't know if I'm exporting them wrong or if exporting the model breaks the uvs, any help?

Screenshots

You need to export/extract textures and apply manually. Weapons tho are known for not having correct uvs lot of times, characters should be fine tho
## Post #61
- Username: DobleC
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 17, 2021 4:21 pm
- Post datetime: 2021-07-17T16:21:43+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from Makoto ↑Sat Jul 17, 2021 7:22 pm at Sat Jul 17, 2021 7:22 pm
>
> 
DobleC wrote: ↑Sat Jul 17, 2021 6:16 pm
[...]


You need to export/extract textures and apply manually. Weapons tho are known for not having correct uvs lot of times, characters should be fine tho

Yup, all UVs appear in a tiny spot on the weapon, is there a known solution to this problem?
## Post #62
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-07-20T13:38:43+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from DobleC ↑Sun Jul 18, 2021 12:21 am at Sun Jul 18, 2021 12:21 am
>
> 
Makoto wrote: ↑Sat Jul 17, 2021 7:22 pm
DobleC wrote: ↑Sat Jul 17, 2021 6:16 pm
[...]


You need to export/extract textures and apply manually. Weapons tho are known for not having correct uvs lot of times, characters should be fine tho


Yup, all UVs appear in a tiny spot on the weapon, is there a known solution to this problem?
Not that i know of
## Post #63
- Username: fulanito
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 30, 2021 7:22 pm
- Post datetime: 2021-07-26T22:01:47+00:00
- Post Title: Re: Tales of Crestoria Tools

Does anyone have successfully get the animations working through the ToCviewer, noesis plugin or blender addon?
## Post #64
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-07-26T23:31:19+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from boruken ↑Tue Jul 27, 2021 6:01 am at Tue Jul 27, 2021 6:01 am
>
> 
Does anyone have successfully get the animations working through the ToCviewer, noesis plugin or blender addon?
Not supported.
This game is a so simple game, the quality of the model is good, but the quality of the animation is not good. 
Would you like to use TALES OF THE RAYS or anime from other games?
## Post #65
- Username: fulanito
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 30, 2021 7:22 pm
- Post datetime: 2021-07-27T02:18:06+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from einherjar007 ↑Tue Jul 27, 2021 7:31 am at Tue Jul 27, 2021 7:31 am
>
> 
boruken wrote: ↑Tue Jul 27, 2021 6:01 am
Does anyone have successfully get the animations working through the ToCviewer, noesis plugin or blender addon?

Not supported.
This game is a so simple game, the quality of the model is good, but the quality of the animation is not good. 
Would you like to use TALES OF THE RAYS or anime from other games?

I would like to use tales of the rays or anim from other games (mostly TALES OF THE RAYS). Can you help me?
## Post #66
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-07-27T05:30:42+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from boruken ↑Tue Jul 27, 2021 10:18 am at Tue Jul 27, 2021 10:18 am
>
> 
I would like to use tales of the rays or anim from other games (mostly TALES OF THE RAYS). Can you help me?

TALES OF THE RAYS is a Unity game, so you can extract anime with Asset Studio.
All you need to learn is animation retargeting. They are not covered in this thread or forum. You need to learn software such as blender.
## Post #67
- Username: iloverdc22
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 21, 2020 2:56 pm
- Post datetime: 2021-09-17T16:22:11+00:00
- Post Title: Re: Tales of Crestoria Tools

Somehow i cant import the .iqe file to blender anymore and got this error in the pic. Any reason why ??
[https://i.imgur.com/HzzXgif.png](https://i.imgur.com/HzzXgif.png)
## Post #68
- Username: iloverdc22
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 21, 2020 2:56 pm
- Post datetime: 2021-12-07T19:12:21+00:00
- Post Title: Re: Tales of Crestoria Tools

No matter what i do. i cant import the .iqe file to blender or even noesis
can someone help me with this ?
## Post #69
- Username: eLTeh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 27, 2021 11:43 am
- Post datetime: 2021-12-09T06:02:02+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from iloverdc22 ↑Wed Dec 08, 2021 3:12 am at Wed Dec 08, 2021 3:12 am
>
> 
No matter what i do. i cant import the .iqe file to blender or even noesis
can someone help me with this ?

I'm using Blender 2.93, and this is the edited script I'm using. Not sure if it'll fix the problem, but hopefully it works for you
[iqe_import.zip](https://xentaxbackup.github.io/file/21356_iqe_import.zip)
## Post #70
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-12-09T06:22:59+00:00
- Post Title: Re: Tales of Crestoria Tools

Since Tales of Crestoria is getting shut down by feb 2022, had anyone have the files of the game backed up?
## Post #71
- Username: iloverdc22
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 21, 2020 2:56 pm
- Post datetime: 2021-12-12T14:23:08+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from andree ↑Thu Dec 09, 2021 2:22 pm at Thu Dec 09, 2021 2:22 pm
>
> 
Since Tales of Crestoria is getting shut down by feb 2022, had anyone have the files of the game backed up?

Here you go [https://mega.nz/folder/b48QhQ7I#tXib5d_Mxj-m18O_YD-VwQ](https://mega.nz/folder/b48QhQ7I#tXib5d_Mxj-m18O_YD-VwQ)
## Post #72
- Username: iloverdc22
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 21, 2020 2:56 pm
- Post datetime: 2021-12-12T14:24:08+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from eLTeh ↑Thu Dec 09, 2021 2:02 pm at Thu Dec 09, 2021 2:02 pm
>
> 
iloverdc22 wrote: ↑Wed Dec 08, 2021 3:12 am
No matter what i do. i cant import the .iqe file to blender or even noesis
can someone help me with this ?


I'm using Blender 2.93, and this is the edited script I'm using. Not sure if it'll fix the problem, but hopefully it works for you

I can open it using Noesis with plugins. Thx for replying anyway.
## Post #73
- Username: SafiraThePanther
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 16, 2021 8:25 am
- Post datetime: 2021-12-16T04:13:17+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from eLTeh ↑Thu Dec 09, 2021 2:02 pm at Thu Dec 09, 2021 2:02 pm
>
> 
iloverdc22 wrote: ↑Wed Dec 08, 2021 3:12 am
No matter what i do. i cant import the .iqe file to blender or even noesis
can someone help me with this ?


I'm using Blender 2.93, and this is the edited script I'm using. Not sure if it'll fix the problem, but hopefully it works for you

I was trying to archive some specific textured and rigged 3D assets since the game is shutting down, but I've been having difficulties with the IQE format. No matter which variant or edit or version of the import script I get my hands on, I always run into the same issue whenever I try to import one into blender, despite using the same version as you (unless 2.93.7 matters compared to just 2.93? But I couldn't find that exact version)
It's driving me nuts, I have no idea how to get it to work

[https://imgur.com/a/TAE3l5g](https://imgur.com/a/TAE3l5g)

And as if blender not cooperating wasn't enough, Noesis is also no help, as whenever I try and load one of my exported IQE format characters, I'm met with errors such as "this file cannot be previewed" which totally blocks me from converting the file into a more useable format (my choice would be FBX)
I'm at 7 hours doing this and losing my mind, can one of you more knowledgeable people help me figure this out?
## Post #74
- Username: SafiraThePanther
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 16, 2021 8:25 am
- Post datetime: 2021-12-16T04:14:27+00:00
- Post Title: Re: Tales of Crestoria Tools

> Reply from iloverdc22 ↑Sun Dec 12, 2021 10:24 pm at Sun Dec 12, 2021 10:24 pm
>
> 
eLTeh wrote: ↑Thu Dec 09, 2021 2:02 pm
iloverdc22 wrote: ↑Wed Dec 08, 2021 3:12 am
No matter what i do. i cant import the .iqe file to blender or even noesis
can someone help me with this ?


I'm using Blender 2.93, and this is the edited script I'm using. Not sure if it'll fix the problem, but hopefully it works for you


I can open it using Noesis with plugins. Thx for replying anyway.

As seen in my above post, I'm having massive issues with the .iqe files as well, how did you solve this? I can't seem to find a plugin that works on Noesis either
## Post #75
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-12-16T05:36:32+00:00
- Post Title: Re: Tales of Crestoria Tools

Why should use *.iqe? Is it useless with *.nexs?
## Post #76
- Username: alwayspink
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 17, 2021 1:43 am
- Post datetime: 2021-12-18T02:00:35+00:00
- Post Title: Re: Tales of Crestoria Tools

Wondering if anyone knows how to extract the text strings from this game? I've already got all the audio converted but I'd like the actual text to go with it, especially so for the non voiced scenes. I've checked through the main files but I'm not sure how to get it out properly.
## Post #77
- Username: iloverdc22
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 21, 2020 2:56 pm
- Post datetime: 2021-12-19T05:00:39+00:00
- Post Title: Re: Tales of Crestoria Tools

Any idea where to look to rip the map models of crestoria ?
## Post #78
- Username: BoxCatter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 26, 2021 1:22 pm
- Post datetime: 2021-12-20T03:39:37+00:00
- Post Title: Re: Tales of Crestoria Tools

Upon trying to use TOCDec on the contents of the BG folder (which contains the 3D environments seen in battle and elsewhere), it only works on a portion of the files and the rest throw an error message, which I managed to grab a screenshot of before it auto-closes:



error message error.png (17.93 KiB) Viewed 120 times
## Post #79
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-03-23T15:08:46+00:00
- Post Title: Re: Tales of Crestoria Tools

How did you guys extract the character textures? I'm having trouble doing it.
