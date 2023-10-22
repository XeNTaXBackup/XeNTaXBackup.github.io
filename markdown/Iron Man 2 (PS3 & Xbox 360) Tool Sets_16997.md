## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-09-10T07:17:04+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

If you've skimmed my previous extraction guides on this game you should find it really time consuming and tedious to extract all submeshes manually through Hex2Obj.
So I have to create some tools to automate the process.

Change log:

20.03.2019
- Fixed a bug for reading certain mesh format;
- Fixed normals issue for Xbox360 models;
- Discard degenerate triangles for Xbox360's trixstripped meshes;
- Added instructions for executebles. Run without prams to see the usage.
21.12.2017
- Add vertex normals support for PS3 version.
29.11.2017
- A few updates on the mesh extractor. You might see below for changes of the usage.
17.09.2017
- Fixed some bugs in the mesh extractor, now it'll work correctly for Xbox 360 version .
14.09.2017
- Updated the BMS unpacking script to skip the unnecessary files which makes the process a bit simpler.
11.09.2017
- Improved the Noesis texture script to support PS3 ambient maps thanks to Acewell's assistance.

See below for the instructions.
[IM2ToolSets.zip](https://xentaxbackup.github.io/file/15927_IM2ToolSets.zip)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-09-10T07:32:39+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

Follow these steps to reach your goal:

Preparations

Use the attached BMS script (IM2_Unpacker_EXT.bms) to unpack the archives. 
Now locate to the output folder. For those big archives some files are named differently, which would require you to make some slight modifications. Here the condition I've met:

```
2. Ambiguous extension "Surfaces" in the same folder locating .SurfaceResident files. Rename them to "*.SurfaceResident"
```

Models Extraction

Use IM2.exe to extract your meshes. In the attachment there has already been a batch script. But you should know how the batch commands work:

```
for %%f in (*.ib) do IM2.exe Num "%%f"
pause
```

The Num is the order of the "_" in the filename before which to be truncated as the obj filename. By default it is set to 1 so it merges files sharing the same name before the first "_" into one obj file.
You can change this value if needed. Be aware that if you set it to a value greater than the amount of "_" in the filename it won't have any effects. No file will be merged then.

Textures Extraction

The textures are stored as headerless data files. So we gotta add them the needed headers. Place IM2T.Processor.exe to the output folder and run the following batch commands:

```
for %%f in (*.SurfaceResident) do IM2T.Processor.exe Ver "%%f"
pause
```

Remember to change "Ver" to your game version, that's either "PS3" or "X360". After the batch process you can find .IM2T files in the same folder. Then use the Noesis script tex_IM2T.py to preview 
and convert them to any format you want.

There're some issues with the lower resolusion images coz their headers are not always correct.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-09-10T07:33:26+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

Several renders I made for some of the suits. You could find them in DVD_HQFrontEnd.pkg.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-10T15:52:54+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

> Reply from Bigchillghost
>
> For PS3 version the AmbientOccusion map is not handled. Don't know what to do with it.
try this  

```
            untwid = bytearray()
            for x in range(imgWidth):
                for y in range(imgHeight):
                    idx = noesis.morton2D(x, y)
                    untwid += data[idx * 4:idx * 4 + 4]
            data = rapi.imageDecodeRaw(untwid, imgWidth, imgHeight, "r8 g8 b8 p8")
            texFmt = noesis.NOESISTEX_RGBA32

```
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-09-11T00:16:09+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

> Reply from AceWell
>
> 
try this
This's what I got:


Am I doing it wrong?

```
		if MapType == 0:
			texFmt = noesis.NOESISTEX_DXT1
		elif MapType == 3 or MapType == 6:
			texFmt = noesis.NOESISTEX_DXT5
		elif MapType == 8:
			untwid = bytearray()
			for x in range(imgWidth):
				for y in range(imgHeight):
					idx = noesis.morton2D(x, y)
					untwid += data[idx * 4:idx * 4 + 4]
			data = rapi.imageDecodeRaw(untwid, imgWidth, imgHeight, "r8 g8 b8 p8")
			texFmt = noesis.NOESISTEX_RGBA32
```
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-11T00:40:28+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

looks ok but the texture size should be 512x512 me thinks, you can see the repeat 
guess you have to do something like this

```
        imgWidth = imgWidth // 2
        imgHeight = imgHeight // 2
        untwid = bytearray()
        for x in range(imgWidth):
            for y in range(imgHeight):
                idx = noesis.morton2D(x, y)
                untwid += data[idx * 4:idx * 4 + 4]
        data = rapi.imageDecodeRaw(untwid, imgWidth, imgHeight, "r8 g8 b8 p8")
        texFmt = noesis.NOESISTEX_RGBA32

```

edit
is all in this thread obsolete now? 
[viewtopic.php?f=16&t=16580](http://forum.xentax.com/viewtopic.php?f=16&t=16580)
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-09-11T01:38:47+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

> Reply from AceWell
>
> looks ok but the texture size should be 512x512 me thinks, you can see the repeat
Oh right, didn't realize that.  
edit: looks like there's something wrong with my browser 

> Reply from AceWell
>
> 
is all in this thread obsolete now? 
viewtopic.php?f=16&t=16580

It shows almost all necessary info of the process of these tools. So if someone's gonna support bones and
anims of this game some day it might come in handy. But for now it indeed is obsolete.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-12-21T08:47:08+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

Updates: Add vertex normals support for PS3 version. Results from X360 version don't seem perfect since their normals were stored in a slightly different way but that's the best I can do for now.
## Post #9
- Username: Willi Miner
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 16, 2018 8:07 pm
- Post datetime: 2018-03-16T12:34:40+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

> Reply from Bigchillghost
>
> Several renders I made for some of the suits. You could find them in DVD_HQFrontEnd.pkg.

Hi. I have 2 questions: Are these models form Iron man 1/ 2 the video game? And 2, is there a download link to obtain those models?
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-16T13:03:55+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

> Reply from Willi Miner
>
> Are these models form Iron man 1/ 2 the video game?
Otherwise? I guess the topic is clear enough.

> Reply from Willi Miner
>
> And 2, is there a download link to obtain those models?
Not sure. Obviously won't by me. I only release the tools. The rest is on your own.
## Post #11
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-03-19T14:32:13+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

Hey mate, pretty awesome toolest. Thanks for it. I've been ripping models from the game and run into a bit of a problem with characters. It seems the "LASH" meshes don't convert properly and I was hoping this epic tool could get an update to fix this one flaw. In case it's needed, I'm using the XBox 360 version of Iron Man 2.

I've taken some screenshots of Black Widow, Iron Man and War Machine so you know what I mean:
[spoiler]



[/spoiler]

I've also uploaded the problematic meshes to my google drive account:
[https://drive.google.com/open?id=1PTe-C ... m13gOY19H7](https://drive.google.com/open?id=1PTe-CUVMpSY-yxGh3jfAZNm13gOY19H7)

Thanks for taking the time to read and check into this and hopefully I hear back from you soon;
Ecelon
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-20T15:32:46+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

> Reply from Ecelon ↑Tue Mar 19, 2019 10:32 pm at Tue Mar 19, 2019 10:32 pm
>
> It seems the "LASH" meshes don't convert properly
Yeah, a stupid bug I wasn't aware when creating the tool. Tools been updated now.
## Post #13
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-03-21T06:46:16+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

Hey mate, thanks for fixing that bug. The models look great now. There is however a new problem. The meshes no longer have their original UV's. Thanks again for the fix, and thought I'd let you know.
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-21T07:28:35+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

> Reply from Ecelon ↑Thu Mar 21, 2019 2:46 pm at Thu Mar 21, 2019 2:46 pm
>
> The meshes no longer have their original UV's.
My bad. Forgot to restore the code after the debugging stage.   
Tool reuploaded now.
## Post #15
- Username: Ar7579009
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Apr 28, 2019 10:28 pm
- Post datetime: 2019-05-06T14:09:50+00:00
- Post Title: Iron Man 2 (PS3 & Xbox 360) Tool Sets

> Reply from Bigchillghost ↑Thu Mar 21, 2019 3:28 pm at Thu Mar 21, 2019 3:28 pm
>
> 
Ecelon wrote: ↑Thu Mar 21, 2019 2:46 pmThe meshes no longer have their original UV's. 

My bad. Forgot to restore the code after the debugging stage.   
Tool reuploaded now.

Hi  bigchillghost  i hope you remember me.
your avengers playground script helped me alot.
i need you help once more please take efforts once more
would you please upload exported models.
i have an how to export .pkg files but the problem is that i don't have iron man 2 game to work on its files and game store aren't interested to download again and i am not getting correct link to downloaded whole game.
if you please upload .obj with textures of these models
TONY STARK
RHODES
NICK FURY 
BLACK WIDOW
## Post #16
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-05-30T18:26:43+00:00
- Post Title: Re: Iron Man 2 (PS3 & Xbox 360) Tool Sets

Hello just wanted to say thank you for this tool.
## Post #17
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-09T14:07:42+00:00
- Post Title: Re: Iron Man 2 (PS3 & Xbox 360) Tool Sets

Does this tool support bone/weights extraction?
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-09T15:50:51+00:00
- Post Title: Re: Iron Man 2 (PS3 & Xbox 360) Tool Sets

No it doesn't.
## Post #19
- Username: BinguBun
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 26, 2023 1:27 pm
- Post datetime: 2023-08-07T08:47:00+00:00
- Post Title: Re: Iron Man 2 (PS3 & Xbox 360) Tool Sets

Is it possible to use this for Iron man 1? because i'm having a lot of trouble extracting the .pkg from it
