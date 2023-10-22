## Post #1
- Username: Gashd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 18, 2018 10:37 pm
- Post datetime: 2018-03-18T16:28:51+00:00
- Post Title: Fate Extella PsVita *.mdl files

PC version of Noesis script does not work on the vita version of *.mdl files
And how to unpack the *.mdl file

please help me



OT})22_Z~M4RHLJ$L75ZQ3R.jpg (123.88 KiB) Viewed 658 times



Sample file
[http://www.mediafire.com/file/082mvcpa2 ... sv0000.mdl](http://www.mediafire.com/file/082mvcpa24as594/sv0000.mdl)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-19T09:25:18+00:00
- Post Title: Fate Extella PsVita *.mdl files

Some small patch to Kotcrab's great Noesis script from here: [https://github.com/kotcrab/fate-explorer/releases](https://github.com/kotcrab/fate-explorer/releases)



vita-sv0000-mdl.jpg (66.25 KiB) Viewed 637 times


Some extra faces which I did not have the time to fix.
(Would need 2 or 3 more model samples to check if the patch is sufficient.)
## Post #3
- Username: Gashd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 18, 2018 10:37 pm
- Post datetime: 2018-03-19T16:14:38+00:00
- Post Title: Fate Extella PsVita *.mdl files

> Reply from shakotay2
>
> Some small patch to Kotcrab's great Noesis script from here: https://github.com/kotcrab/fate-explorer/releases
vita-sv0000-mdl.jpg
Some extra faces which I did not have the time to fix.
(Would need 2 or 3 more model samples to check if the patch is sufficient.)
Thank you very much for your reply and help 
This is a sample file you need
[http://www.mediafire.com/file/csp0ounfu760bxr/model.zip](http://www.mediafire.com/file/csp0ounfu760bxr/model.zip)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-19T17:28:16+00:00
- Post Title: Fate Extella PsVita *.mdl files

thanks! Here are the changes to patch into the original script; 

####################################################################
be sure to use CORRECT indents, for example 8 blanks. Don't mix in tabs, never ever. You have been warned!
####################################################################

This is the most important change for VITA models; the vxstEntryCount is located 8 bytes earlier (reading 0x10 bytes instead of 0x18):

```
        for _, des in enumerate(vxstList):
            bs.seek(des.offset + self.nearOffset, NOESEEK_ABS)
            bs.readBytes(0x10)
```


Then additional vertexStrides to be inserted (you might insert 19 and 27 and see if it improves anything). The UV1BufferOfs
should be (vertexStride -4 ) for HalfFloats; but pay attention that it's constant (0x18) / doesn't follow the rule in the original code from vstride= 32 and above.

So it was a bit wild guessing; choosing 0x1B for vStride=31 made sense to me (but not tested); for vStride=35 I just decremented 0x18 (for vStride=36) to 0x17; but not sure.

Replace the lines in the original script from
"if vertStride == 24:" to elif vertStride == 36: by

```
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x10)
            if vertStride == 23:  #
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x13)
            elif vertStride == 24:  # 0xC, 0x10 unk floats
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x14)
            elif vertStride == 28:  # 0xC, 0x10, 0x14 unk floats
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x18)
            elif vertStride == 31:  # 
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x1B)
            elif vertStride == 32:  # 0xC, 0x10, 0x14 unk floats, 0x1C unk
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x18)
            elif vertStride == 35:  # 
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x17)
            elif vertStride == 36:

```

For the additional faces: as I said, don't have the time to fix this.

Anyways, HTH
## Post #5
- Username: Gashd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 18, 2018 10:37 pm
- Post datetime: 2018-03-19T19:23:34+00:00
- Post Title: Fate Extella PsVita *.mdl files

> Reply from shakotay2
>
> thanks! Here are the changes to patch into the original script; 

####################################################################
be sure to use CORRECT indents, for example 8 blanks. Don't mix in tabs, never ever. You have been warned!
####################################################################

This is the most important change for VITA models; the vxstEntryCount is located 8 bytes earlier (reading 0x10 bytes instead of 0x18):
Code: Select all        vxstEntryCount = []
        for _, des in enumerate(vxstList):
            bs.seek(des.offset + self.nearOffset, NOESEEK_ABS)
            bs.readBytes(0x10)

Then additional vertexStrides to be inserted (you might insert 19 and 27 and see if it improves anythink). The UV1BufferOfs
should be (vertexStride -4 ) for HalfFloats; but pay attention that it's constant (0x18)/doesn't follow the rule in the original code from vstride= 32 and above.

So it was a bit wild guessing; choosing 0x1B for vStride=31 made sense to me (but not tested); for vStride=35 I just decremented 0x18 (for vStride=36) to 0x17; but not sure.

Replace the lines in the original script from
"if vertStride == 24:" to elif vertStride == 36: by
Code: Select all            if vertStride == 20:  # 
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x10)
            if vertStride == 23:  #
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x13)
            elif vertStride == 24:  # 0xC, 0x10 unk floats
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x14)
            elif vertStride == 28:  # 0xC, 0x10, 0x14 unk floats
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x18)
            elif vertStride == 31:  # 
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x1B)
            elif vertStride == 32:  # 0xC, 0x10, 0x14 unk floats, 0x1C unk
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x18)
            elif vertStride == 35:  # 
                rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vertStride, 0x17)
            elif vertStride == 36:

