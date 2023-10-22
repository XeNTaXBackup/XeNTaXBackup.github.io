## Post #1
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-01T17:42:28+00:00
- Post Title: how do you extract feamber file formats

i really want to extract them
.zbp = texture
.zc = alternative model file
.lv = map model file
## Post #2
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-01T18:09:36+00:00
- Post Title: how do you extract feamber file formats

while i was able to export the .zbp to .bpg then .png im still trying to extract the .lv files and .zc files from the first space racing
## Post #3
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-02T07:19:18+00:00
- Post Title: how do you extract feamber file formats

they need to update the noesis plugin so it could be usable in every feamber game because some games basically don't let you extract those files for example the last ship in space racing 2 and crazy racer 3d models
## Post #4
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-23T07:04:33+00:00
- Post Title: how do you extract feamber file formats

the .lv files have the .zdo files in them, please bumpity bumpy bump
## Post #5
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-27T17:19:43+00:00
- Post Title: how do you extract feamber file formats

i mean insides of them, how to view the contents of .lv
## Post #6
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-28T06:52:19+00:00
- Post Title: how do you extract feamber file formats

i realised the .zc files are the hitboxes for the ships
## Post #7
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-28T07:50:12+00:00
- Post Title: how do you extract feamber file formats

bump please
## Post #8
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-28T07:52:47+00:00
- Post Title: how do you extract feamber file formats

in addition update the noesis script so it doesn't spew this error
here are files i tried: [https://www.mediafire.com/file/07r2tluo ... 2.zdo/file](https://www.mediafire.com/file/07r2tluoim5cjqr/bmw_m2.zdo/file) 
[https://www.mediafire.com/file/3207bd30 ... 4.zdo/file](https://www.mediafire.com/file/3207bd301vwpten/ship14.zdo/file)
[Zrzut ekranu 2021-07-28 095158.png](https://xentaxbackup.github.io/file/20526_Zrzut ekranu 2021-07-28 095158.png)
## Post #9
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-28T09:02:38+00:00
- Post Title: how do you extract feamber file formats

actually in the obj folder for the maps you can find the parts of the map, can someone update the noesis plugin so it's supportable with level objects please?
## Post #10
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-18T08:25:31+00:00
- Post Title: how do you extract feamber file formats

bump
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-18T15:12:42+00:00
- Post Title: how do you extract feamber file formats

> Reply from fajNYgosciu1234 ↑Wed Jul 28, 2021 3:52 pm at Wed Jul 28, 2021 3:52 pm
>
> 
in addition update the noesis script so it doesn't spew this error
here are files i tried: https://www.mediafire.com/file/07r2tluo ... 2.zdo/file 
https://www.mediafire.com/file/3207bd30 ... 4.zdo/fileDid you ask the author Tuliopilloto from vg-resource.com for an update? (should be an easy fix: there's only larger blocks with zeroes at the beginning of the bmw_m2.zdo file.)

(As you may know I'm a fan of hex2obj so find my solution here, click on up arrow:)

> Reply from shakotay2 ↑Wed Aug 18, 2021 11:11 pm at Wed Aug 18, 2021 11:11 pm
>
> 
(And sorry, no time to patch the Noesis script.)
## Post #12
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-18T15:56:20+00:00
- Post Title: how do you extract feamber file formats

he isn't active yet
## Post #13
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-29T09:01:41+00:00
- Post Title: how do you extract feamber file formats

and yet i messaged him, he is no longer active
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-29T13:17:57+00:00
- Post Title: how do you extract feamber file formats

No reason to give up, is it?  

Here's how to patch Tuliopilloto's Noesis script for (and only for) the bmw_m2 zdo (for one sub mesh only).
This is an excerpt from his script I will mainly deal with:

```
	NumMesh = bs.readUInt()
	Offset = bs.readUInt()
	for i in range(NumMesh):
		bs.seek(Offset, NOESEEK_ABS)
		Size = bs.readUInt()
		bs.seek(0x8, NOESEEK_REL)
		VCount = bs.readUInt()
		SizeS = bs.readUInt()
		NCount = bs.readUInt()
		SizeN = bs.readUInt()
		NumUV = bs.readUInt()
		UVCount = bs.readUInt()
		SizeUV = bs.readUInt()
		bs.seek(0x14, NOESEEK_REL)
		FCount = bs.readUInt()
		SizeF = bs.readUInt()
		FVFsize = 12
		VBuff = bs.readBytes(VCount * FVFsize)
```


Well, with some basic understanding in python scripting it's no rocket science to adapt the script for the bmw_m2.zdo.
Starting with the params from here (click the up arrow):

> Reply from shakotay2 ↑Wed Aug 18, 2021 11:11 pm at Wed Aug 18, 2021 11:11 pm
>
> 

vertex count: 6550 = 0x1996
start of vertex block: 0x334DC

See the picture below: 56 bytes back brings you to 0x334A4
doing the "seek 8" reverse: -8 -> 0x3349c
skip "Size" backwards: -4 -> 0x33498

That's the absolute offset value the scripts needs to approach to.
Somewhere in the .zdo file there should be a fitting relative offset.

Since I have no interest to search for it I'd patch the script like so:

```
	#NumMesh = bs.readUInt()
	#Offset = bs.readUInt()
	NumMesh = 1
	Offset = 0x33498
	for i in range(NumMesh):
```


2 other changes (- 0x40):

```
		bs.seek(Offset+SizeUV-0x40, NOESEEK_ABS)
```

and

```
		FBuff = bs.readBytes(FCount * 2)
```

I have no idea where this -0x40 (size correction) comes from and no time/interest to care for.

You may add some debug lines to the script such like:

```
		print("uv addr: ",hex(addr))
```

and compare their output to the params from hex2obj .
Then you can calculate the size corrections for yourself.

Good luck!
.



bmw_m2-zdo-hex.png (67.93 KiB) Viewed 57 times
## Post #15
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-09-04T17:26:53+00:00
- Post Title: how do you extract feamber file formats

I have updated the .zdo loader module in the following programs:

- 3D Object Converter v8.011	(Windows)
- i3DConverter v4.101		(macOS)
- i3DConverter v2.101		(Linux)

How to get the 3D Object Converter v8.011:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v8.011.

How to get the i3DConverter macOS v4.101:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v4.101.

How to get the i3DConverter Linux v2.101:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v2.101.
