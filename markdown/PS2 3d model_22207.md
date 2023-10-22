## Post #1
- Username: Num Sei
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 02, 2020 5:57 am
- Post datetime: 2020-05-26T23:03:49+00:00
- Post Title: PS2 3d model

Hello, this time, my doubts are about ps2 3d models. I extracted files from a ps2 game, and found 3d maps (How do I know they were 3d models? - They were in a file where related things were found and most of them weren't  2d images, except the textures, which really are from the map, which made me absolutely sure that the file was a 3d model), but I couldn't find any way to extract it.  I tried to extract in game with ninjaripper, but I couldn't.

The file:

[https://www.mediafire.com/file/9d7iuhg4 ... a.cmp/file](https://www.mediafire.com/file/9d7iuhg416spg84/0000000a.cmp/file)

One thing I realized:

In the offset "11CA00" you can see the names of the textures, after I think there are your data or something like that.

Sorry for the english, i'm using google translate.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-27T00:16:12+00:00
- Post Title: PS2 3d model

Using hex2obj (view link in my sig):
.



0000000a_1-cmp.png (9.23 KiB) Viewed 361 times
## Post #3
- Username: Num Sei
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 02, 2020 5:57 am
- Post datetime: 2020-05-27T00:30:36+00:00
- Post Title: PS2 3d model

Thanks, but I had already tried use hex2obj, before asking the question, it really is very difficult to use.  Could you say the offset you used?  I think this is very distorted.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-27T00:50:01+00:00
- Post Title: PS2 3d model

H2O file is

0x0 500
Vb1
16 99
0x1610 21974
021000
0x0 255

Copy the 6 above lines into a .txt file and rename it to 0000000a_1.H2O. Load mesh and H2O files into hex2obj.
Toggle 'noPtc' button to 'PtCld' (point cloud).

Removing doubles (not implemented) gives less "distortion" but using auto created face indices doesn't look nice:
.



0000000a_1-cmp.jpg (161.16 KiB) Viewed 354 times



> Reply from Num Sei ↑Wed May 27, 2020 8:30 am at Wed May 27, 2020 8:30 am
>
> 
Thanks, but I had already tried use hex2obj, before asking the question, it really is very difficult to use.It's a helper tool - it was nether intended to be a "one click" solution.  And no, I don't think that it's "difficult to use".  It requires some basic understanding of 3D formats, though.
## Post #5
- Username: Num Sei
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 02, 2020 5:57 am
- Post datetime: 2020-05-27T00:53:12+00:00
- Post Title: PS2 3d model

Okay, thanks, I'll see what I can do.
## Post #6
- Username: Num Sei
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 02, 2020 5:57 am
- Post datetime: 2020-05-27T01:29:00+00:00
- Post Title: PS2 3d model

Okay, I did everything you said.  There were some dll's errors, but I managed to download them and everything was fine.  What appeared to me was like the first screenshort you sent, but I didn't understand the rest of what you said. But the textures?  Is there any way to get them?
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-27T06:32:08+00:00
- Post Title: PS2 3d model

> Reply from shakotay2 ↑Wed May 27, 2020 8:50 am at Wed May 27, 2020 8:50 am
>
> 
Removing doubles (not implemented) gives less "distortion" but using auto created face indices doesn't look nice
The vertices block is chopped into thousands of small pieces and there seems to be other data than positions.



MDL.jpg (164.46 KiB) Viewed 326 times



> Reply from Num Sei ↑Wed May 27, 2020 7:03 am at Wed May 27, 2020 7:03 am
>
> 
I extracted files from a ps2 game
With what?

> Reply from Num Sei ↑Wed May 27, 2020 7:03 am at Wed May 27, 2020 7:03 am
>
> 
but I couldn't find any way to extract it.
You may use this BMS script to chop the cmp file more delicately:

```
get folderStr basename
set idx long 0
do
	savepos Offset
	getdstring Ext 4
	get Size long
	goto 8 0 SEEK_CUR
	if Ext != "CMTX"
		math Offset + 0x10
		math Size - 0x10
		string Name p "%s/%d.%s" folderStr idx Ext
		log Name Offset Size
		goto Size 0 SEEK_CUR
	else
		set EndPos long Offset
		math EndPos + Size
		savepos RelOffset
		idstring "TARC"
		get Skip long
		get TexNum long
		get HeaderSize long
		for i = 0 < TexNum
			getdstring TexName 0x10
			goto 0x10 0 SEEK_CUR
			get Offset long
			get Size long
			goto 8 0 SEEK_CUR
			math Offset + RelOffset
			string Name p "%s/%d_tex/%s.CEMP" folderStr idx TexName
			log Name Offset Size
		next i
		goto EndPos
	endif
	math idx + 1
	savepos CurPos
while CurPos < EndOfFile

```


> Reply from Num Sei ↑Wed May 27, 2020 9:29 am at Wed May 27, 2020 9:29 am
>
> 
But the textures?  Is there any way to get them?
The textures are in the CEMP/P2IG container and here's the data of 6.CEMP unpacked by the above script:
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-05-27T10:36:40+00:00
- Post Title: PS2 3d model

here is Noesis python script to open textures from cmp file directly or extracted "CEMP" files also.   
*script updated May 28, 2020*


 tex_NamcoxCapcom_PS2_cmp_cemp.zip
(1.2 KiB) Downloaded 34 times
## Post #9
- Username: Num Sei
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 02, 2020 5:57 am
- Post datetime: 2020-05-27T17:17:53+00:00
- Post Title: PS2 3d model

Thank you all for the help.  I'll explain everything from the beginning. 

The game is Namco X Capcom from PS2, when extracting the ISO there are many FAC and FAH files, there is a file called map.fac accompanied by a map.fah.  I extracted it with a QuickBMS script from a game called Sunday Magazine (which probably has the same structure as Namco X Capcom, I never saw that game, I just know that I can extract my files successfully).  After extracting, there are far and cmp files, the important ones are the cmp, the far are just character sprites.

Here are some links that helped me achieve everything.

[https://zenhax.com/viewtopic.php?t=12732](https://zenhax.com/viewtopic.php?t=12732)

[https://dwn009.fandom.com/wiki/Namco_%C ... pcom/Files](https://dwn009.fandom.com/wiki/Namco_%C3%97_Capcom/Files) 

I will now test the scripts.
## Post #10
- Username: Num Sei
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 02, 2020 5:57 am
- Post datetime: 2020-05-27T20:46:55+00:00
- Post Title: PS2 3d model

Well, the textures are ok. Is there any way to open the 3d model?

And the noesis script don't support some files, here are them:
[https://www.mediafire.com/file/7a0rkcnc ... rk.7z/file](https://www.mediafire.com/file/7a0rkcnchbn732u/Don%27t_work.7z/file)

And I also think that there may be some 3d model here in this file that I found outside of map.fac:
[https://www.mediafire.com/file/czu7grjt ... 4.far/file](https://www.mediafire.com/file/czu7grjtrbn11yx/00000004.far/file)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-28T07:28:25+00:00
- Post Title: PS2 3d model

Some filtering will be required to get rid of superfluous faces:
.



00000004-far-heart.png (31.39 KiB) Viewed 250 times
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-05-28T11:11:04+00:00
- Post Title: PS2 3d model

> Reply from Num Sei ↑Thu May 28, 2020 4:46 am at Thu May 28, 2020 4:46 am
>
> 
And the noesis script don't support some files, here are them:
https://www.mediafire.com/file/7a0rkcnc ... rk.7z/file
fixed, replaced non ascii characters in file names with x, updated script here:
[viewtopic.php?f=16&t=22207&p=163602#p163602](https://forum.xentax.com/viewtopic.php?f=16&t=22207&p=163602#p163602)
## Post #13
- Username: Num Sei
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 02, 2020 5:57 am
- Post datetime: 2020-05-28T16:50:31+00:00
- Post Title: PS2 3d model

Ok, thanks. But how can I open the model?