For the additional faces: as I said, don't have the time to fix this.

Anyways, HTH

The script can work with the vita model
Not perfect but still thank you very much for your help



UJ[T_8900LCGQS3${Y{C6OK.png (190.5 KiB) Viewed 614 times
## Post #6
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2018-07-28T15:09:18+00:00
- Post Title: Fate Extella PsVita *.mdl files

I added support for PS Vita models based on this. New script also works on Fate/Extella Link models.

[https://github.com/kotcrab/fate-explore ... g/mdl-v1.2](https://github.com/kotcrab/fate-explorer/releases/tag/mdl-v1.2)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-26T02:43:13+00:00
- Post Title: Fate Extella PsVita *.mdl files

> Reply from jay11800
>
> Hello, I am trying to apply materials to the MDL files of fate extella link, when I go into noesis my model has 7 materials, all of which have textures, but aren't linked for some odd reason.you guys!  Why not just print out the texture path in Noesis?
It uses ".mxt" as texture extension.
If your extension is different for whatever reason then change it, like such:

```
                def getTexPath(extension):
                    texPath = self.stringBank[sstv.texPathSid]
                    texNormalizedName = path.splitext(path.basename(texPath))[0]
                    #texFinalPath = rapi.getDirForFilePath(rapi.getInputName()) + texNormalizedName + extension
                    texFinalPath = rapi.getDirForFilePath(rapi.getInputName()) + texNormalizedName + ".png"
                    #print("TexFinalPath: ", cnt, " ", texFinalPath)
                    if rapi.checkFileExists(texFinalPath):  # check in current dir first
                        return texFinalPath, texNormalizedName
```

Works for me:



ch001_m01_00-mdl.jpg (65.37 KiB) Viewed 519 times
## Post #8
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-10-16T16:22:13+00:00
- Post Title: Fate Extella PsVita *.mdl files

> Reply from shakotay2
>
> jay11800 wrote:Hello, I am trying to apply materials to the MDL files of fate extella link, when I go into noesis my model has 7 materials, all of which have textures, but aren't linked for some odd reason.you guys!  Why not just print out the texture path in Noesis?
It uses ".mxt" as texture extension.
If your extension is different for whatever reason then change it, like such:
Code: Select all            for sstv in sstvList:
                def getTexPath(extension):
                    texPath = self.stringBank[sstv.texPathSid]
                    texNormalizedName = path.splitext(path.basename(texPath))[0]
                    #texFinalPath = rapi.getDirForFilePath(rapi.getInputName()) + texNormalizedName + extension
                    texFinalPath = rapi.getDirForFilePath(rapi.getInputName()) + texNormalizedName + ".png"
                    #print("TexFinalPath: ", cnt, " ", texFinalPath)
                    if rapi.checkFileExists(texFinalPath):  # check in current dir first
                        return texFinalPath, texNormalizedName
Works for me:
ch001_m01_00-mdl.jpg

So what do I do with this, add it to the python script? I tried that, and nothing happened
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-16T16:46:04+00:00
- Post Title: Fate Extella PsVita *.mdl files

Uncomment thsi line (delete the #):
#print("TexFinalPath: ", cnt, " ", texFinalPath)
to find out what your problem might be.
In
def registerNoesisTypes():
this line's required: noesis.logPopup()
## Post #10
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-10-16T17:28:27+00:00
- Post Title: Fate Extella PsVita *.mdl files

> Reply from shakotay2
>
> Uncomment thsi line (delete the #):
#print("TexFinalPath: ", cnt, " ", texFinalPath)
to find out what your problem might be.
In
def registerNoesisTypes():
this line's required: noesis.logPopup()
[Noesis error.JPG](https://xentaxbackup.github.io/file/15034_Noesis error.JPG)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-16T18:48:33+00:00
- Post Title: Fate Extella PsVita *.mdl files

yeah, sorry, forgot that I added more lines:

```
        for mate in materialInfo:

...

                cnt = cnt + 1
                if texFinalPath is None:
                    continue
```
Take care of correct indents; and use blanks or tabs but no mixing
## Post #12
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-10-16T19:38:16+00:00
- Post Title: Fate Extella PsVita *.mdl files

> Reply from shakotay2
>
> yeah, sorry, forgot that I added more lines:
Code: Select all        cnt= 0
        for mate in materialInfo:

...

                cnt = cnt + 1
                if texFinalPath is None:
                    continueTake care of correct indents; and use blanks or tabs but no mixing
I'm still struggling trying to figure out what to do with this, and where it should go :c
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-16T19:49:33+00:00
- Post Title: Fate Extella PsVita *.mdl files

what do you mean?

search for the line "for mate in materialInfo:" in the script
and put the line cnt=0 before it.

search for the line "if texFinalPath is None:" in the script; there's two occurences;
put the line
cnt = cnt + 1
before the one which is followed by "continue".

Or, even simpler, just use
print("TexFinalPath: ", texFinalPath)
(should do the trick, the "cnt"  is not that important)
## Post #14
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-10-16T20:57:02+00:00
- Post Title: Fate Extella PsVita *.mdl files

> Reply from shakotay2
>
> what do you mean?

search for the line "for mate in materialInfo:" in the script
and put the line cnt=0 before it.

search for the line "if texFinalPath is None:" in the script; there's two occurences;
put the line
cnt = cnt + 1
before the one which is followed by "continue".

Or, even simpler, just use
print("TexFinalPath: ", texFinalPath)
(should do the trick, the "cnt"  is not that important)
Ok, I did it exactly like I think you are saying it goes, and I get this now
[error2.JPG](https://xentaxbackup.github.io/file/15035_error2.JPG)
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-16T21:24:19+00:00
- Post Title: Fate Extella PsVita *.mdl files

dunno, what's going wrong there-
Maybe you should follow Kotcrab's tip:

> Reply from Kotcrab
>
> If you want textures automatically loaded in Noesis you just need to open .mdl file from original extract directory without renaming or moving anything.
## Post #16
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-10-16T23:07:35+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

> Reply from shakotay2
>
> dunno, what's going wrong there-
Maybe you should follow Kotcrab's tip:
Kotcrab wrote:If you want textures automatically loaded in Noesis you just need to open .mdl file from original extract directory without renaming or moving anything.
 I have no clue, I haven't moved or renamed anything. If I could just convert the texture files, then that would be fine, i'll just manually reapply the textures, but I can't get some of these converted.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-20T10:28:36+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

> Reply from jay11800
>
>   I have no clue, I haven't moved or renamed anything. If I could just convert the texture files, then that would be fine, i'll just manually reapply the textures, but I can't get some of these converted.Using the py script from Kotcrab's Noesis MDL loader v1.2? Couldn't test it with mxt (or gxt?) textures, because I don't have those files.
My post as of Sep. 26th based on use of pngs.
## Post #18
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-10-20T22:52:35+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

> Reply from shakotay2
>
> jay11800 wrote:  I have no clue, I haven't moved or renamed anything. If I could just convert the texture files, then that would be fine, i'll just manually reapply the textures, but I can't get some of these converted.Using the py script from Kotcrab's Noesis MDL loader v1.2? Couldn't test it with mxt (or gxt?) textures, because I don't have those files.
My post as of Sep. 26th based on use of pngs.
[https://drive.google.com/open?id=1ttHVm ... -Ca-22PxCO](https://drive.google.com/open?id=1ttHVmNGG7B_QW_QwgD4S6h-Ca-22PxCO)
Here is what I am working with, I've included the fbx, gxt, and the tool I've tried to convert it with.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-21T12:34:59+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

yeah, GXTConvert.exe throws an exception: Index out of bounds; Noesis says: "GXT is corrupted".



Vita-gtx.png (8.58 KiB) Viewed 978 times


"Your" gtx headers are different from the ones handled by Noesis so far.

(The words at offsets 0x38 and 0x3A should be image width and height.)

Guess, we should leave this case to AceWell.
## Post #20
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-02-09T00:45:54+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

So god eater 3 has the same or similar format to Fate Extella, the unpackers for fate extella work with god eater 3 but the python script have a bug

samples including the script
[https://cdn.discordapp.com/attachments/ ... amples.zip](https://cdn.discordapp.com/attachments/475394244605902858/543592745592291328/god_eater_3_samples.zip)
## Post #21
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-09T03:22:05+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

There are just slight changes. I made a dirty fix to make it work with your static mesh samples. Skeleton is loaded too, but no skinning. Weights/bone ids are in the last 8 bytes of the vertex buffer, but there might be a need for remapping, so I left it for now.

Also not sure if that monster should look like that, or if some meshes are not getting loaded.


[data_fate_extella_ge3.rar](https://xentaxbackup.github.io/file/15682_data_fate_extella_ge3.rar)
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-09T05:14:33+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

> Reply from jay11800
>
> https://drive.google.com/open?id=1ttHVm ... -Ca-22PxCO
Here is what I am working with, I've included the .... gxt, and the tool I've tried to convert it with.

> Reply from shakotay2
>
> Guess, we should leave this case to Acewell.
okay  
jay11800's samples are gone but here is bms script to build pvr header for those "corrupt" gxt demo textures:


 FateMXTDemo_gxt2pvr.zip
(396 Bytes) Downloaded 62 times


supports pvrtc 2bpp rgba
## Post #23
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-02-09T14:28:28+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

> Reply from akderebur
>
> There are just slight changes. I made a dirty fix to make it work with your static mesh samples. Skeleton is loaded too, but no skinning. Weights/bone ids are in the last 8 bytes of the vertex buffer, but there might be a need for remapping, so I left it for now.
heres some (i think?) human character for a sample if it helps you more(they wouldnt load)
[https://cdn.discordapp.com/attachments/ ... ctersl.zip](https://cdn.discordapp.com/attachments/475394244605902858/543800263228653568/possible_player_charactersl.zip)
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-09T15:27:31+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

I have attached a new script. It is mostly about looking at different vertex buffer types, and changing the "Dx11Impl" accordingly. I won't continue with this, someone who has all the game files can do it properly.

Bone weights working for the character parts too. Still like I said there might be other vertex variations, so don't expect it to work with everything.


[data_fate_extella_ge3_weights.rar](https://xentaxbackup.github.io/file/15686_data_fate_extella_ge3_weights.rar)
## Post #25
- Username: kotaxzz1
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 21, 2015 1:44 am
- Post datetime: 2019-02-12T13:42:22+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

> Reply from akderebur
>
> I have attached a new script. It is mostly about looking at different vertex buffer types, and changing the "Dx11Impl" accordingly. I won't continue with this, someone who has all the game files can do it properly.

Bone weights working for the character parts too. Still like I said there might be other vertex variations, so don't expect it to work with everything.
work on most model file, but no with Face model. thank you.
## Post #26
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2019-03-05T14:09:28+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

can somebody please re-upload kotcrab's script,  the   linked page is gone
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-05T16:33:47+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

> Reply from tone ↑Tue Mar 05, 2019 10:09 pm at Tue Mar 05, 2019 10:09 pm
>
> can somebody please re-upload kotcrab's script,  the   linked page is gone
shakotay posted a link to all those tools in this post.   
[https://forum.xentax.com/viewtopic.php? ... 34#p138745](https://forum.xentax.com/viewtopic.php?f=16&t=17834#p138745)
## Post #28
- Username: shiraori
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 24, 2019 5:25 pm
- Post datetime: 2019-04-24T09:30:17+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

Can someone help me understand why this is happening? 


errors2.png (40.34 KiB) Viewed 729 times

 The errors appear on every Link file I try to load.
## Post #29
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2022-04-13T14:15:16+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

You can load the face by erasing a specific line
## Post #30
- Username: LaniusAetherion
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 09, 2022 4:08 am
- Post datetime: 2022-08-09T00:24:05+00:00
- Post Title: Re: Fate Extella PsVita *.mdl files

> Reply from ATFE0123 ↑Wed Apr 13, 2022 10:15 pm at Wed Apr 13, 2022 10:15 pm
>
> 
You can load the face by erasing a specific line

Which line needs to be erased?
