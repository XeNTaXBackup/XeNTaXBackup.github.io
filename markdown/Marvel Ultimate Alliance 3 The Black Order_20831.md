## Post #1
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-07-18T13:51:33+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

So pretty much a game that's by Koei Tecmo, which uses G1T for textures, and most likely G1M for models, but I need help here, as the files are all compressed, and judging from the file extensions, might be ZL (zlib) compression?

Uploaded some files for some people to look at
[https://mega.nz/#F!lo0E0ADK!HaQgRSh8bQGJTaHcborCsQ](https://mega.nz/#F!lo0E0ADK!HaQgRSh8bQGJTaHcborCsQ)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-18T15:43:42+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

Here. Quickbms script for decompressing them.

```
get TotLen long
putvarchr MEMORY_FILE TotLen 0
log MEMORY_FILE 0 0
append
Do
get ChunkLen long
SavePos OFFSET
clog MEMORY_FILE OFFSET ChunkLen 10000000
math OFFSET + CHUNKLEN
goto OFFSET
get ChunkLen long
goto -4 0 SEEK_CUR
While ChunkLen > 0
append
get MEM_SIZE asize MEMORY_FILE
log BNAME 0 MEM_SIZE MEMORY_FILE

```
## Post #3
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-07-18T18:28:46+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

deleted
## Post #4
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-07-18T22:35:08+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

> Reply from akderebur ↑Thu Jul 18, 2019 11:43 pm at Thu Jul 18, 2019 11:43 pm
>
> 
Here. Quickbms script for decompressing them.
Code: Select allget BNAME basename
get TotLen long
putvarchr MEMORY_FILE TotLen 0
log MEMORY_FILE 0 0
append
Do
get ChunkLen long
SavePos OFFSET
clog MEMORY_FILE OFFSET ChunkLen 10000000
math OFFSET + CHUNKLEN
goto OFFSET
get ChunkLen long
goto -4 0 SEEK_CUR
While ChunkLen > 0
append
get MEM_SIZE asize MEMORY_FILE
log BNAME 0 MEM_SIZE MEMORY_FILE

thanks, works like a charm! Daemon1 tool extracts the textures just fine, but doesn't seem like it grabs the models even tho there's G1M inside the file.

Edit: via editing the base game file via hex, I was only able to extract the bones.

> 

Edit2: Added more files to the link in the first post, Iron Man for example has a lot of tables in his model file, while Black Panther's texture has 2 textures that exports all broken.
## Post #5
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-07-19T07:53:18+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

If you manually cut out the G1M then daemon's tool works okay on most models. Anything with cloth/physics won't work though, it uses the same physics format as DOA6 and that hasn't been fixed yet.
## Post #6
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-07-19T09:50:00+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

> Reply from TRDaz ↑Fri Jul 19, 2019 3:53 pm at Fri Jul 19, 2019 3:53 pm
>
> 
If you manually cut out the G1M then daemon's tool works okay on most models. Anything with cloth/physics won't work though, it uses the same physics format as DOA6 and that hasn't been fixed yet.
Ye I figured that out, I made a small script to extract the G1M files from the model package, and sadly Mysterio is one of the models that won't convert, which makes me thing it's due to the cloth physics that u spoke of.

been posting some pics of these models on my twitter.
[https://twitter.com/Demonslayerx8/statu ... 6093926401](https://twitter.com/Demonslayerx8/status/1152114566093926401)
## Post #7
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-07-22T10:03:28+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

How do you cut out G1M please ?
## Post #8
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-07-22T19:41:04+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

> Reply from huitbgoiouythy ↑Mon Jul 22, 2019 6:03 pm at Mon Jul 22, 2019 6:03 pm
>
> 
How do you cut out G1M please ?
I used VGMToolbox to extract the G1M's from the game
## Post #9
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-07-22T20:33:38+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

> Reply from demonslayerx8 ↑Tue Jul 23, 2019 3:41 am at Tue Jul 23, 2019 3:41 am
>
> 
huitbgoiouythy wrote: ↑Mon Jul 22, 2019 6:03 pm
How do you cut out G1M please ?

I used VGMToolbox to extract the G1M's from the game

Thx for the answer, the image is not loading sadly 

Pingu! from Xentax Discord found how to extract the stream_voice containing voice line of MUA 3 here : [https://discord.gg/3HU5sC](https://discord.gg/3HU5sC)
Many thx to him and AceKombat for finding the script to extract. The .ktsl2asbin does not have a script yet, but AceKombat found very valuable info of it.
## Post #10
- Username: hallinbirch
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 25, 2016 11:51 pm
- Post datetime: 2019-07-23T16:33:30+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

hello guys im sorry to interrupt this conversation with my n00bish requests
when using the file carver you mentioned i use "_M1G7300" for file start search string
but where does the file end 
whats the terminator or size offset 
thanks for any help in advance
## Post #11
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2019-08-23T17:50:08+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

Would anyone be able to post a small guide on getting the models?
## Post #12
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-09-08T11:21:33+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

> Reply from huitbgoiouythy ↑Tue Jul 23, 2019 4:33 am at Tue Jul 23, 2019 4:33 am
>
> 
demonslayerx8 wrote: ↑Tue Jul 23, 2019 3:41 am
huitbgoiouythy wrote: ↑Mon Jul 22, 2019 6:03 pm
How do you cut out G1M please ?

I used VGMToolbox to extract the G1M's from the game


Thx for the answer, the image is not loading sadly 

Pingu! from Xentax Discord found how to extract the stream_voice containing voice line of MUA 3 here : https://discord.gg/3HU5sC
Many thx to him and AceKombat for finding the script to extract. The .ktsl2asbin does not have a script yet, but AceKombat found very valuable info of it.
Sorry for a late reply + reviving this thread.. but has any progress been made on the ktsl2asbin?
## Post #13
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-09-16T18:59:40+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

> Reply from demonslayerx8 ↑Sun Sep 08, 2019 7:21 pm at Sun Sep 08, 2019 7:21 pm
>
> 
huitbgoiouythy wrote: ↑Tue Jul 23, 2019 4:33 am
demonslayerx8 wrote: ↑Tue Jul 23, 2019 3:41 am

I used VGMToolbox to extract the G1M's from the game


Thx for the answer, the image is not loading sadly 

Pingu! from Xentax Discord found how to extract the stream_voice containing voice line of MUA 3 here : https://discord.gg/3HU5sC
Many thx to him and AceKombat for finding the script to extract. The .ktsl2asbin does not have a script yet, but AceKombat found very valuable info of it.

Sorry for a late reply + reviving this thread.. but has any progress been made on the ktsl2asbin?

I haven't asked AceKombat, since last time he said he's too busy to make a batch script, at the time, he discovered the following, credits and many thx to him. I'll contact him see if he can do one on Discord.
Trimmed:
Magic ID String 0x00: 0xC5CCCB70
0x04 = File Length 32-bit LE
0x14 = Name string-header end (relative from offset 0x00) LE
0x1C = Name
## Post #14
- Username: Roseweave
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 26, 2019 6:43 am
- Post datetime: 2019-09-25T22:54:52+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

Does anyone have a model file for Ms. Marvel? It seems like the most detailed version of her atm
## Post #15
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-09-26T06:06:57+00:00
- Post Title: Marvel Ultimate Alliance 3 The Black Order

> Reply from Roseweave ↑Thu Sep 26, 2019 6:54 am at Thu Sep 26, 2019 6:54 am
>
> 
Does anyone have a model file for Ms. Marvel? It seems like the most detailed version of her atm

sadly her model uses the updated physics, so can't be extracted with Daemon's tool. The tool for FETH can't open it either cause there's changes to the geometry section that can't be read yet, been trying to get the maker of the tool to add support for it, but no luck yet.
## Post #16
- Username: Roseweave
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 26, 2019 6:43 am
- Post datetime: 2019-10-29T03:55:21+00:00
- Post Title: Re: Marvel Ultimate Alliance 3 The Black Order

Damn. What are the chances the Avengers game one will be extractable? Have people been able to pull models out of Spider-man?
## Post #17
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-11-04T09:16:15+00:00
- Post Title: Re: Marvel Ultimate Alliance 3 The Black Order

> Reply from Roseweave ↑Tue Oct 29, 2019 11:55 am at Tue Oct 29, 2019 11:55 am
>
> 
Damn. What are the chances the Avengers game one will be extractable? Have people been able to pull models out of Spider-man?
the Spider-Man game has been extractable, just look for Daemon1's topic for Marvel's SpiderMan. As for Marvel's Avengers game, it'll most likely take half a year or more to dump that game.
## Post #18
- Username: SpideyFan360
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 21, 2017 3:36 am
- Post datetime: 2019-12-28T10:29:40+00:00
- Post Title: Re: Marvel Ultimate Alliance 3 The Black Order

So with the 2nd DLC update out... any luck with getting models or are we still stuck?
## Post #19
- Username: sleepingmaster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 25, 2017 1:48 pm
- Post datetime: 2021-03-14T09:47:56+00:00
- Post Title: Re: Marvel Ultimate Alliance 3 The Black Order

> Reply from pepsiguy2 ↑Sat Aug 24, 2019 1:50 am at Sat Aug 24, 2019 1:50 am
>
> 
Would anyone be able to post a small guide on getting the models?

I have it figured more or less. 

Things you will need (in addition to the MUA3 files): 
QuickBMS
Noesis
Cethleann ( [viewtopic.php?f=10&t=21679#p159434](https://forum.xentax.com/viewtopic.php?f=10&t=21679#p159434) )
Noesis .g1m plugin: ( [viewtopic.php?f=16&t=21666](https://forum.xentax.com/viewtopic.php?f=16&t=21666))

1.) Use QuickBMS along with the BMS script posted earlier in the thread to extract the mesh (in ACTION > MODEL folder) and textures (ACTION > TEXTURE) for your character of choice. You should have a xxx_mdl.bin (mesh) and a  xxx.g1t (textures) now. 

2.) Download, setup Cethleann. Drag your xxx.mdl.bin onto Cethleann.Unbundler.exe. It should kick out a folder (same location as your mdl.bin) that contains the separate pieces from the .bin file. If you see g2m's in here, you're in business. While you're here add the xxx.g1t you extracted earlier to this folder. 

3.) Download the .g1m plugin for Noesis (projectG1m.dll), add  to your Noesis > plugins folder. Open Noesis, click on the Tools tab, check the box "merge all assets in the same folder" (or you're not getting bones). 

4.) Open Noesis, navigate to your folder with the g1m's  and your g1t, select the g1m's.  If all goes well you should have your model, bones and textures attached. Export to format of your choice.

Shoutouts to Yretenai and Joschka for the .g1m wizardry.
## Post #20
- Username: TommaLlama
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 15, 2022 5:45 am
- Post datetime: 2022-05-14T21:47:59+00:00
- Post Title: Re: Marvel Ultimate Alliance 3 The Black Order

> Reply from sleepingmaster ↑Sun Mar 14, 2021 5:47 pm at Sun Mar 14, 2021 5:47 pm
>
> 
pepsiguy2 wrote: ↑Sat Aug 24, 2019 1:50 am
Would anyone be able to post a small guide on getting the models?


I have it figured more or less. 

Things you will need (in addition to the MUA3 files): 
QuickBMS
Noesis
Cethleann ( viewtopic.php?f=10&t=21679#p159434 )
Noesis .g1m plugin: ( viewtopic.php?f=16&t=21666)

1.) Use QuickBMS along with the BMS script posted earlier in the thread to extract the mesh (in ACTION > MODEL folder) and textures (ACTION > TEXTURE) for your character of choice. You should have a xxx_mdl.bin (mesh) and a  xxx.g1t (textures) now. 

2.) Download, setup Cethleann. Drag your xxx.mdl.bin onto Cethleann.Unbundler.exe. It should kick out a folder (same location as your mdl.bin) that contains the separate pieces from the .bin file. If you see g2m's in here, you're in business. While you're here add the xxx.g1t you extracted earlier to this folder. 

3.) Download the .g1m plugin for Noesis (projectG1m.dll), add  to your Noesis > plugins folder. Open Noesis, click on the Tools tab, check the box "merge all assets in the same folder" (or you're not getting bones). 

4.) Open Noesis, navigate to your folder with the g1m's  and your g1t, select the g1m's.  If all goes well you should have your model, bones and textures attached. Export to format of your choice.

Shoutouts to Yretenai and Joschka for the .g1m wizardry.

Hey there!
Sorry for the necropost, just wasn't sure where else to ask this..
I was following this guide it worked like a charm, awesome!
The issue I'm having is trying to rip the animations, specifically the mot.bin files.
I was able to get a mot.bin file after using quickbms on the mot.bin.zl_ files located in the ROMFS -> ACTION -> MOTION folder , but Noesis doesn't seem to be able to preview the mot.bin or export it.
I've tried using the other Cethleann Exporters but nothing seems to output anything.
I think the mot.bin could be exported but I'm not sure what program would be able to do it, as I'm fairly new to this stuff.
Everything I've learned was in this guide, so if anyone possibly has any suggestions on how I could export these mot.bin files, it would be amazing!

Thanks!!
## Post #21
- Username: Raphael Splinterson
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 31, 2016 12:36 pm
- Post datetime: 2022-08-05T14:42:06+00:00
- Post Title: Re: Marvel Ultimate Alliance 3 The Black Order

> Reply from sleepingmaster ↑Sun Mar 14, 2021 5:47 pm at Sun Mar 14, 2021 5:47 pm
>
> 
pepsiguy2 wrote: ↑Sat Aug 24, 2019 1:50 am
Would anyone be able to post a small guide on getting the models?


I have it figured more or less. 

Things you will need (in addition to the MUA3 files): 
QuickBMS
Noesis
Cethleann ( viewtopic.php?f=10&t=21679#p159434 )
Noesis .g1m plugin: ( viewtopic.php?f=16&t=21666)

1.) Use QuickBMS along with the BMS script posted earlier in the thread to extract the mesh (in ACTION > MODEL folder) and textures (ACTION > TEXTURE) for your character of choice. You should have a xxx_mdl.bin (mesh) and a  xxx.g1t (textures) now. 

2.) Download, setup Cethleann. Drag your xxx.mdl.bin onto Cethleann.Unbundler.exe. It should kick out a folder (same location as your mdl.bin) that contains the separate pieces from the .bin file. If you see g2m's in here, you're in business. While you're here add the xxx.g1t you extracted earlier to this folder. 

3.) Download the .g1m plugin for Noesis (projectG1m.dll), add  to your Noesis > plugins folder. Open Noesis, click on the Tools tab, check the box "merge all assets in the same folder" (or you're not getting bones). 

4.) Open Noesis, navigate to your folder with the g1m's  and your g1t, select the g1m's.  If all goes well you should have your model, bones and textures attached. Export to format of your choice.

Shoutouts to Yretenai and Joschka for the .g1m wizardry.


Hi all. I liked the lesson that is written here. However, I can't find a full tutorial on extracting data from .nsz files so I can actually try this tutorial. The methods I've tried give errors. Can you please tell me how did you extract the files from .nsz?
