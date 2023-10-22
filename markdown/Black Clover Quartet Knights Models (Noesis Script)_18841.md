## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-22T02:19:05+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

chrrox and I have improved his Gunslinger Stratos script to work with the models from this game. All the stuff for unpacking archives and loading models/textures are included in the attachment. I will explain the process below.

Unpack/Decompress

Unpack the "GxArchivedFile" archives using black_clover_unpack.bms. Models will be exported to folder "FA61C1D7" and textures to "FC397BB3".

After that they need to be decompressed using BC_Dec.exe. Drag and drop a file or a whole folder on the exe, and it will create unpacked files with the "_unp" suffix.

3D Models/Textures

Use the Noesis script to load the .mdl and .tex files. If you want the material data to get loaded too, make sure to decompress the "5E12DE0D" folder. Only the highest LODs are loaded by default, you can change that in the script.

Texture Finder Tool

Model textures are only applied if they are in the same directory as the .mdl file. First of all make sure you have decompressed these 3 folders : "5E12DE0D", "FA61C1D7", "FC397BB3". Now drag and drop a .mdl file on the BC_TexFinder.exe. It will copy all the necessary textures to the model directory. Load the .mdl file in Noesis, and it should have the textures applied.

Screenshots




Credits
chrrox - Base noesis script and overall help
daemon1 - Hash function
[Black_Clover_Scripts_U2.rar](https://xentaxbackup.github.io/file/14967_Black_Clover_Scripts_U2.rar)
## Post #2
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-09-23T00:16:33+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

while I'm glad a script is made for this, but it seems to fight against the fate_extella MDL noesis script
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-23T00:31:43+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

Either disable the Fate plugin temporarily, or change the ".mdl" extension to something else in the script and change the bms script accordingly.
## Post #4
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-09-23T02:10:20+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

hmm alright... wish there was a simpler way to locate the proper textures tho

anyways, I found some textures that are in BC6 format (example: file 7D5AF7F2_unp.tex), they're pretty much normal maps for characters it looks like.

> 124B40BD
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-09-23T02:32:29+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from demonslayerx8
>
> hmm alright... wish there was a simpler way to locate the proper textures tho

anyways, I found some textures that are in BC6 format (example: file 7D5AF7F2_unp.tex), they're pretty much normal maps for characters it looks like.
124B40BD

just use ninja ripper.
when the game starts go to costume select and dump the costume you want.
only the textures from that costume will be dumped.
## Post #6
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2018-09-23T20:22:06+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

So daemon was making tools for gundam breaker 3, but stopped since you guys made tools for the same engine, would it be possible to add support for the scripts? I provided a sample file its ps4 only btw [https://www.mediafire.com/file/hc6sw267 ... 1.zip/file](https://www.mediafire.com/file/hc6sw267jctvfv1/GxArchivedFile001.zip/file)
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-24T11:34:07+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

I am not really interested in mecha models, but I will take a look some time, since the differences seem to be minor. For now I have attached a script for unpacking the archive.

For loading the textures change this line (line 315)

```
imgWidth, imgHeight, type1, type2, type3, type4, unk00 = bs.read("2H4BI")
```

to this :

```
unk,imgWidth, imgHeight, type1, type2, type3, type4, unk00 = bs.read("I2H4BI")
```

[gundam_breaker_unpack.rar](https://xentaxbackup.github.io/file/14908_gundam_breaker_unpack.rar)
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-24T15:30:08+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from akderebur
>
> Textures are only applied if they are in the same directory as the .mdl file. So you need to either find them yourself from the .tex files, or rip them with Ninjaripper for ease.

Can you explain this? If textures will be applied automatically, why anyone needs to use Ninjaripper ?
## Post #9
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-24T15:44:49+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from daemon1
>
> 
Can you explain this? If textures will be applied automatically, why anyone needs to use Ninjaripper ?
I couldn't figure out the name hashing. The mdc files has proper paths for textures, but .tex files themselves have hashes as names. So I have no way of finding the .tex files automatically.

What I meant is that if you find those tex files yourself or use Ninjaripper to get them, they will be loaded in Noesis automatically when they are in the same folder as the mdl. So the "automatic" part here refers to loading of already ripped/found textures automatically, not automatic finding of the .tex files.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-24T16:04:06+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

i will try finding hash function, this will help many games on this engine
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-24T20:29:21+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

ok i found the hash function, and its not crc32

i need some time to test it
## Post #12
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2018-09-24T22:05:48+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from demonslayerx8
>
> while I'm glad a script is made for this, but it seems to fight against the fate_extella MDL noesis script
I've fixed my Fate MDL script so this shouldn't happen anymore.
## Post #13
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-09-28T05:52:07+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from daemon1
>
> ok i found the hash function, and its not crc32

i need some time to test it
how goes the progress on the tests?
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-28T15:11:55+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from demonslayerx8
>
> daemon1 wrote:ok i found the hash function, and its not crc32

i need some time to test it
how goes the progress on the tests?
tests passed. the function works for all textures/models names
## Post #15
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-09-29T08:12:07+00:00
- Post Title: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from daemon1
>
> demonslayerx8 wrote:daemon1 wrote:ok i found the hash function, and its not crc32

i need some time to test it
how goes the progress on the tests?
tests passed. the function works for all textures/models names
oohh nice, can't wait for the update then.
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-02T12:17:38+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

I have added a new tool (BC_TexFinder.exe) for getting the model textures automatically. Check out the first post to see how to use it.

Huge thanks to daemon1 for figuring out the hash function.
## Post #17
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2018-10-02T19:12:50+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

i get an issue with the noesis script, or maybe the actual tools for gundam breaker 3 [https://i.imgur.com/LoMlnSh.png](https://i.imgur.com/LoMlnSh.png) all unp files are either 0 or 1kbs big and wont load
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-02T20:53:15+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from Rin
>
> all unp files are either 0 or 1kbs big and wont load
Like I said, I haven't looked at the model files for that game yet. I will do it when I have the time. Have other priorities atm. So noesis script won't work as it is now.

Unpacking should be fine using the script I posted here : [viewtopic.php?p=144363#p144363](http://forum.xentax.com/viewtopic.php?p=144363#p144363)
## Post #19
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-10-03T11:43:51+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Seems like there's some models that doesn't get all the textures with the TexFinder... example, Asta's hair, Charmy's outfit, Captain Yami's face, default Yuno's book and so forth.

But still, works better than I expected it to be.
## Post #20
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-03T12:32:17+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from demonslayerx8
>
> example, Asta's hair, Charmy's outfit, Captain Yami's face, default Yuno's book and so forth.
I am not familiar with the character names. Planning to watch the series some time  

Can you pm me the .mdl file names for those characters you mentioned? I can take a look to see what is wrong.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-03T15:08:50+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

i will publish the tool for gundam breaker 3, its almost ready
## Post #22
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-10-04T00:05:30+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from akderebur
>
> demonslayerx8 wrote:example, Asta's hair, Charmy's outfit, Captain Yami's face, default Yuno's book and so forth.
I am not familiar with the character names. Planning to watch the series some time  

Can you pm me the .mdl file names for those characters you mentioned? I can take a look to see what is wrong.
I'll just say the filenames here lol

> 4E22E410_unp - Captain Yami's face texture
>
> 008FF299_unp - Black Asta book texture (pre-order DLC)
>
> 17DC9E61_unp - Vanessa Bikini face texture (Summer Costume Set DLC)
>
> 886FF7DE_unp - Fana face texture
>
> 903D9EE3_unp - Mars face texture
>
> 943E094E_unp - fails to preview
>
> A1E3B0FD_unp - Yuno's book texture
>
> A4F82B76_unp - Charmy's body texture
>
> C47BA7DD_unp - Asta's hair texture
>
> E5B8A3E8_unp - Captain Yami's alt outfit body texture (Summer Costume Set DLC)
>
> F0FBDC5A_unp - all textures not exported for it
## Post #23
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-04T07:34:11+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

There was a small bug while converting the hash value to hex string. I have fixed it and updated the first post. All textures should be found now.
## Post #24
- Username: franada
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 07, 2018 2:13 pm
- Post datetime: 2018-10-26T22:24:24+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

in the masterwin64 folder I have 4 GxArchiveFile

ooo.dat
000.dath
001.dat
001.dath

should I decompress them all? 

Because when I do that at one point they ask me if I want to overwrite files because they already exist.
## Post #25
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-26T22:30:06+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from franada
>
> 
should I decompress them all?
Just decompress one of the dat/dath pairs. So like only select 000.dat and 001.dat when using the script.
## Post #26
- Username: franada
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 07, 2018 2:13 pm
- Post datetime: 2018-10-27T00:23:07+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

I use the Technic to find the texture but it not showing in the neosis. Dont really matter I think . Its normal that the material is kind of broken? Like the hair is the same material as the body. Or the eyes with the mouth
## Post #27
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-27T07:24:19+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from franada
>
> Like the hair is the same material as the body. Or the eyes with the mouth
I haven't encountered that with the character models. Can you tell me the names of the files that you have this problem with?
## Post #28
- Username: franada
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 07, 2018 2:13 pm
- Post datetime: 2018-10-27T08:02:25+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from akderebur
>
> franada wrote: Can you tell me the names of the files that you have this problem with?

All of them. Got the same problem with little witch academia. the materiel are all over the place. For that one for example all the teeth are one material and the vertex are not all connected so its a mess to find the base expression. I dont know what cause that.

[https://gyazo.com/892b403c3a0fe9ee2b3b12ecd3b6d7f5](https://gyazo.com/892b403c3a0fe9ee2b3b12ecd3b6d7f5)
## Post #29
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-27T08:13:51+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Do they get loaded properly in Noesis? As you can see in my first post, the characters should be loaded with no problem, including the materials.

> Reply from franada
>
> Got the same problem with little witch academia.
That game uses Unity afaik. If you are having this problem with multiple tools it might be related to the model importer of your 3d software. What format do you export to from Noesis?
## Post #30
- Username: Μadara
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 04, 2018 6:10 am
- Post datetime: 2018-12-03T23:50:42+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

So I spent a couple of hours trying to figure out what exactly I'm doing. I got Noesis as well as read about how to use .bms files however I still couldn't figure out how to take apart the .dat files. When trying to view them in Noesis it just kept giving me an error.

Edit: Never mind I'm dumb and read over it. Thanks for this guide though.

Edit 2: Now I can't get the material textures to apply to the model when viewing them in Noesis.
## Post #31
- Username: ELEVATRs
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 09, 2018 5:07 pm
- Post datetime: 2018-12-09T12:26:34+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Thanks for the tutorial
## Post #32
- Username: ELEVATRs
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 09, 2018 5:07 pm
- Post datetime: 2018-12-10T12:03:14+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

by the way, when i unpack the .tex files, should they load in fully textured in noesis??
## Post #33
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-10T15:27:59+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from ELEVATRs
>
> by the way, when i unpack the .tex files, should they load in fully textured in noesis??
You have to use the Texture Finder Tool first. After that when you load the .mdl files in Noesis, they should be textured.
## Post #34
- Username: ELEVATRs
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 09, 2018 5:07 pm
- Post datetime: 2018-12-10T17:31:54+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

thanks, i can view the textures in noesis now, but i want to export them as a different file format for blender, it works for the model, but the textures do not get converted, and i tried flipping the UV's please help!!
## Post #35
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-10T18:27:18+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from ELEVATRs
>
> it works for the model, but the textures do not get converted
Load the .tex files with Noesis, then export them to any format you want. This is mostly related to usage of Noesis so I won't go into detail. You can find lots of tutorials on how to use Noesis,
## Post #36
- Username: ELEVATRs
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 09, 2018 5:07 pm
- Post datetime: 2018-12-11T14:43:06+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

One more thing, when i export the textures and open the models in blender, i need to UVmap/Unwrap them and it is really time-consuming and difficult
## Post #37
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-11T14:45:22+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from ELEVATRs
>
> One more thing, when i export the textures and open the models in blender, i need to UVmap/Unwrap them and it is really time-consuming and difficult
You shouldn't need to do that. You must have a problem with Noesis export or Blender import.
## Post #38
- Username: ELEVATRs
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 09, 2018 5:07 pm
- Post datetime: 2018-12-12T18:07:32+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

[http://prntscr.com/lu4pn6](http://prntscr.com/lu4pn6)

I have a problem, whenever I try upload this model, an error pops up.

Model name: 96F70BC6
## Post #39
- Username: Tahugamer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 26, 2018 3:46 pm
- Post datetime: 2018-12-26T09:55:44+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Hello i'm new to this stuff but when i try to Unpack the .Dat or .Dath it just won't do it i have QuickBms and am using the script but it says the offset is 8 bytes off i don't know what to do and really wanna get models from this game if anyone could help that would be nice and thanks for reading.
## Post #40
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2019-01-17T07:33:30+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Could you guys look at some MDL files from Death end re;Quest? It uses the same engine. The .tex files work fine, but the MDL files won't work. 
I believe these are mobs/characters. From looking through the texture files.

```
https://mega.nz/#!758niIhS!Yk2RE8BnQvaG8-6CCu5KiwdCdb94IMHq8D5eZ0b81J0
```
## Post #41
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-17T09:56:16+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from anime663
>
> Could you guys look at some MDL files from Death end re;Quest?
[fmt_Orochi4.rar](https://xentaxbackup.github.io/file/15498_fmt_Orochi4.rar)
## Post #42
- Username: JackKamikazeXYZ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 24, 2019 5:49 am
- Post datetime: 2019-01-23T23:27:49+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

what is GxArchivedFile
## Post #43
- Username: Melvinnnn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Mar 14, 2019 5:06 am
- Post datetime: 2019-03-13T21:57:05+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Hello
This article is close to what I needed. However, I can not understand because I am Japanese and I do not understand English. Can this ripping the 3dmodel? if you can, Can you create a tutorial video? Of course I pay the reward
Bad English for Google Translation
## Post #44
- Username: Melvinnnn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Mar 14, 2019 5:06 am
- Post datetime: 2019-03-13T23:16:38+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

I have the same problem.
How did you extract GxArchivedFile000.dat using black_clover_unpack.bms?
## Post #45
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-05-20T21:30:25+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

anyone able to update the scripts for death end's PC version? here are samples [https://www.mediafire.com/file/22293el4 ... c.zip/file](https://www.mediafire.com/file/22293el4edq3yc8/death_end_pc.zip/file)
## Post #46
- Username: Satania
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 02, 2018 8:39 pm
- Post datetime: 2019-05-24T22:47:51+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

were you able to find a script for the .xet and .ldm file for Death end reQuest Pc?
## Post #47
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2019-05-25T00:46:22+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from Satania ↑Sat May 25, 2019 6:47 am at Sat May 25, 2019 6:47 am
>
> 
were you able to find a script for the .xet and .ldm file for Death end reQuest Pc?

I think you can just batch rename those to .tex and .mdl since they're just name-inverted extensions for some reason, decompression tool and noesis .mdl and .tex plugin works fine in most cases.
## Post #48
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-27T16:13:49+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from Rin ↑Tue May 21, 2019 5:30 am at Tue May 21, 2019 5:30 am
>
> 
anyone able to update the scripts for death end's PC version?
Here is the updated script for PC. If a model/texture isn't working, then it is probably not important. Don't ask for fix please.
[fmt_Orochi4_PC.rar](https://xentaxbackup.github.io/file/16297_fmt_Orochi4_PC.rar)
## Post #49
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2019-05-28T18:45:49+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Hello

is it possible to extract animations?

Thx for help
## Post #50
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2019-05-29T18:26:50+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

I dont understand how work BC_TexFinder.exe
-----------------------------------------------------------------------------------------------
Model textures are only applied if they are in the same directory as the .mdl file. First of all make sure you have decompressed these 3 folders : "5E12DE0D", "FA61C1D7", "FC397BB3". Now drag and drop a .mdl file on the BC_TexFinder.exe. It will copy all the necessary textures to the model directory. Load the .mdl file in Noesis, and it should have the textures applied.
-------------------------------------------------------------------------------------------------

1) I unpack  .mdl and .tex and .mdc of folder "5E12DE0D", "FA61C1D7", "FC397BB3"
2) I copy all  unp_.mdl and unp_.tex and unp_.mdc in only one folder
3) I drop unp_.mdl on BC_TexFinder.exe

But I dont have texture applied 

How work BC_TexFinder.exe?
## Post #51
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2019-05-30T12:15:16+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

I find solution for look texture on mesh into Noesis
you have to put all the file mdl tex in a file which keeps the name of:  "5E12DE0D"
## Post #52
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2019-07-02T10:42:39+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from akderebur ↑Tue May 28, 2019 12:13 am at Tue May 28, 2019 12:13 am
>
> 
Rin wrote: ↑Tue May 21, 2019 5:30 am
anyone able to update the scripts for death end's PC version?

Here is the updated script for PC. If a model/texture isn't working, then it is probably not important. Don't ask for fix please.

Any chance you could get the MDC to read on it too? When I try to open the Death End's MDL I get an error on Noesis. 
[https://i.imgur.com/SXhGt3n.png](https://i.imgur.com/SXhGt3n.png) (Error in question)

Right now since all enemies and characters are in one file, all the textures are sorta conglomerated in one place. with 1712 different tex files to sift through, it would be nice to know which belongs to which. As it stands even Daemons tool seems to hang on the mdc.

Or do you know of a way to find out what tex file belongs to which through the MDC? I'm just plain having trouble reading it due to my lack of experience with hex and coding. Any help appreciated.

Edit: Nvm, the thing gets hashed anyways, and Ninja Ripper doesnt work with Death End so no such thing as getting out Textures. That way.
## Post #53
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-02T11:53:48+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from kurokairaku ↑Tue Jul 02, 2019 6:42 pm at Tue Jul 02, 2019 6:42 pm
>
> 
Any chance you could get the MDC to read on it too?
No plans to support MDC atm. Hash function needs to be found first anyway.
## Post #54
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2019-07-04T23:27:15+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from akderebur ↑Tue Jul 02, 2019 7:53 pm at Tue Jul 02, 2019 7:53 pm
>
> 
kurokairaku wrote: ↑Tue Jul 02, 2019 6:42 pm
Any chance you could get the MDC to read on it too? 

No plans to support MDC atm. Hash function needs to be found first anyway.

Finding the models are easy just textures are not, so I use Intel GPA now to get textures.  I kinda wish though Ninja Ripper works with the game. I really want to make a cool wallpaper render of the beginning house area as I find it to be beautiful, but Ninja Ripper apparently cant see the DrawIndexed call and instead rips out the Draw call, but according to Intel GPA Drawindex is where all the mesh and textures are at. Intel GPA does see the geometry but I have to do it one by one otherwise haha. I heard it is possible to modify the ninja ripper dll but I know nothing of that.
## Post #55
- Username: ELEVATR3000
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 05, 2019 2:30 pm
- Post datetime: 2019-08-07T01:50:16+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

how would i export the file from noesis with the textures mapped?
## Post #56
- Username: Unari
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jan 31, 2019 12:53 pm
- Post datetime: 2019-08-21T03:07:39+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Hey guys, so i'm literally stuck on the first step; I have the GxArchivedFiles, but when i try and use the bms to extract from them it gives me some errors. I've tried extracting directly from the files in the Black Clover Quartet Knights\resource\masterWin64 and it ends up finding no files. If anyone could help i'd really appreciate it. Contact me here: Discord - Unari#4049
## Post #57
- Username: indiaskapie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 18, 2019 5:21 am
- Post datetime: 2019-09-19T21:38:05+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

OMG OMG OMG!!! I managed to rip the characters!! Thank you!!! Will share the files if anyone is interested, but I need to add the textures in to the Blender files  Soooooo happy!
## Post #58
- Username: indiaskapie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 18, 2019 5:21 am
- Post datetime: 2019-09-23T17:47:59+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

I'm posting them on my deviant art profile if you're interested deviantart/indiaskapie
## Post #59
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-07-04T18:39:45+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Hi there, I've recently come back to extracting models from this game after getting Mereoleona's DLC and I'm trying to unpack the game files, I know I've done it before but I'm getting an error this time, I got both the .dat and .dath in the same location



I might just be overlooking something
## Post #60
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-04T22:32:07+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from Eag1e ↑Sun Jul 05, 2020 2:39 am at Sun Jul 05, 2020 2:39 am
>
> 
I've done it before but I'm getting an error this time
Slightly different magic. Try the gundam script maybe : [viewtopic.php?p=144363#p144363](https://forum.xentax.com/viewtopic.php?p=144363#p144363)
## Post #61
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-07-04T22:59:37+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from akderebur ↑Sun Jul 05, 2020 6:32 am at Sun Jul 05, 2020 6:32 am
>
> 
Eag1e wrote: ↑Sun Jul 05, 2020 2:39 am
I've done it before but I'm getting an error this time

Slightly different magic. Try the gundam script maybe : viewtopic.php?p=144363#p144363

Seems to be somewhat working, although it only results in some type-less files in random folders
for GxArchivedFile000.dat 


For GxArchivedFile001.dat
## Post #62
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-05T07:42:58+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from Eag1e ↑Sun Jul 05, 2020 6:59 am at Sun Jul 05, 2020 6:59 am
>
> 
 although it only results in some type-less files in random folders
It requires a new script then. Need to see the file.
## Post #63
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-07-05T13:00:40+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from akderebur ↑Sun Jul 05, 2020 3:42 pm at Sun Jul 05, 2020 3:42 pm
>
> 
Eag1e wrote: ↑Sun Jul 05, 2020 6:59 am
 although it only results in some type-less files in random folders

It requires a new script then. Need to see the file.

Uploaded a dat and dath file to MEGA [https://mega.nz/folder/hYcUnQJR#IBeTpkV4XOkZqXdpPoD6BA](https://mega.nz/folder/hYcUnQJR#IBeTpkV4XOkZqXdpPoD6BA)
## Post #64
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-05T17:29:02+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from Eag1e ↑Sun Jul 05, 2020 9:00 pm at Sun Jul 05, 2020 9:00 pm
>
> 
Uploaded a dat and dath file
I haven't downloaded the dat file because its large, but this script should work based on dath.
[black_clover_unpack_alt.zip](https://xentaxbackup.github.io/file/18429_black_clover_unpack_alt.zip)
## Post #65
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-07-05T23:37:06+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from akderebur ↑Mon Jul 06, 2020 1:29 am at Mon Jul 06, 2020 1:29 am
>
> 
Eag1e wrote: ↑Sun Jul 05, 2020 9:00 pm
Uploaded a dat and dath file

I haven't downloaded the dat file because its large, but this script should work based on dath.

This works, thank you!
## Post #66
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2020-07-27T10:33:20+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Can somebody please explain me how the hell do I use that triple damned "bc_texfinder.exe" tool? Step-by-step please. Method from the first post not working.
## Post #67
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2020-08-04T19:36:16+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Also can someone update Noesis script please? The one here just merges all the mesh part into one huge mesh which make separating and texturing it a huge pain. Thank you.
## Post #68
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-04T21:18:10+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from lezisell ↑Wed Aug 05, 2020 3:36 am at Wed Aug 05, 2020 3:36 am
>
> 
The one here just merges all the mesh part into one huge mesh which make separating and texturing it a huge pain.

You probably did not unpack/decompress the folder containing the ".mdc" files. In that case the material info is not read properly and meshes aren't separated. Use the same procedure I have described in the first post and it should work without a problem. It should also auto-texture too that way.
## Post #69
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2020-08-05T05:29:02+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

I did. I even keep MDC with MDL in one folder when converting into FBX. It still merges all the meshes. I've extracted all the textures needed with "Ninja Ripper" now all I need is working models.

Here's the model I'm trying to work: [https://mega.nz/file/8wMyRC6K#2_fmj_tht ... zVKz1PWt5k](https://mega.nz/file/8wMyRC6K#2_fmj_thtdjJ0ejlno7jt2KeIe-eUSznkzVKz1PWt5k)

I did everything by manual, unpacked MDC and MDL, extracted the textures with Ninja Ripper and still converted model comes merged.

And this what happens when I'm placing both MDL and MDC in one folder with TEX files.
[https://imgur.com/a/H6OopfG](https://imgur.com/a/H6OopfG)
## Post #70
- Username: zuraxe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 09, 2020 8:55 am
- Post datetime: 2020-08-17T18:28:52+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

same problem as  lezisell
anyone can help please?
## Post #71
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-17T19:39:26+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from lezisell ↑Wed Aug 05, 2020 1:29 pm at Wed Aug 05, 2020 1:29 pm
>
> 
I even keep MDC with MDL in one folder when converting into FBX. 

extracted the textures with Ninja Ripper and still converted model comes merged.

And this what happens when I'm placing both MDL and MDC in one folder

> Reply from zuraxe ↑Tue Aug 18, 2020 2:28 am at Tue Aug 18, 2020 2:28 am
>
> 
same problem as  lezisell

MDC and MDL don't need to be in the same folder. In fact I checked the script and it loads the MDC from the folder "5E12DE0D". So make sure it is in that folder specifically.

The links lezisell posted aren't active anymore. If you upload a MDL/MDC pair I can take a look.
## Post #72
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2020-08-18T06:14:07+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

Thanks. I think I understand my mistake. Quick thing though. Should folder names be in uppercase for this to work, or can I rename them to lowercase? Because I really hate the uppercase in files naming. It's psychological.
## Post #73
- Username: EggyTrashBag
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 20, 2020 5:48 pm
- Post datetime: 2020-08-20T20:49:59+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

i've recently been trying to rip models and textures from death end request 2 as it recently came out and uses the same Orochi4 engine as the first game though i'm struggling to unpack the GxArchived files using the black clover bms script and the alt script, all that it displays is this:



I've attempted to use the gundam breaker bms script aswell and although that seems to work there's files which have weird file types and i'm not sure what to do with them
## Post #74
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-20T21:14:36+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from EggyTrashBag ↑Fri Aug 21, 2020 4:49 am at Fri Aug 21, 2020 4:49 am
>
> 
i'm struggling to unpack the GxArchived files using the black clover bms script and the alt script

Need to see the file. PM me if you can provide a sample.

Edit:

Made an unpack script based on the archive sample I have received. No file/folder hashes were present in the archive.
[death_end_req_2_unpack.rar](https://xentaxbackup.github.io/file/18634_death_end_req_2_unpack.rar)
## Post #75
- Username: neidhardt
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Apr 01, 2020 1:07 pm
- Post datetime: 2020-08-26T08:01:28+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

I was able to get into Death end re;Quest 2's .dat files just fine, but the MDL files are what's not working for me using the noesis scripts here. 
I get an error upon opening and exporting the files. [https://i.imgur.com/9wz9vZN.png](https://i.imgur.com/9wz9vZN.png)


Here's the samples I tried it on. [https://drive.google.com/file/d/16cQgfV ... sp=sharing](https://drive.google.com/file/d/16cQgfV1HBHJuCind9LDcopPTbZ8m7n7v/view?usp=sharing)
## Post #76
- Username: EggyTrashBag
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 20, 2020 5:48 pm
- Post datetime: 2020-11-17T15:41:52+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from neidhardt ↑Wed Aug 26, 2020 4:01 pm at Wed Aug 26, 2020 4:01 pm
>
> 
I was able to get into Death end re;Quest 2's .dat files just fine, but the MDL files are what's not working for me using the noesis scripts here.

how exactly did you get the script to work? when I used it I just get more dat files and such, not sure if i was doing it correctly
## Post #77
- Username: A157
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 18, 2022 6:35 am
- Post datetime: 2022-04-18T00:08:28+00:00
- Post Title: Re: Black Clover: Quartet Knights Models (Noesis Script)

> Reply from demonslayerx8 ↑Sun Sep 23, 2018 8:16 am at Sun Sep 23, 2018 8:16 am
>
> 
while I'm glad a script is made for this, but it seems to fight against the fate_extella MDL noesis scriptwhy is it 0 mb after i tried to decompressed it using the tools?
