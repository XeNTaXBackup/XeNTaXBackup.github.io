## Post #1
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-09-27T23:26:46+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

EDITED (10/3/2018):
Just put this out there so if anyone can write a Noesis/Max plugin to import/export this game then here's some mode samples 3MB ([https://drive.google.com/open?id=1hrUJM ... tPD7NvzE9M](https://drive.google.com/open?id=1hrUJMHmhhwtitut79mpaYLtPD7NvzE9M))...
Here's the full folder with everything extracted 743MB ==> [https://drive.google.com/open?id=16XYbB ... TMxPmfxd7G](https://drive.google.com/open?id=16XYbBh2uQB9wxi92o47aOaTMxPmfxd7G)
----------------------------------------------------------------------------------------------------------
Hi, I know this game has multiple versions in the past... but this JX3 HD Remake look really awesome and I'm just posted here cuz I checked the other posts and I don't think it's been cover yet (or sorry if I missed it).

This game has a total of 74.5GB of .DAT files and .IDX files (mostly .dat files... I don't know if these dat files can just be imported into Noesis/Max/Blender by writing some script on it or maybe it need to be extracted from the dat files first). So if anyone can help extract these DAT files, then you have my thanks and anyone who is interested in the future.

Sample file 202MB [https://drive.google.com/open?id=1PD7W4 ... L-15LbQkWH](https://drive.google.com/open?id=1PD7W4hxY1HF5c0EoOCPBhgL-15LbQkWH)

If need more sample, just let me know... I'll upload them ASAP.
Here's some Screenshots

[http://image.9game.cn/2018/3/2/19669711.jpg](http://image.9game.cn/2018/3/2/19669711.jpg)
[http://jx3.xoyo.com/uploadfile/2018/030 ... 524187.jpg](http://jx3.xoyo.com/uploadfile/2018/0302/20180302093524187.jpg)
[http://jx3.xoyo.com/uploadfile/2018/030 ... 519705.jpg](http://jx3.xoyo.com/uploadfile/2018/0302/20180302093519705.jpg)
-----------------------------------------------------------
Game Site: [http://jx3.xoyo.com/index/](http://jx3.xoyo.com/index/)
MMOByte Overview: [https://www.youtube.com/watch?v=MIv731kIFu4](https://www.youtube.com/watch?v=MIv731kIFu4)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
All the necessary tool(s) from this thread is here. [https://drive.google.com/open?id=18UGXT ... cWytrWQFuP](https://drive.google.com/open?id=18UGXTvSZf8V_ci027yG2DicWytrWQFuP)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-28T12:39:21+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

You can use this BMS script to unpack the chunks as a first step:


 datUnpack.rar
(513 Bytes) Downloaded 141 times


Just select the dat file as input and leave the rest to the script.

No time to dig into the format. Sorry about that.
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-09-28T15:55:05+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

Looks pretty cool, could someone share model samples after extraction?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-28T16:03:10+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

I didn't find face indices in the orgUncompressed folder at a first glance.
Here's some file types in the orgCompressed folder:



JX3-data.jpg (111.22 KiB) Viewed 820 times
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-28T16:24:51+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

The raw data size of chunk 0 is around 110 mb while it's almost the equal size after decompression. Maybe there's another layer of compression. Chunks with smaller size seem OK though, like in chunk_1 there're some texture name strings and material info. 
Edit: Never mind. It's just a mp4 file.

BTW, data of some chunks in the orgUncompressed folder seem to be in big-endian.
## Post #6
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-01T18:05:56+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

Hi thanks a lot guys... I've used the datUnpack.bms script and got a lot of chunks .dat files from it. There's like 250+ folders with their respective .dat files from the game. So it's gonna take a while to find where the models are.
I'll upload some samples to here and see if anyone can make sense of anything.
[https://drive.google.com/open?id=1647lR ... iTcAQOMVPn](https://drive.google.com/open?id=1647lRspq02iW9-2p8-f6J4iTcAQOMVPn)
It would be easier to identify the models through the textures but since there's like 300 files to extract from, I'll upload it once I got any lead.
In the mean time, here's some additional samples (not extracted) 
[https://drive.google.com/open?id=14Oafz ... YdgQNsexPk](https://drive.google.com/open?id=14OafzAJRofshsHJHTs4bv6YdgQNsexPk)
[https://drive.google.com/open?id=1kNlFI ... KN8Q_6nmTF](https://drive.google.com/open?id=1kNlFIkS4U9k8I4Kw5aiF2HKN8Q_6nmTF)
[https://drive.google.com/open?id=1pNsT2 ... LZDFWJNHiB](https://drive.google.com/open?id=1pNsT2zjZK2IGJDiuPdCwp7LZDFWJNHiB)
[https://drive.google.com/open?id=1YbOpx ... zXw7tcZZPa](https://drive.google.com/open?id=1YbOpxYBV7o4XSQCOOCH_5AzXw7tcZZPa)
## Post #7
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-01T20:23:30+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> You can use this BMS script to unpack the chunks as a first step:
datUnpack.rar
Just select the dat file as input and leave the rest to the script.

No time to dig into the format. Sorry about that.

Hi Bigchillghost, thanks for the script...
I kept running into these issues running out of memory so I can't extract all these .dat files... I had 32GB RAM on my machine so I kinda doubt that's the main issue.
Sample [https://drive.google.com/open?id=1cV4Xz ... c0prvQ3Cgb](https://drive.google.com/open?id=1cV4XzPT0AvLoMV4tjBPsXnc0prvQ3Cgb)


And sometime it show the message 
"Not enough storage is available to process this command." but I don't remember which file it was so I can't provide you a sample. 

I've used both the normal quickbms.exe and quickbms_4gb.exe... They pretty much the same... So I guess some of the header got messed up in these files or something.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-02T11:00:17+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18
>
> 
In the mean time, here's some additional samples (not extracted)
The script works fine with these files(tested on the first sample). You just need to wait patiently before you witness any output info.

> Reply from petventh18
>
> Hi Bigchillghost, thanks for the script...
I kept running into these issues running out of memory so I can't extract all these .dat files... I had 32GB RAM on my machine so I kinda doubt that's the main issue.
I modified the script to export correct file extensions this morning, but when I was testing it, that issue occurs to me on the same file that my script handled correctly twice before. I guess it might be some bugs of QuickBMS. So I decided to make a standalone tool for unpacking the assets. It's roughly tested on several samples(the one in the first post and the one from the first url) but it's still a beta.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-02T11:14:17+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

Here's a x86 release of the tool:


 JX3HDUnpacker.7z
v0.2.0 (147.99 KiB) Downloaded 146 times


Place them in the dir of the dat/idx files and double-click the .bat to run the program in batch command.
It'll log all text info into a new corresponding file(.txt or .json) within 8 megabytes for convenience of reading, unless current text chunk has already exceed that size.

Note: Files end with ".TBD" means their extensions are to be determined.
## Post #10
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-02T18:53:18+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> Here's a x86 release of the tool:
Place them in the dir of the dat/idx files and double-click the .bat to run the program in batch command.
It'll log all text info into one corresponding file(.txt or .json) for convenience of reading.
Oh thanks so much, work like a charm... I tested and worked on most files... Here's the files that had a model textures and some .mesh files along with some subtitle scripts too...
60MB  ===> [https://drive.google.com/open?id=1FcQyb ... LvWG2SNMFH](https://drive.google.com/open?id=1FcQyb1KJCPRlRzfkmSF1KZLvWG2SNMFH)
743MB ==> [https://drive.google.com/open?id=16XYbB ... TMxPmfxd7G](https://drive.google.com/open?id=16XYbBh2uQB9wxi92o47aOaTMxPmfxd7G)

...with this maybe someone can help write a Noesis/Max script to import/export them.

There's still some files that came out empty such as this screenshot... but since it can already extracted the textures and mesh files from some other .dat files, I guess these files not necessarily contain any more models (I hope)... I guess the only thing I might miss is if these are animation files or something. 

Here's a sample of the file that can't be extracted.
596MB ==> [https://drive.google.com/open?id=12i5GJ ... 8n2Pn3IWIe](https://drive.google.com/open?id=12i5GJMivmJA2ArfPnWggYI8n2Pn3IWIe)
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-03T04:17:06+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18
>
> There's still some files that came out empty such as this screenshot... but since it can already extracted the textures and mesh files from some other .dat files, I guess these files not necessarily contain any more models (I hope)... I guess the only thing I might miss is if these are animation files or something. 
Here's a sample of the file that can't be extracted.
Well it's just an issue resulting from the illegal extensions. I've improved the code for determining them, especially more accurately for the mesh files so you might need to run the [lastest version](http://forum.xentax.com/viewtopic.php?p=144645#p144645) on all packages again. Sorry about that.
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-03T09:31:13+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18
>
> Here's the files that had a model textures and some .mesh files along with some subtitle scripts too...
743MB ==> https://drive.google.com/open?id=16XYbB ... TMxPmfxd7G
Mesh from 000003B3.mesh:



000003B3.mesh.jpg (72.9 KiB) Viewed 758 times


And the one from 000005E0.mesh:



It seems that the model needs proper scaling to get the perfect mesh.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-03T10:22:44+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> It seems that the model needs proper scaling to get the perfect mesh.I don't even know how this can work: floats for the mesh don't fit into an FVF of 6?
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-03T10:36:13+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

> Reply from shakotay2
>
> I don't even know how this can work: floats for the mesh don't fit into an FVF of 6?
You mean the 6 floats before the vertex buffer?
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-03T11:11:06+00:00
- Post Title: JX3 HD Remake 剑网3 (.dat files)

FVFsize= 6; but I see, it's ShortAll (instead of WordUV, which you seem to have used for uvs' displaying only.)

My confusion also aroused from the fact that there seems to be 6 floats values (bounding box) before the mesh using shorts.
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-03T11:19:59+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from shakotay2
>
> FVFsize= 6; but I see, it's ShortAll (instead of WordUV, which you seem to have used for uvs' displaying only.)
Oh, I forgot that WordUV is actually using float as vertex type. 

> My confusion also aroused from the fact that there seems to be 6 floats values (bound box) before the mesh using shorts.
Yeah, I guess it's related to the scaling of the model. There're also 3 floats before the UV buffer. Maybe a scaling for UVW?
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-03T15:16:55+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18
>
> ...with this maybe someone can help write a Noesis/Max script to import/export them.well, I'm not a fan of writing scripts but as a first helper this tool may serve:


 Make_obj-JX3.zip
(68.69 KiB) Downloaded 52 times


Uses simple formula for getting the uvs' start address, so might fail.
Tested with 00000506.mesh and 00000163.mesh only!

Might make sense to manually insert some g SM_x lines into the MakeObj_log.obj in case there's submeshes.

You might try this H2O file for 00000163.mesh with hex2obj (0.24e required to have the 'unsigned shorts' box checked!)

0x70061 56925
Vb1
6 99
0x12C 18341
040300
0x3A499 6

(It produces an obj file (File/SaveAs mesh) with g SM_x lines inserted each 500 faces.)
------------------------------

The H2O file for 00000161.mesh is

0x5588D 34152
Vb1
6 99
0x12C 14001
040300
0x2C835 6

With the tool you'll need to correct the uvs startaddress here.
In the lower left editbox it reads 2C833 after loading the above mentioned mesh file. When checking this in a hexeditor you'll see (with a little experience) that the auto calculation is 2 bytes "off".

So exit (important!) and restart the tool, don't load the mesh!

In the editbox type 2C835, no typos, please!
then load the 00000161.mesh again.

The procedure may be required for other *.mesh, too, review the proposed uv start address in a hexeditor to decide whether it must be corrected.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-03T15:32:43+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

"submeshes" 500 faces each:



00000506-mesh.png (147.66 KiB) Viewed 248 times
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-03T19:46:14+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

00000158.mesh, x and y scaled by 2.0:



00000158-ship.png (196.03 KiB) Viewed 239 times
## Post #20
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-03T20:00:55+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> Well it's just an issue resulting from the illegal extensions. I've improved the code for determining them, especially more accurately for the mesh files so you might need to run the lastest version on all packages again. Sorry about that.
Oh thank you for the update. 

> Reply from shakotay2
>
> well, I'm not a fan of writing scripts but as a first helper this tool may serve:...
Thank you... it help... I'll try to shamelessly to modified some Noesis script to see if I can make it work for this game... that way it'll be easier to export them in batch.
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-04T03:42:44+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from shakotay2
>
> 00000158.mesh, x and y scaled by 2.0:
Had you used the bounding box?



000003B3.jpg (59.76 KiB) Viewed 227 times


Seems OK with the character:


Now the problem is to get correct normal vectors:
## Post #22
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-04T04:16:18+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> 

It seems that the model needs proper scaling to get the perfect mesh.
I put everything that appear on your screenshot but I don't have the same thing...
Can you give me some pointer?

I don't have a checkbox right after the dropbox "ShortAll" so I think that's the reason.
## Post #23
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-04T04:24:00+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

You need version 0.24e to handle unsigned shorts.
[viewtopic.php?p=142434#p142434](http://forum.xentax.com/viewtopic.php?p=142434#p142434)
## Post #24
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-04T04:28:12+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> You need version 0.24e to handle unsigned shorts.
viewtopic.php?p=142434#p142434
Oh lol stupid me... I reread shakotay2 post and he did mentioned it... I was being dumb...

But yeah after I used version 0.24e this is what I got...


It look like some backcurling happening there... but it look different than yours.
## Post #25
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-04T04:34:39+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

I just import it into Max and inverted the normals.
## Post #26
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-04T04:37:09+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> I just import it into Max and inverted the normals.
Oh yeah you're right nvm, your model SS was from 3d software... so I was being dumb again. 
But can you tell me how you got the start address and count and then the FVF Size? I watch some youtube video on how to use Hex2Obj but i kept getting different numbers than yours.
## Post #27
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-04T04:43:59+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

Here's the structure of the header from offset 0x90:

```
long	TrixCount
long	MtlGroupCount
long	Voffset // 6 floats for bounding box before vertex data
long	NormalOffset
long	NULL
long	UVoffset // 3 floats before UV data
long	NULL
long	NULL
long	FIoffset
long	MtlGroupOffset

```

So the face indices count would be (TrixCount * 3).
## Post #28
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-04T04:56:47+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from shakotay2
>
> 
Might be senseful to manually insert some g SM_x lines into the MakeObj_log.obj in case there's submeshes.
Is that how you split the mesh into multiple parts? Such as cloth, hair, head, face, etc?
Because I noticed the Make_obj-JX3.exe tool combined all of them into one mesh while Hex2Obj had them separated into submeshes.
Is it possible to do so as well?
## Post #29
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-04T04:59:47+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> Here's the structure of the header from offset 0x90:
Code: Select alllong	Vcount
long	TrixCount
long	MtlGroupCount
long	Voffset // 6 floats for bounding box before vertex data
long	NormalOffset
long	NULL
long	UVoffset // 3 floats before UV data
long	NULL
long	NULL
long	FIoffset
long	MtlGroupOffset

So the face indices count would be (TrixCount * 3).
Thank you for the structure... that helps!
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-04T08:15:47+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> Had you used the bounding box?nope, just a wild guess, because the BBox calculated from the unsigned vertex data in hex2obj doesn't match with the real values so far. Need to look what's going wrong there:
# BBox 0.000000 255.468750, 0.000000 255.468750, 0.000000 255.468750



00000503-mesh-BBox.png (31.48 KiB) Viewed 213 times



> Reply from petventh18
>
> shakotay2 wrote:
Might be senseful to manually insert some g SM_x lines into the MakeObj_log.obj in case there's submeshes.

> Is that how you split the mesh into multiple parts? Such as cloth, hair, head, face, etc?Didn't check a character so far, but 'yes', hex2obj inserts such lines all 500 faces each.

> Because I noticed the Make_obj-JX3.exe tool combined all of them into one mesh while Hex2Obj had them separated into submeshes.
>
> Is it possible to do so as well?Is possible, but generally that splitting results in random submeshes (SMs). It's just kind a luck that the static models seem to have roundabout 500 faces clusters here, imho.

So for characters it's more sensefull to insert those lines manually, as there's aren't so many SMs, head, upper body, lower body for example.
## Post #31
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-04T11:11:36+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from shakotay2
>
> because the BBox calculated from the unsigned vertex data in hex2obj doesn't match with the real values so far. Need to look what's going wrong there:
# BBox 0.000000 255.468750, 0.000000 255.468750, 0.000000 255.468750
Why does it need to match with the calculated bounding box? I think they're using unsigned shorts to map with the floats within the BBox so that they won't lose too much precision. So we just need to divide the bounding box space into 65535 segments on each axis to get their corresponding scale units.
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-04T12:00:13+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

yeah, my bad, I thought the BBox auto calculation went wrong, but seems it doesn't 

65535? depends on your divider when creating the mesh - I just need to divide 5376.0376 by 255.469 for the x-scaling for example.

well, seems to fit:



scale 21,6.2,16.png (39.08 KiB) Viewed 356 times
## Post #33
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-05T00:26:38+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from shakotay2
>
> Is possible, but generally that splitting results in random submeshes (SMs). It's just kind a luck that the static models seem to have roundabout 500 faces clusters here, imho.
So for characters it's more sensefull to insert those lines manually, as there's aren't so many SMs, head, upper body, lower body for example.
I see, thank you... 
I'm just wondering, is it possible for you to add some code to the Make_obj-JX3.exe tool to make it so the output .obj file had the same name as the .mesh file? 
And if it's not too much trouble then maybe add batch feature to the tool too? Cuz this game had too many files and going through each .mesh at a time is really tedious and tiring to find the player models. Sorry for nagging so much... Just ignored my babbling if it's too much trouble =)

EDITED:
I tested a few of the meshes using Make_obj-JX3.exe tool and these 3 samples are the one that cannot be imported into 3D Software after forming the obj file.
[https://drive.google.com/open?id=1FoZn5 ... t1Qogf4E5y](https://drive.google.com/open?id=1FoZn55KLbfGVWxUsgaoyn2t1Qogf4E5y)
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-05T10:06:48+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18
>
> I'm just wondering, is it possible for you to add some code to the Make_obj-JX3.exe tool to make it so the output .obj file had the same name as the .mesh file? 
And if it's not too much trouble then maybe add batch feature to the tool too? Cuz this game had too many filesyeah, I was thinking about this since a long time. The batch feature is simple for console apps, but a GUI app needs an auto exit feature like SendMessage (hwnd, WM_CLOSE, 0L, 0L) ; which I used; but not sure about the side effects.  

But didn't you plan to create a Noesis script?

> EDITED:
>
> I tested a few of the meshes using Make_obj-JX3.exe tool and these 3 samples are the one that cannot be imported into 3D Software after forming the obj file.yeah, I see. Would require to use the addresses from the "magic table" at 0x90 where I only take the counts from so far. (Auto calculation of addresses doesn't seem to work for all files.)
## Post #35
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-05T19:04:01+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from shakotay2
>
> But didn't you plan to create a Noesis script?
I've only started learning C# language a year ago  (so still super noob when come to program languages)... And when I tried python script along with some example plugin from other games and some tutorial on Youtube... it's basically a nightmare for noobie such as myself since every script seem to different from one another when it come to section like 

```
def noepyLoadModel(data, mdlList):
```
 or 
> class mesh(object): or 
```
class mesh(SanaeObject):
```
... There's so many variation that I can't do it with my current skill... I guess I'll have to start learning python first before attempting again...    

> yeah, I see. Would require to use the addresses from the "magic table" at 0x90 where I only take the counts from so far. (Auto calculation of addresses doesn't seem to work for all files.)
Since can't change the offset from the tool, I guess will have to manually using Hex2Obj...
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-05T21:25:37+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18
>
> it's basically a nightmare for noobie such as myself since every script seem to different from one another when it come to section likeI have a deja vue  
Yea, I know that feeling; here's some simple script for beginners with some Noesis/python knowledge:
[viewtopic.php?f=16&t=9534&p=141865&hili ... an#p141865](http://forum.xentax.com/viewtopic.php?f=16&t=9534&p=141865&hilit=snowman#p141865)
(ah, see, there's some math with the face indices buffer, feel free to ask, why, that's a matter of the format, not of python)
(Noesis is a powerful tool, there's absolutely no doubt, but the first scripting steps, are not so nice.  )

> Since can't change the offset from the tool, I guess will have to manually using Hex2Obj...That's a good start, imho.
But for hundreds of *.mesh files you might prefer this one (cmd line tool, GUI pops up and exits):


 Make_obj-JX3_cmdline.zip
(16.67 KiB) Downloaded 57 times


tested with 3 files only
 you need the dlls from the previous zip
 you need to adjust the "path to the exe" in the .cmd file.
 blanks in *.mesh pathname not supported!
 start the cmd file in the folder where your *.mesh files reside

btw: you might drag 'n drop a single *.mesh onto the exe, too
## Post #37
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-05T22:48:24+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from shakotay2
>
> ...here's some simple script for beginners with some Noesis/python knowledge:
viewtopic.php?f=16&t=9534&p=141865&hili ... an#p141865
(ah, see, there's some math with the face indices buffer, feel free to ask, why, that's a matter of the format, not of python)....
But for hundreds of *.mesh files you might prefer this one (cmd line tool, GUI pops up and exits):

Thanks a lot for the info and for the tool update... it'll save me lots of time to sort through those models...

You mentioned that the UVs is 2 bytes off... so restart the tool and type in the new value on the editbox... then load the same mesh again, correct? Because it's hard to find the correct texture for the correct model since they're name differently... would be so nice if the name of texture match well like how Umodel arrange them... or even like how Ninja Ripper did it...
I wonder how the developer even keep track on all their models/texture with all these kind of names... or is it that the extract tool automatically rename them?
## Post #38
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-06T00:52:07+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18
>
> I wonder how the developer even keep track on all their models/texture with all these kind of names... or is it that the extract tool automatically rename them?
There do seem to be some text recording the asset names but not every package outputs them, and some of these info is in json format which makes it so annoying/difficult to read. Yep you're correct the tool names them automatically using the orders of their chunks.
## Post #39
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-06T02:59:23+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> There do seem to be some text recording the asset names but not every package outputs them, and some of these info is in json format which makes it so annoying/difficult to read. Yep you're correct the tool names them automatically using the orders of their chunks.
Ah I c... thanks for clearing that up... I opened the json file on Notepad++ and only some .srt are recorded in it... 
ex: "srtFile": "data\\source\\maps_source\\树入库临时保存\\s_雪竹019c4_st.srt"
But the output file will be something like 0000XXXX.SRT 

And the .SRT files itself does have some texture name recorded like 
(SP_wanhuashupi001H.tga  SP_wanhuashupi001H_Nor.tga  SP_wanhuashupi001   S_wanhuazitengluo002.tga    S_wanhuazitengluo002_Nor.tga    Atlas   S_wanhuazitengluo002_Billboards.tga S_wanhuazitengluo002_Billboards_Nor.tga...)
So based on that we can see some diffuse and normal texture that are corresponding to the  wanhuashupi001.mesh...

But because everything was renamed, it will take a lot of guessing game to match the correct texture into the model (assuming that the UV is correct after turning the mesh to obj)...

If it's not too much trouble then may I ask if it's possible to modify the extraction tool to not rename the file based on the chunk but leave it as is? (Doesn't matter if it's Chinese characters)... Some folder had over 6000 files, so trying to guess their texture based on the current name is quite literary a nightmare.
That or maybe had a .log file that keep track of the original name to the current exacted name?
And again, if it's too much of a hassle then forget about it... I'm already very thankful that you created the tool as it is.
## Post #40
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-06T03:51:21+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18
>
> assuming that the UV is correct after turning the mesh to obj
Well, about that, have you checked if they're mapping?

> Reply from petventh18
>
> 
If it's not too much trouble then may I ask if it's possible to modify the extraction tool to not rename the file based on the chunk but leave it as is?
Maybe. That would require more research on the organization of the chunks, which can take some time. I'll see what I can do with it. But don't expect too much yet.

Edit: I can say that it's impossible to read filenames now because:
- The assets are linked by different objects in the json files, usually more than one times for each asset, and you can't locate the asset names with the MD5 hashes coz they don't even esixt in the json;
- There do seem to be a filelist in a certain json file, and there're some texture names in a binary chunk(using the ext .def in the following version), but their amounts and extensions don't match with the actual outputs, nor their sums.

> Reply from petventh18
>
> Doesn't matter if it's Chinese characters...
I was wondering if the names will output correctly if they contain any Chinese. I hope I don't have to deal with the character encoding stuffs.

> Reply from petventh18
>
> Some folder had over 6000 files, so trying to guess their texture based on the current name is quite literary a nightmare.
Ah, I can imagine that. 

> Reply from petventh18
>
> That or maybe had a .log file that keep track of the original name to the current exacted name?
Sounds good, but not necessary, nor possible. Because the tool didn't read any filenames at all. It just decompresses each chunk and assigns the index of the loop to the string buffer as the output filename (in hex). The simplest solution is to save every chunk with a decimal index name so that you can sort them with your Windows explorer. It still needs your guessing work though. But it's an alternative. Better than nothing.

Edit: Now you can have it:


 JX3HDUnpacker.rar
v0.3.0 (162.37 KiB) Downloaded 116 times


Changes:
- Changed naming patterns from hex to decimal index;
- No text/json files will be merged;
- Improve detection of text/json data (first 4 bytes only).
- The files with the signature "\x08\x00\x00\x00" will be separated from the TBD files, using the extension ".8";
- The binary chunk(s) containing texture names will use the extension ".def".
## Post #41
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-06T07:05:19+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18
>
> shakotay2 wrote:...here's some simple script for beginners with some Noesis/python knowledge:
http://forum.xentax.com/viewtopic.php?f ... an#p141865
(ah, see, there's some math with the face indices buffer, feel free to ask, why, that's a matter of the format, not of python)....
But for hundreds of *.mesh files you might prefer this one (cmd line tool, GUI pops up and exits):


Thanks a lot for the info and for the tool update... it'll save me lots of time to sort through those models...I wasn't sure if it would work for 100s of models...  

> You mentioned that the UVs is 2 bytes off... so restart the tool and type in the new value on the editbox... then load the same mesh again, correct?Forget about that; that's for the old version with auto calculation of addresses; sometimes it gave incorrect values (2 bytes off for example) for the uvs' start.

The cmdline version gets all values from  the magic table at 0x90 (counts and addresses) now. But it "relies" on a 12 bytes offset in the uvs' block (3 floats to be skipped before the uv data).

btw: this format is a very good start to be used with a Noesis script (you don't need the face indices buffer math in my previous linked sample).
The codelines for getting the face indices should look like this (untested):
faceBuff = bs.readBytes(faceCount*3*4)
rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_UINT, faceCount*3, noesis.RPGEO_TRIANGLE, 1)
UINT because of DWord face indices
and you don't need this weird
 b = struct.pack('H' * len(idxBuf), *idxBuf) for this format

here's a working Noesis script, tested with 00000161.mesh:

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("JX3", ".mesh")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    bs = NoeBitStream(data)
    bs.seek(0x54, NOESEEK_ABS)
    idstring = bs.readUInt()
    if idstring != 0x4D455348:
        print("not a JX3 file!")
        return 0
    return 1

def noepyLoadModel(data, mdlList):    
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    #rapi.rpgClearBufferBinds()
    bs.seek(0x90, NOESEEK_ABS)
    vertsCount = bs.readUInt()
    faceCount = bs.readUInt()
    bs.seek(0xA8, NOESEEK_ABS)
    uvAddr = bs.readUInt()
    uvAddr += 12
    bs.seek(0xB4, NOESEEK_ABS)
    FIaddr = bs.readUInt()

    bs.seek(0x12C, NOESEEK_ABS)
    VertBuf = bs.readBytes(vertsCount * 6)
    bs.seek(uvAddr, NOESEEK_ABS)
    uv1Buf = bs.readBytes(vertsCount * 6)
    bs.seek(FIaddr, NOESEEK_ABS)
    idxBuf = bs.readBytes(faceCount*3*4)
    rapi.rpgBindPositionBufferOfs(VertBuf, noesis.RPGEODATA_USHORT, 6, 0)
    rapi.rpgBindUV1Buffer(uv1Buf, noesis.RPGEODATA_USHORT, 6)
    rapi.rpgCommitTriangles(idxBuf, noesis.RPGEODATA_UINT, faceCount*3, noesis.RPGEO_TRIANGLE, 1)

    mdl = rapi.rpgConstructModel()
    mdlList.append(mdl)

    return 1

```
(Maybe I should have used some NOESEEK_REL constants but I'm too lazy to calculate the required offsets.  )

edit: attaching above mentioned sample, in case it's not available any more:


 00000161.zip
(218.75 KiB) Downloaded 18 times



Also I didn't care for the normals buffer, as always.
addr can be found in the magic table; refer to the struct that Bigchillghost posted.
## Post #42
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-08T12:15:45+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> Now the problem is to get correct normal vectors:
I can't believe that they actually packed the normals in this way. You need to perform the following operations to get the correct normals:

```
{
	dblNM[i].x = charNM[i].x / 127.0;
	dblNM[i].y = charNM[i].y / 127.0;
	dblNM[i].z = charNM[i].z / 127.0;
	if (dblNM[i].x < 0.0)
		dblNM[i].x = -dblNM[i].x - 1.0;
	if (dblNM[i].y < 0.0)
		dblNM[i].y = -dblNM[i].y - 1.0;
	if (dblNM[i].z < 0.0)
		dblNM[i].z = -dblNM[i].z - 1.0;
	dblNM[i].x = -dblNM[i].x;
	dblNM[i].y = -dblNM[i].y;
	dblNM[i].z = -dblNM[i].z;
}
```

Test result:



normals.jpg (128.71 KiB) Viewed 296 times


Is that a common case?
## Post #43
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2018-10-09T01:41:11+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

@shakotay2
Thanks for the script... It make it a lot easier for noobie me  Although I couldn't get the CMD version of the tool to work at all. I place the prev folder with some .mesh inside of it. But it just won't do anything when click or drag a mesh file to it. I made sure to rename the path inside the .cmd file as well...

But it's very hard matching the texture and model so I decided to buy an Xoyo account and tried my luck with Ninja Ripper... good thing it worked... 



So if anyone don't wanna sort through the mesh manually then try Ninja Ripper... the down side is that you can only rip the model you see and you'll have fking nightmare trying to register for a game account without a chinese phone number. And the face and hair position don't match properly so you have to manually trying to put it together.
## Post #44
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-11-03T15:13:34+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

Probably this is pointless but here's the truth: since I've updated my binary FBX builder to support face materials and other features, 
this format had been the perfect sample for testing purpose. Wouldn't it be a waste if it'd never got released?  

For example here's one of the material group of the entire mesh from 000005E0.mesh (7 in total):


Note that the UVs endoced as WORD are a bit off the correct position which I have no clue of why. 
I made a little correction for this model only so it's not guaranteed to work for all UVs. 
For float UVs you don't have worry about it though.


 JX3Convertor.zip
(59.07 KiB) Downloaded 91 times


Just run the tool without prams to see the usage.
## Post #45
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2019-02-10T21:23:48+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost
>
> Probably this is pointless but here's the truth: since I've updated my binary FBX builder to support face materials and other features, 
this format had been the perfect sample for testing purpose. Wouldn't it be a waste if it'd never got released?  

For example here's one of the material group of the entire mesh from 000005E0.mesh (7 in total):


Note that the UVs endoced as WORD are a bit off the correct position which I have no clue of why. 
I made a little correction for this model only so it's not guaranteed to work for all UVs. 
For float UVs you don't have worry about it though.
The attachment JX3Convertor.zip is no longer available
Just run the tool without prams to see the usage.

Why can't I open?
[Untitled.png](https://xentaxbackup.github.io/file/15701_Untitled.png)
## Post #46
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2019-02-18T15:02:02+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18 ↑Tue Oct 09, 2018 9:41 am at Tue Oct 09, 2018 9:41 am
>
> 
@shakotay2
Thanks for the script... It make it a lot easier for noobie me  Although I couldn't get the CMD version of the tool to work at all. I place the prev folder with some .mesh inside of it. But it just won't do anything when click or drag a mesh file to it. I made sure to rename the path inside the .cmd file as well...

But it's very hard matching the texture and model so I decided to buy an Xoyo account and tried my luck with Ninja Ripper... good thing it worked... 



So if anyone don't wanna sort through the mesh manually then try Ninja Ripper... the down side is that you can only rip the model you see and you'll have fking nightmare trying to register for a game account without a chinese phone number. And the face and hair position don't match properly so you have to manually trying to put it together.
Can you share the model with me? I cannot register for a JX3 account
## Post #47
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-19T08:07:28+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from usabdt ↑Mon Feb 11, 2019 5:23 am at Mon Feb 11, 2019 5:23 am
>
> 
Why can't I open?

> Reply from Bigchillghost ↑Tue Oct 02, 2018 7:14 pm at Tue Oct 02, 2018 7:14 pm
>
> 
Here's a x86 release of the tool:
JX3HDUnpacker.7z
Place them in the dir of the dat/idx files and double-click the .bat to run the program in batch command.
It'll log all text info into a new corresponding file(.txt or .json) within 8 megabytes for convenience of reading, unless current text chunk has already exceed that size.

Note: Files end with ".TBD" means their extensions are to be determined.
## Post #48
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-16T08:02:23+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from petventh18 ↑Sat Oct 06, 2018 6:48 am at Sat Oct 06, 2018 6:48 am
>
> I wonder how the developer even keep track on all their models/texture with all these kind of names...
Just downloaded the game out of curiosity. Now I can tell you that it's really simple. The game provides options for users to manage assets on their drive, so that they can remove and download them at any time as you please. What else could you expect to make the most easy-to-extract game?  
The database of these assets are placed aside the asset folders in a file named Trunk.dir. And I logged all the names of the assets into a text file which eventually reached to 128 MB. Here's a few names from the begining of the list:

```
maps/唐门/v_001/039_region.map
maps/巴陵县/v_056/058_region.map
data/source/player/m1/部件/m1_4101/m1_4101_belt_nor.hdd2
maps/南屏山/v_062/052_region.map
maps/洛阳/v_027/042_region.map
represent/rl/00042400/00042634.krl
data/source/maps_source/texture/db_zcm机关哨塔001_01h.hdd2
...

```

There's also some human readable info in the PakV4Manager folder if you're interested.
## Post #49
- Username: kingh668
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 22, 2019 1:48 pm
- Post datetime: 2019-04-22T06:15:32+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Sat Mar 16, 2019 4:02 pm at Sat Mar 16, 2019 4:02 pm
>
> 
petventh18 wrote: ↑Sat Oct 06, 2018 6:48 amI wonder how the developer even keep track on all their models/texture with all these kind of names...

Just downloaded the game out of curiosity. Now I can tell you that it's really simple. The game provides options for users to manage assets on their drive, so that they can remove and download them at any time as you please. What else could you expect to make the most easy-to-extract game?  
The database of these assets are placed aside the asset folders in a file named Trunk.dir. And I logged all the names of the assets into a text file which eventually reached to 128 MB. Here's a few names from the begining of the list:
Code: Select allmaps/长安/v_031/035_region.map
maps/唐门/v_001/039_region.map
maps/巴陵县/v_056/058_region.map
data/source/player/m1/部件/m1_4101/m1_4101_belt_nor.hdd2
maps/南屏山/v_062/052_region.map
maps/洛阳/v_027/042_region.map
represent/rl/00042400/00042634.krl
data/source/maps_source/texture/db_zcm机关哨塔001_01h.hdd2
...

There's also some human readable info in the PakV4Manager folder if you're interested.

Hi,
How to extract Trunk.dir file content?
Can you share it?
## Post #50
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-20T06:11:02+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Sat Mar 16, 2019 4:02 pm at Sat Mar 16, 2019 4:02 pm
>
> 
petventh18 wrote: ↑Sat Oct 06, 2018 6:48 amI wonder how the developer even keep track on all their models/texture with all these kind of names...

Just downloaded the game out of curiosity. Now I can tell you that it's really simple. The game provides options for users to manage assets on their drive, so that they can remove and download them at any time as you please. What else could you expect to make the most easy-to-extract game?  
The database of these assets are placed aside the asset folders in a file named Trunk.dir. And I logged all the names of the assets into a text file which eventually reached to 128 MB. Here's a few names from the begining of the list:
Code: Select allmaps/长安/v_031/035_region.map
maps/唐门/v_001/039_region.map
maps/巴陵县/v_056/058_region.map
data/source/player/m1/部件/m1_4101/m1_4101_belt_nor.hdd2
maps/南屏山/v_062/052_region.map
maps/洛阳/v_027/042_region.map
represent/rl/00042400/00042634.krl
data/source/maps_source/texture/db_zcm机关哨塔001_01h.hdd2
...

There's also some human readable info in the PakV4Manager folder if you're interested.Hello mate , well first of all wanna say thanks for the wonderful job, now I have a question, some useful information how get correct file names in the files, the problem is Trunk.dir can't see file names, look like is crypted or something

when open with notepad++ ofc I see this, you sure say so if encrypted why you see that, wel no idea really, if you can give a hand really grateful for all your job in community, ok have a nice day.

DIRFILE�zk�   d:\qb\buildagent\workspace\root\JX3\zhcn_hd\BuildFarm\Tools\Common\PakV4\Database/FullPackage                                                                                                                                                                       Trunk                                                           �1p ��*w`X�  ��
    �      �      !      !      !      !      !      !      !      !      !      !      !      !      !      !
## Post #51
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-21T15:53:14+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Wed May 20, 2020 2:11 pm at Wed May 20, 2020 2:11 pm
>
> the problem is Trunk.dir can't see file names, look like is crypted or something

when open with notepad++ ofc I see this, you sure say so if encrypted why you see that, wel no idea really
I wouldn't consider binary plaintext as "encrypted". Getting only the names won't help you coz you'll need other info like package IDs, offsets and sizes etc. to extract corresponding assets. I wrote a resource unpacker over a year ago after the research on the database's format was finished, but never had the desire to release it. No idea whether the format has been changed or not ever since, or if the tool still work.
## Post #52
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-21T15:55:51+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Thu May 21, 2020 11:53 pm at Thu May 21, 2020 11:53 pm
>
> 
CriticalError wrote: ↑Wed May 20, 2020 2:11 pmthe problem is Trunk.dir can't see file names, look like is crypted or something

when open with notepad++ ofc I see this, you sure say so if encrypted why you see that, wel no idea really

I wouldn't consider binary plaintext as "encrypted". Getting only the names won't help you coz you'll need other info like package IDs, offsets and sizes etc. to extract corresponding assets. I wrote a resource unpacker over a year ago after the research on the database's format was finished, but never had the desire to release it. No idea whether the format has been changed or not ever since, or if the tool still work.understand bro, is possible test it? I can't send private message because you don't have avaliable it, so let me know if possible test it.
## Post #53
- Username: Seamoroar1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 24, 2018 12:17 am
- Post datetime: 2020-05-29T07:25:57+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

You can try Ninja Ripper



TIM截图20200529152446.png (166.93 KiB) Viewed 157 times
## Post #54
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-29T13:13:12+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

Yes thats good but is not the point, if somebody interested I get source code client + Tools for Visual Studio 2008
## Post #55
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-01T13:47:32+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Thu May 21, 2020 11:55 pm at Thu May 21, 2020 11:55 pm
>
> so let me know if possible test it.
Well, they updated the database format and replaced the asset names with some 10-byte sequences so the old tool no longer works. There're about 58 megabytes of extra data at the end of the dir file which might be a compressed string buffer. Not sure if it's encrypted or not.

> Reply from CriticalError ↑Fri May 29, 2020 9:13 pm at Fri May 29, 2020 9:13 pm
>
> 
I get source code client + Tools for Visual Studio 2008
Tools for what?
## Post #56
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-06-01T13:57:37+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Mon Jun 01, 2020 9:47 pm at Mon Jun 01, 2020 9:47 pm
>
> 
CriticalError wrote: ↑Thu May 21, 2020 11:55 pmso let me know if possible test it.

Well, they updated the database format and replaced the asset names with some 10-byte sequences so the old tool no longer works. There're about 58 megabytes of extra data at the end of the dir file which might be a compressed string buffer. Not sure if it's encrypted or not.
CriticalError wrote: ↑Fri May 29, 2020 9:13 pm
I get source code client + Tools for Visual Studio 2008

Tools for what?I get full source code of that game, with importers, exporters for 3ds max, etc but can't compile, lot of errors, but all information is there, so just in case because you do great work before, maybe this is more useful for you than me ofc, I work hard to get the source but nobmatter, I can provide it to work if you agree, just need a email or something to send this.
## Post #57
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-01T14:24:15+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Mon Jun 01, 2020 9:57 pm at Mon Jun 01, 2020 9:57 pm
>
> I get full source code of that game
But a project for VS2008? Is it actually for the remaked game? Also is it for recent a game version? 
You might try searching for the string "Trunk.dir" with case-insensitive in the source and see if there's a match.

There seem to be an official animation editor for this game with support of fbx export. Have you ever tried that?
## Post #58
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-06-01T15:03:07+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Mon Jun 01, 2020 10:24 pm at Mon Jun 01, 2020 10:24 pm
>
> 
CriticalError wrote: ↑Mon Jun 01, 2020 9:57 pmI get full source code of that game
But a project for VS2008? Is it actually for the remaked game? Also is it for recent a game version? 
You might try searching for the string "Trunk.dir" with case-insensitive in the source and see if there's a match.

There seem to be an official animation editor for this game with support of fbx export. Have you ever tried that?well I need try check files later, anyway no found about this animation editor you say, if you drop link rrally gratefull, and the problem anyway is get correct file names of the fimes, this is the major search, for that reason mention about source.
## Post #59
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-02T05:20:12+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Mon Jun 01, 2020 11:03 pm at Mon Jun 01, 2020 11:03 pm
>
> no found about this animation editor you say
Well they actually called it "movie editor". You'll find it at the game's official download page.
Entry: [https://jx3.xoyo.com/movieeditor/](https://jx3.xoyo.com/movieeditor/)
Index page: [https://movieeditor.jx3.xoyo.com/index.html](https://movieeditor.jx3.xoyo.com/index.html)

Tested it myself and you can customize your character and export to fbx.
## Post #60
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-06-02T10:59:16+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Tue Jun 02, 2020 1:20 pm at Tue Jun 02, 2020 1:20 pm
>
> 
CriticalError wrote: ↑Mon Jun 01, 2020 11:03 pmno found about this animation editor you say

Well they actually called it "movie editor". You'll find it at the game's official download page.
Entry: https://jx3.xoyo.com/movieeditor/
Index page: https://movieeditor.jx3.xoyo.com/index.html

Tested it myself and you can customize your character and export to fbx.well looking in the site I found yesterday, you right, the only problem is need account, because need login inclient and when try create one using fake chinese names and citizen id no work, always give verification name failure so it's useless
## Post #61
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-02T11:30:50+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Tue Jun 02, 2020 6:59 pm at Tue Jun 02, 2020 6:59 pm
>
> well looking in the site I found yesterday, you right, the only problem is need account, because need login inclient and when try create one using fake chinese names and citizen id no work, always give verification name failure so it's useless
You just need to create one with a phone number and type in the verification code you get from the text and that should be enough to give you access to the movie editor. Though you can't get into the game.
## Post #62
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-06-02T11:58:29+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Tue Jun 02, 2020 7:30 pm at Tue Jun 02, 2020 7:30 pm
>
> 
CriticalError wrote: ↑Tue Jun 02, 2020 6:59 pmwell looking in the site I found yesterday, you right, the only problem is need account, because need login inclient and when try create one using fake chinese names and citizen id no work, always give verification name failure so it's useless 

You just need to create one with a phone number and type in the verification code you get from the text and that should be enough to give you access to the movie editor. Though you can't get into the game.I don't know how you create it bro, im in the webpage and you can't avoid real name autentifcacion and citizen ID, it ask in the registration, the phone need be from china and I get one via online free sms, the problem is the citizen id and real name need be writen in chinese like say there.

as you can see in all type of registration are 3 are marked by *
## Post #63
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-06-02T13:25:16+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

try translating page maybe you will find a phone nomber registration way.

Anyway , could someone try that movie editor and tell us what you could do? Export option etc etc

I can't download the client and try myself.
## Post #64
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-02T13:48:56+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Tue Jun 02, 2020 7:58 pm at Tue Jun 02, 2020 7:58 pm
>
> I don't know how you create it bro, im in the webpage and you can't avoid real name autentifcacion and citizen ID, it ask in the registration, the phone need be from china and I get one via online free sms, the problem is the citizen id and real name need be writen in chinese like say there.
You should register from the game page here: [http://jx3.xoyo.com/](http://jx3.xoyo.com/)



reg.jpg (220.21 KiB) Viewed 155 times



> Reply from Drawing ↑Tue Jun 02, 2020 9:25 pm at Tue Jun 02, 2020 9:25 pm
>
> 
could someone try that movie editor and tell us what you could do? Export option etc etc
There're switches for textures and skining during export. You can combine character/creature mesh parts as you pleased and export them to fbx. It seems you can't export maps but only loading the scenes.
## Post #65
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-06-02T15:21:28+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

Which Number is work?:D
Mys to long:D
## Post #66
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-06-02T21:26:27+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Tue Jun 02, 2020 9:48 pm at Tue Jun 02, 2020 9:48 pm
>
> 
CriticalError wrote: ↑Tue Jun 02, 2020 7:58 pmI don't know how you create it bro, im in the webpage and you can't avoid real name autentifcacion and citizen ID, it ask in the registration, the phone need be from china and I get one via online free sms, the problem is the citizen id and real name need be writen in chinese like say there.

You should register from the game page here: http://jx3.xoyo.com/

reg.jpg
Drawing wrote: ↑Tue Jun 02, 2020 9:25 pm
could someone try that movie editor and tell us what you could do? Export option etc etc

There're switches for textures and skining during export. You can combine character/creature mesh parts as you pleased and export them to fbx. It seems you can't export maps but only loading the scenes.

many thanks. Does it load animation too so that it's possible to export them in fbx?
Criticall spoke about a plugin to import them, dunno know if he was speaking about this tool or other one
## Post #67
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-03T01:05:55+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

@CriticalError & @Drawing: a little advice? You both should really edit your posts to avoid unnecessary embedded quotes.

> Reply from Drawing ↑Wed Jun 03, 2020 5:26 am at Wed Jun 03, 2020 5:26 am
>
> Does it load animation too so that it's possible to export them in fbx?
Yeah animation is available too and that's why they called it the "movie editor". But I didn't try exporting with anim loaded. And now I have everything deleted from my drive and guess you'll have to find out yourself.
## Post #68
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-06-03T05:35:23+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

Can everywhere share a working Account? i cant registry with my telephone number because its too long.
## Post #69
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-06-03T16:07:50+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

well is not work for me, I register account all be ok, I set client path and anyway when open after seconds give a notificacion and close in seconds, never see interface of editor, no idea whats going on, I test in virtual machine and in main windows, both give me same error.



The engine could not initialize
## Post #70
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-03T16:22:48+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Thu Jun 04, 2020 12:07 am at Thu Jun 04, 2020 12:07 am
>
> no idea whats going on
You should be able to change the language to English from the combo box. Probably you didn't set the path correctly.
## Post #71
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-06-03T16:42:51+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Thu Jun 04, 2020 12:22 am at Thu Jun 04, 2020 12:22 am
>
> 
CriticalError wrote: ↑Thu Jun 04, 2020 12:07 amno idea whats going on

You should be able to change the language to English from the combo box. Probably you didn't set the path correctly.I test everything and no luck as you see.
## Post #72
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-03T16:50:35+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Thu Jun 04, 2020 12:42 am at Thu Jun 04, 2020 12:42 am
>
> 
Tried "Apply Selected Path"?
## Post #73
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-06-03T16:54:37+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Wed Jun 03, 2020 9:05 am at Wed Jun 03, 2020 9:05 am
>
> 
@CriticalError & @Drawing: a little advice? You both should really edit your posts to avoid unnecessary embedded quotes.


Yeah animation is available too and that's why they called it the "movie editor". But I didn't try exporting with anim loaded. And now I have everything deleted from my drive and guess you'll have to find out yourself.

oh sorry forgot to edit.

Ok i will try on free time. 
Maybe to register with phone number you should add your prefix.
## Post #74
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-06-03T23:41:11+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Thu Jun 04, 2020 12:50 am at Thu Jun 04, 2020 12:50 am
>
> 
CriticalError wrote: ↑Thu Jun 04, 2020 12:42 am


Tried "Apply Selected Path"?well after repair client it open now and sucess, really is a nice tool, just the problem is not interface in english but anyway so good, animations loaded automatically, I trying figure out how export it to FBX, many thanks for all support, thanks mate.
## Post #75
- Username: moiianxiv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 09, 2020 2:31 pm
- Post datetime: 2020-12-09T06:49:18+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

Excuse me, is there any way to modify UI texture by using those tools?
I want to hide particular UI buttons since they are messy.
## Post #76
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-12-10T03:00:59+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

Thank you everyone for the information. I was interested in the animation editor, so I tried it.

First of all, the quality of the anime in this game is not very good. The model is beautiful. As the title "HD Remake" suggests, it may be that the was released with a replace new model and texture only. The quality of the anime is clearly older generation.

After downloading the client, we can use the editor, but can't use any model other than the preset unless you set the system locale to Chinese. If change the system locale to Chinese and restart the OS, will be able to access all the files.
We can also get the animation by playing the animation in the character preview window and outputting it as FBX.

However, this tool requires user registration and authentication is required to start it. Please note that if development feels a problem,
its functionality may be stopped.

*EDIT
As an aside, the game client contains some Unity3D files.
If I remember correctly, these are mobile model files. Contains only a few assets.
## Post #77
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-12-13T19:19:49+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Thu Jun 04, 2020 7:41 am at Thu Jun 04, 2020 7:41 am
>
> 
well after repair client it open now and sucess, really is a nice tool, just the problem is not interface in english but anyway so good, animations loaded automatically, I trying figure out how export it to FBX, many thanks for all support, thanks mate.

How did you manage to repaired client? I'm facing the same problem when I select game directory and apply path.
## Post #78
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-12-13T22:29:23+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Drawing ↑Mon Dec 14, 2020 3:19 am at Mon Dec 14, 2020 3:19 am
>
> 
CriticalError wrote: ↑Thu Jun 04, 2020 7:41 am
well after repair client it open now and sucess, really is a nice tool, just the problem is not interface in english but anyway so good, animations loaded automatically, I trying figure out how export it to FBX, many thanks for all support, thanks mate.


How did you manage to repaired client? I'm facing the same problem when I select game directory and apply path.Well I use my cellphone to translate buttons in chinnese to EN but  I don't remember which one it's, and is necessary set CN language in windows and unicode as far remember, if not set no work.
## Post #79
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-12-15T18:44:28+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from CriticalError ↑Mon Dec 14, 2020 6:29 am at Mon Dec 14, 2020 6:29 am
>
> 
Well I use my cellphone to translate buttons in chinnese to EN but  I don't remember which one it's, and is necessary set CN language in windows and unicode as far remember, if not set no work.

Thanks, in the end I succeded in repair the client ( although dunno know how ) and launched the program that works. 
I change language in English but the menu in the movie editor is not completely translated, I found a little bit difficult to use, understand options and find where NPC and creatures are located, anyway practises will help understand it.

For those who dunno how to register, just use a public chinese phone number, there are plenty on internet, however some of them have been already used ( good luck   )
## Post #80
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-12-16T07:32:29+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

Hey,


Are not all graphics cards supported? I always get the following error when starting:
## Post #81
- Username: ItsLucas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 21, 2021 12:31 pm
- Post datetime: 2021-01-21T06:12:10+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Tue Oct 02, 2018 7:14 pm at Tue Oct 02, 2018 7:14 pm
>
> 
Here's a x86 release of the tool:
JX3HDUnpacker.7z
Place them in the dir of the dat/idx files and double-click the .bat to run the program in batch command.
It'll log all text info into a new corresponding file(.txt or .json) within 8 megabytes for convenience of reading, unless current text chunk has already exceed that size.

Note: Files end with ".TBD" means their extensions are to be determined.
May I request a linux version of the tool?
Some friends and me arr performing personal analysis on the game's base mechanics and scripts. We mainly do that on a linux server.
Many thanks
## Post #82
- Username: whc2001
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 24, 2021 1:23 pm
- Post datetime: 2021-01-24T05:41:05+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from KingJuls ↑Wed Dec 16, 2020 3:32 pm at Wed Dec 16, 2020 3:32 pm
>
> 
Hey,


Are not all graphics cards supported? I always get the following error when starting:

Have you ticked the check box saying "RTX" when launching? If so uncheck it and try again.
## Post #83
- Username: crism
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 20, 2021 11:21 am
- Post datetime: 2021-03-23T02:43:44+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Thu May 21, 2020 11:53 pm at Thu May 21, 2020 11:53 pm
>
> 
CriticalError wrote: ↑Wed May 20, 2020 2:11 pmthe problem is Trunk.dir can't see file names, look like is crypted or something

when open with notepad++ ofc I see this, you sure say so if encrypted why you see that, wel no idea really

I wouldn't consider binary plaintext as "encrypted". Getting only the names won't help you coz you'll need other info like package IDs, offsets and sizes etc. to extract corresponding assets. I wrote a resource unpacker over a year ago after the research on the database's format was finished, but never had the desire to release it. No idea whether the format has been changed or not ever since, or if the tool still work.Excuse me, can I get the latest version of the tool now? I need him to extract some information
## Post #84
- Username: moiianxiv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 09, 2020 2:31 pm
- Post datetime: 2021-07-23T03:41:08+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

This BMS script doesn't work now. Can anyone help?



5.PNG (27.18 KiB) Viewed 105 times
## Post #85
- Username: lanup
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 07, 2021 7:02 pm
- Post datetime: 2021-09-08T11:49:55+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Mon Jun 01, 2020 9:47 pm at Mon Jun 01, 2020 9:47 pm
>
> 
CriticalError wrote: ↑Thu May 21, 2020 11:55 pmso let me know if possible test it.

Well, they updated the database format and replaced the asset names with some 10-byte sequences so the old tool no longer works. There're about 58 megabytes of extra data at the end of the dir file which might be a compressed string buffer. Not sure if it's encrypted or not.
CriticalError wrote: ↑Fri May 29, 2020 9:13 pm
I get source code client + Tools for Visual Studio 2008

Tools for what?
Thank you for your great job！Can you tell me the idea of analysis file Trunk.dir？I just want to get the correct path of the extracted resources.I'm in a total mess.Thanks a lot.
## Post #86
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-09-09T12:01:51+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from lanup ↑Wed Sep 08, 2021 7:49 pm at Wed Sep 08, 2021 7:49 pm
>
> Can you tell me the idea of analysis file Trunk.dir？I just want to get the correct path of the extracted resources.
I don't think it'd be that easy as it was before, since they'd replaced the asset names with hashes.
## Post #87
- Username: lanup
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 07, 2021 7:02 pm
- Post datetime: 2021-09-10T10:24:36+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Thu Sep 09, 2021 8:01 pm at Thu Sep 09, 2021 8:01 pm
>
> 
lanup wrote: ↑Wed Sep 08, 2021 7:49 pmCan you tell me the idea of analysis file Trunk.dir？I just want to get the correct path of the extracted resources.

I don't think it'd be that easy as it was before, since they'd replaced the asset names with hashes.

Thank you for your reply!I want to know where to start analyzing the file，even results are just hashes.I just need a tip from you(the file is a txt?or it's compressed by a certain algorithm? )Help me a little plz!
## Post #88
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-09-11T06:22:07+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from lanup ↑Fri Sep 10, 2021 6:24 pm at Fri Sep 10, 2021 6:24 pm
>
> 
I want to know where to start analyzing the file，even results are just hashes.
Well, that's a difficult question. What can I say? It's basically the same process as analyzing any archive formats. You can start from here:
[http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF)
## Post #89
- Username: lanup
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 07, 2021 7:02 pm
- Post datetime: 2021-09-11T08:36:20+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Sat Sep 11, 2021 2:22 pm at Sat Sep 11, 2021 2:22 pm
>
> 
lanup wrote: ↑Fri Sep 10, 2021 6:24 pm
I want to know where to start analyzing the file，even results are just hashes.

Well, that's a difficult question. What can I say? It's basically the same process as analyzing any archive formats. You can start from here:
http://wiki.xentax.com/index.php/DGTEFF

Thank you,I will start learnning it.You are a nice man.
## Post #90
- Username: lanup
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 07, 2021 7:02 pm
- Post datetime: 2021-09-11T08:43:34+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Sat Sep 11, 2021 2:22 pm at Sat Sep 11, 2021 2:22 pm
>
> 
lanup wrote: ↑Fri Sep 10, 2021 6:24 pm
I want to know where to start analyzing the file，even results are just hashes.

Well, that's a difficult question. What can I say? It's basically the same process as analyzing any archive formats. You can start from here:
http://wiki.xentax.com/index.php/DGTEFF
BTW,the last question I swear.You created a wonderful standlone tool to unpack JX3OL,is that the same principle as BMS script you written before?(I want to learn something from your BMS script beacause I can see it's source code.)
## Post #91
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-09-11T15:24:25+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from lanup ↑Sat Sep 11, 2021 4:43 pm at Sat Sep 11, 2021 4:43 pm
>
> is that the same principle as BMS script you written before?
Yep. As far as I remember it was just a port to C of the same logics in that BMS script.
## Post #92
- Username: lanup
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 07, 2021 7:02 pm
- Post datetime: 2021-09-11T23:39:39+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

> Reply from Bigchillghost ↑Sat Sep 11, 2021 11:24 pm at Sat Sep 11, 2021 11:24 pm
>
> 
lanup wrote: ↑Sat Sep 11, 2021 4:43 pmis that the same principle as BMS script you written before?

Yep. As far as I remember it was just a port to C of the same logics in that BMS script.

Thank you!
## Post #93
- Username: xtruong712
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 01, 2021 12:20 am
- Post datetime: 2022-02-17T14:14:25+00:00
- Post Title: Re: JX3 HD Remake 剑网3 (.dat files)

I want unpack Pak file of version VietNam, it is version 9 class. but maybe they was change type pak
This is link pak: [https://drive.google.com/file/d/1mL0_EY ... sp=sharing](https://drive.google.com/file/d/1mL0_EYx47DPB-oXz1ixKONlCJlj4OIFm/view?usp=sharing)
