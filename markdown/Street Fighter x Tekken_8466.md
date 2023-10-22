## Post #1
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-03T22:17:03+00:00
- Post Title: Street Fighter x Tekken

I'm working on accessing the files on the 360 version... but they're in container files in .awb format... anyone familiar with this? Noesis doesn't seem to be able to recognize it.

edit- .awb seems to be the format for the sound files... while the models, etc seem to be in one large 2 gig file called CMN.eaf
## Post #2
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-03T22:49:08+00:00
- Post Title: Street Fighter x Tekken

so from my research I apparently need Kensou's tool to dump the aef file... but so far I can't find a working link... does anyone have one?
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-03T23:50:30+00:00
- Post Title: Street Fighter x Tekken

[viewtopic.php?p=37288#p37288](http://forum.xentax.com/viewtopic.php?p=37288#p37288)
Here's a quickbms script
By hcs
[http://hcs64.com/files/eaf03.bms](http://hcs64.com/files/eaf03.bms)
## Post #4
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-03T23:54:03+00:00
- Post Title: Street Fighter x Tekken

> Reply from ShiroiKaze
>
> so from my research I apparently need Kensou's tool to dump the aef file... but so far I can't find a working link... does anyone have one?

Try this.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
comtype deflate

idstring "#EAF"

# 0x4 may be file name length

goto 0x10
get file_count long

set idxpos = 0x80
for i = 0 < file_count
    goto idxpos
    get name string
    math idxpos + 0x100
    goto idxpos
    get dummy long
    get offset long
    get size long

    goto offset
    get id long
    if id == 0x23454D5A
        endian little
        get crc long
        get uncompsize long
        get blah long
        endian big

        savepos cdatapos
        math size - 0x10
        clog name cdatapos size uncompsize
    else
        log name offset size
    endif

    math idxpos + 0x20
next i
```


If that thing doesn't work, then here you have, Kensou's tool:

[https://skydrive.live.com/?cid=C59EA3C9 ... 49FCBE!177](https://skydrive.live.com/?cid=C59EA3C98A300F31&id=C59EA3C98A300F31!781#cid=FFBE4E570949FCBE&id=FFBE4E570949FCBE!177)
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-04T00:45:13+00:00
- Post Title: Street Fighter x Tekken

Emb texture file is somewhat different.
## Post #6
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-04T01:01:01+00:00
- Post Title: Street Fighter x Tekken

so with kensou's tool + emo2smd we have already rigged models...

Yey
## Post #7
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-04T02:06:40+00:00
- Post Title: Street Fighter x Tekken

> Reply from dj082502
>
> 
Emb texture file is somewhat different.

No, the structure is the same and those files are multichannel mask textures. After seeing the texture, the red channel is a gray diffuse texture and the other 3 channels (blue,green and alpha channels) are masks controling muliply color layer limits.

So basically, youll have to edit your texture in photohop like scVI-V textures.

Also, there's just one emb per emo object.
## Post #8
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-04T03:46:37+00:00
- Post Title: Street Fighter x Tekken

yup I already managed to rip all the models including alt costumes and the 12 vita fighters... but the texture files are funky colors... almost like a normal map

edit- Oh I see the deal with the texture files... any easy way to convert them?
## Post #9
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-04T04:37:55+00:00
- Post Title: Street Fighter x Tekken

> Reply from ShiroiKaze
>
> yup I already managed to rip all the models including alt costumes and the 12 vita fighters... but the texture files are funky colors... almost like a normal map

edit- Oh I see the deal with the texture files... any easy way to convert them?

It's easy to edit textures, but need some work and patience.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-04T04:44:59+00:00
- Post Title: Street Fighter x Tekken

> No, the structure is the same and those files are multichannel mask textures. After seeing the texture, the red channel is a gray diffuse texture and the other 3 channels (blue,green and alpha channels) are masks controling muliply color layer limits.

What does that mean? And if the red channel is just gray, wouldn't that make it difficult to compute the correct color with only the blue, green, and alpha?

More importantly, how does game use that to properly compute the colors?

What is the procedure to editing the textures, and what makes it difficult to automate it given the information provided?
## Post #11
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-04T04:47:18+00:00
- Post Title: Street Fighter x Tekken

I can see them as separate channels in photoshop... just not sure what to do to fix them. Each character also has a "pandora mode" texture added in the file that also jumbles things up a bit
## Post #12
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-03-04T13:10:17+00:00
- Post Title: Street Fighter x Tekken

Hmm interesting... anyone tried modifying the textures and injecting them back into the .EAF yet to set what happens?

I don't have the game yet so i can't try :O
## Post #13
- Username: emankcin700jp
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 17, 2011 4:36 pm
- Post datetime: 2012-03-05T10:33:29+00:00
- Post Title: Street Fighter x Tekken

Just one question.  Is there any difference between the model use in SF4 and SFxT?  Like for example, the Ryu model?
## Post #14
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-05T15:26:25+00:00
- Post Title: Street Fighter x Tekken

> Reply from emankcin700jp
>
> Just one question.  Is there any difference between the model use in SF4 and SFxT?  Like for example, the Ryu model?

Besides different texture formats when you try to play animation via the SF4 Assets Explorer you get a lot of vertices that flip out... even on characters that were in SF4. The geometry on the models look identical though.
## Post #15
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-05T21:58:30+00:00
- Post Title: Street Fighter x Tekken

> Reply from finale00
>
> No, the structure is the same and those files are multichannel mask textures. After seeing the texture, the red channel is a gray diffuse texture and the other 3 channels (blue,green and alpha channels) are masks controling muliply color layer limits.


What does that mean? And if the red channel is just gray, wouldn't that make it difficult to compute the correct color with only the blue, green, and alpha?

More importantly, how does game use that to properly compute the colors?

What is the procedure to editing the textures, and what makes it difficult to automate it given the information provided?

Have you edited SCIV-V textures by yourself?? It's the same process.

This is how it works:

[http://www.youtube.com/watch?v=ZA0tTKvX ... d7OBi5Uz26](http://www.youtube.com/watch?v=ZA0tTKvXxrs&context=C361e8c6ADOEgsToPDskIsRAMdcpN6yGd7OBi5Uz26)

Thanks Mario for the video.

Edit. it's faster to do that in photosop.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-05T22:07:04+00:00
- Post Title: Re: Street Fighter x Tekken

So there is no way to automate the process?
## Post #17
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-03-05T22:07:55+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from Darko
>
> finale00 wrote:No, the structure is the same and those files are multichannel mask textures. After seeing the texture, the red channel is a gray diffuse texture and the other 3 channels (blue,green and alpha channels) are masks controling muliply color layer limits.


What does that mean? And if the red channel is just gray, wouldn't that make it difficult to compute the correct color with only the blue, green, and alpha?

More importantly, how does game use that to properly compute the colors?

What is the procedure to editing the textures, and what makes it difficult to automate it given the information provided?

Have you edited SCIV-V textures by yourself?? It's the same process.

This is how it works:

http://www.youtube.com/watch?v=ZA0tTKvX ... d7OBi5Uz26

Thanks Mario for the video.

Edit. it's faster to do that in photosop.
What doesn't make sense is that even the skin uses those "masks" It's really weird.
## Post #18
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-09T14:27:00+00:00
- Post Title: Re: Street Fighter x Tekken

I think the transparency masks on the skin are for pandora mode
## Post #19
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2012-03-09T15:38:12+00:00
- Post Title: Re: Street Fighter x Tekken

is there any diference between ps3 and x360 files?
## Post #20
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-03-10T00:19:24+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from ShiroiKaze
>
> I think the transparency masks on the skin are for pandora modeJudging by how they look, yes and no. Some parts use it for the Pandora markings, others use it for transparency.

> Reply from iK1L73r
>
> is there any diference between ps3 and x360 files?Not that I noticed. Other than the fact that the PS3 textures needed to have their DDS headers fixed, both the models and textures appear to be the exact same. At least, from the files I've compared.
## Post #21
- Username: unkoburizou
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 01, 2010 4:47 pm
- Post datetime: 2012-03-10T05:21:20+00:00
- Post Title: Re: Street Fighter x Tekken

> Not that I noticed. Other than the fact that the PS3 textures needed to have their DDS headers fixed, both the models and textures appear to be the exact same. At least, from the files I've compared.
Oh, thanks! PS3 textures worked perfectly
## Post #22
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2012-03-14T06:49:18+00:00
- Post Title: Re: Street Fighter x Tekken

The bms script doesnt work for me, I get an error stating that the there is an invalid datatype on line 14. 

I have managed to extract the files manually using a hex editor though. I'm thinking about adding support in my x-packer application to extract and inject files into the eaf archive. Has anyone succeeded in adding modified files to the archive?
[ryu_tekken.jpg](https://xentaxbackup.github.io/file/5185_ryu_tekken.jpg)
## Post #23
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-17T19:44:19+00:00
- Post Title: Re: Street Fighter x Tekken

I think the reason for the funky colors on the textures in both this game and the Soul Calibur games has to do with that each game has custom colors for every character. There must be some file that adjusts the hues... but the base textures are these funky cyan tones. Anyway I'm just hand coloring the textures in photoshop like suggested... I'm putting together a SFxT parody animation... here's my first test render with Poison's alt costume [http://youtu.be/3IYERjtc4rI](http://youtu.be/3IYERjtc4rI)
## Post #24
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2012-03-17T22:11:27+00:00
- Post Title: Re: Street Fighter x Tekken

Anyone get the .emz files working for like backgrounds and stuff? I've been trying to convert the store background with the SF4 tools, but it's not going so well.
## Post #25
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-18T00:41:42+00:00
- Post Title: Re: Street Fighter x Tekken

the backgrounds don't use .emz files... they're controlled by a series of .lua files in the script folder... as far as I know there's no way to view or extract them properly... I've been trying to get Kunimitsu out of the Mishima background myself
## Post #26
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2012-03-18T00:48:52+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from ShiroiKaze
>
> the backgrounds don't use .emz files... they're controlled by a series of .lua files in the script folder... as far as I know there's no way to view or extract them properly... I've been trying to get Kunimitsu out of the Mishima background myself
Go to the UI folder, then store, then bg. It's an .emz file.
## Post #27
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-18T02:20:25+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from JohnGrimm
>
> ShiroiKaze wrote:the backgrounds don't use .emz files... they're controlled by a series of .lua files in the script folder... as far as I know there's no way to view or extract them properly... I've been trying to get Kunimitsu out of the Mishima background myself
Go to the UI folder, then store, then bg. It's an .emz file.

UI= User Interface... that has nothing to do with the stages. That emz file you're looking for is the background for the dlc store. The stages are in the field folder... each stage has it's own subfolder there. In the subfolders you'll see the vfx folder that does have some emz files... but all vfx are is stuff like smoke and effects in the background. Like I said, the stages are controlled by the .lua files in the script subfolder in each field folder.
## Post #28
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2012-03-18T02:37:46+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from ShiroiKaze
>
> JohnGrimm wrote:ShiroiKaze wrote:the backgrounds don't use .emz files... they're controlled by a series of .lua files in the script folder... as far as I know there's no way to view or extract them properly... I've been trying to get Kunimitsu out of the Mishima background myself
Go to the UI folder, then store, then bg. It's an .emz file.

UI= User Interface... that has nothing to do with the stages. That emz file you're looking for is the background for the dlc store. The stages are in the field folder... each stage has it's own subfolder there. In the subfolders you'll see the vfx folder that does have some emz files... but all vfx are is stuff like smoke and effects in the background. Like I said, the stages are controlled by the .lua files in the script subfolder in each field folder.
I never said anything about the stages. If I meant the stages I would have said stages. Clearly the stages would be 3D models anyways and not an .emz file. In fact, if you look at the first post I made, I even said I was trying to get the background for the store.
## Post #29
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-18T03:27:02+00:00
- Post Title: Re: Street Fighter x Tekken

works fine for me
[store_bg.jpg](https://xentaxbackup.github.io/file/5203_store_bg.jpg)
## Post #30
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2012-03-18T04:00:25+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from ShiroiKaze
>
> works fine for me
What did you use for it? I've been trying BMS scripts all over the place and haven't found one that worked.
## Post #31
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-18T04:06:48+00:00
- Post Title: Re: Street Fighter x Tekken

use the latest version of SF4 Asset Explorer
## Post #32
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2012-03-18T04:10:54+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from ShiroiKaze
>
> use the latest version of SF4 Asset Explorer
Thanks for the help.
## Post #33
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-18T20:55:38+00:00
- Post Title: Re: Street Fighter x Tekken

Has anyone tried to swap SSFIV AE models with sfxtk models??
## Post #34
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-03-18T23:18:19+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from Darko
>
> Has anyone tried to swap SSFIV AE models with sfxtk models??[Someone has, but it's pretty wonky so far](http://i.imgur.com/zi2XO.jpg) since the models aren't aligned the same way as SFIV's.
## Post #35
- Username: ShiroiKaze
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Mar 04, 2012 6:14 am
- Post datetime: 2012-03-23T13:14:30+00:00
- Post Title: Re: Street Fighter x Tekken

Has anyone been able to view or export any of the meshes from the backgrounds? SF4 explorer just gives me a jumbled mess of vertices... maybe there's some bms script to convert them?

update- it seems using v.0.33 of sf4explorer can display and export background meshes... but the UVs or normals are still messed up
## Post #36
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2012-04-13T08:49:56+00:00
- Post Title: Re: Street Fighter x Tekken

I was wondering if it's possible to get Toro, Koro, and/or Cole from the ps3 version of the game. 
If possible could someone send me the raw files? I would do it my self but I have no way of getting the files off of my disk.
## Post #37
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2012-05-07T21:22:51+00:00
- Post Title: Re: Street Fighter x Tekken

im really srry about noob ........ how to use { emo2smd.pl and EMB Extractor.pl } scripts?
## Post #38
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-08T00:40:14+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from lumekano
>
> im really srry about noob ........ how to use { emo2smd.pl and EMB Extractor.pl } scripts?

You need to have perl installed in your pc. The just run emo2smd.pl (double click on it) inside the folder you have your files (in this case your obj.emo file) drag and drop that file inside the command window that has opened and press enter. It'll generate a .smd file which you can import in 3dsmax or blender. The textures just extract them with sf4 assets explorer.

See ya.
## Post #39
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2012-05-27T02:08:37+00:00
- Post Title: Re: Street Fighter x Tekken

Sorry, but what file have texture inside?
## Post #40
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-27T05:12:18+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from grotesque
>
> Sorry, but what file have texture inside?

emb file.
## Post #41
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2012-05-27T10:43:06+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from Darko
>
> grotesque wrote:Sorry, but what file have texture inside?

emb file.

Thanks!
And some tutorial for fix colors?
## Post #42
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-05-28T10:07:29+00:00
- Post Title: Re: Street Fighter x Tekken

How open emo2smd.pl and EMB Extractor.pl o.O?
## Post #43
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-30T04:31:15+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from Kamillho
>
> How open emo2smd.pl and EMB Extractor.pl o.O?

You need to install perl first, then just double click on the file and it'll open a command window, drag and drop your emo file inside that window (to avoid writting the file's name manually) and press enter. That's all.

Someone asked for a tutorial for coloring the difuse texture:



Tomorrow I'm gonna post it.

See ya.
## Post #44
- Username: Carpethop
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Sep 12, 2011 8:02 pm
- Post datetime: 2012-05-31T21:22:58+00:00
- Post Title: Re: Street Fighter x Tekken

Can someone please help with files extraction from PS3 version ? I already extracted all files from  awb file but i cant do anything with extracted files.
## Post #45
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-06-01T05:43:33+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from SuperCheater5
>
> Can someone please help with files extraction from PS3 version ? I already extracted all files from  awb file but i cant do anything with extracted files.AWB files have the sound effects for the characters (which are ADX2/HCA, which hasn't been cracked yet). You'll need to unpack the main file and get the EMO and EMB files for the character models and textures.
## Post #46
- Username: Carpethop
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Sep 12, 2011 8:02 pm
- Post datetime: 2012-06-01T10:52:20+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from RandomTBush
>
> SuperCheater5 wrote:Can someone please help with files extraction from PS3 version ? I already extracted all files from  awb file but i cant do anything with extracted files.AWB files have the sound effects for the characters (which are ADX2/HCA, which hasn't been cracked yet). You'll need to unpack the main file and get the EMO and EMB files for the character models and textures.
I can't extract anything from EMO and EMB files,I tried to extract some files with SF4 Asset Explorer but its not working.
## Post #47
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-06-05T20:15:17+00:00
- Post Title: Re: Street Fighter x Tekken

Does anyone clearly know how to get models and textures of the ps3 version?
Someone ported Cole over to Smash Brawl and well i personally end in nowhere when trying to extract his files =/
## Post #48
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-06-06T16:52:52+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from o0Crofty0o
>
> Does anyone clearly know how to get models and textures of the ps3 version?
Someone ported Cole over to Smash Brawl and well i personally end in nowhere when trying to extract his files =/

Nope, only 360/pc version. I haven't tried and I don't need to.
## Post #49
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2012-06-06T20:39:25+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from o0Crofty0o
>
> Does anyone clearly know how to get models and textures of the ps3 version?
Someone ported Cole over to Smash Brawl and well i personally end in nowhere when trying to extract his files =/

Just use piecemontee SF4 explorer V0.37b to open the ps3 emo and emb files. they work the same way as the 360 version, you just need to fix the dds files headers. I helped the guy fix the textures so if you want them instead of fixing them yourself message me.
## Post #50
- Username: Motumoyo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 12, 2012 9:47 am
- Post datetime: 2012-06-12T05:21:15+00:00
- Post Title: Re: Street Fighter x Tekken

See the texture, the red channel is the mask of a gray diffuse texture and three-channel temperature control muliply color layer limit.
## Post #51
- Username: solidus2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 14, 2012 6:21 am
- Post datetime: 2012-08-14T19:13:29+00:00
- Post Title: Re: Street Fighter x Tekken

Greatings,

I´m having a lot of trouble trying to extract textures from sfxt (both x360 and ps3 version, but i can extract the models).

I´m using sf4 explorer, and can´t ready the emb and emm files (i can open those files, but sf4e doesn´t show anything).


Can someone help me?

Regards
## Post #52
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-08-15T06:07:40+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from solidus2
>
> Greatings,

I´m having a lot of trouble trying to extract textures from sfxt (both x360 and ps3 version, but i can extract the models).

I´m using sf4 explorer, and can´t ready the emb and emm files (i can open those files, but sf4e doesn´t show anything).


Can someone help me?

Regards

Are you changing the endianess option according to the files version you have??
## Post #53
- Username: solidus2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 14, 2012 6:21 am
- Post datetime: 2012-08-16T09:14:39+00:00
- Post Title: Re: Street Fighter x Tekken

> Reply from Darko
>
> 

Are you changing the endianess option according to the files version you have??

Greatings,

Yes, I´ve  change the endianess. but still can´t extract or view the textures.
## Post #54
- Username: wajahat122
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 19, 2012 10:25 pm
- Post datetime: 2012-08-23T12:11:47+00:00
- Post Title: Re: Street Fighter x Tekken

can anyone khnown how to convert sxft emo,emm to any other format
like
obj, tga or any other
## Post #55
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2016-10-13T10:47:30+00:00
- Post Title: Re: Street Fighter x Tekken

hi everyone
i need some help since i m completely noob on those things
i m trying to unpack the CMN.eaf fil eof the psvita version but i get error using the bms script found in this thread
can someone help me fixing the script?
thanks in advance


attached is the img of the ps3 eaf with the working script on the left and the vita eaf on the right (which need a script fix)

sorry for my bad english
[final.jpg](https://xentaxbackup.github.io/file/11787_final.jpg)
## Post #56
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-13T19:51:01+00:00
- Post Title: Re: Street Fighter x Tekken

from your screenshot it looks like the main difference is the endianess,
maybe comment out the line where it says "endian big" with a "#" and try it again
## Post #57
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2016-10-14T06:40:55+00:00
- Post Title: Re: Street Fighter x Tekken

thankyou for your help   

now the script unpack the CMN.eaf but ive noticed a problem

every single file extracted has a different lenght but viewing them in a hex editor looks the same and with a EAF header  
[x.jpg](https://xentaxbackup.github.io/file/11790_x.jpg)
