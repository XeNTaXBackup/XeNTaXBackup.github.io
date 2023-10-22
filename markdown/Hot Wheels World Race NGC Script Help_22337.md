## Post #1
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-01T04:04:56+00:00
- Post Title: Hot Wheels World Race NGC Script Help

Hello, I hope you are well.
I spent time playing with this script, but I can't seem to get it to work. So the message that appears tells me that the buffer is not correct, but I don't know what to do.

Here is how the model is loaded with Hex2obj:



aeroflash_med.png (51.81 KiB) Viewed 215 times
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-01T04:06:54+00:00
- Post Title: Hot Wheels World Race NGC Script Help

Here is the script plus some sample files:


 Script + rom .zip
(211.47 KiB) Downloaded 18 times



Thank you for your help!
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-07-01T08:29:07+00:00
- Post Title: Hot Wheels World Race NGC Script Help

Hello,
do a correction of one line only, DWORD FIs here, means 4 instead of 2 bytes:
FBuff = bs.readBytes(FCont*3*4)

btw: "FCont"? In english you'd better choose "FCount" or "FCnt" or "FaceCnt", just as a thought.
## Post #4
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-01T23:00:27+00:00
- Post Title: Hot Wheels World Race NGC Script Help

Thank you very much   , now the script loads the templates, I still need to edit it to load the second mesh, the way I did until it loads the second mesh, but stops loading files that have only one mesh.

> Reply from shakotay2 ↑Wed Jul 01, 2020 4:29 pm at Wed Jul 01, 2020 4:29 pm
>
> 
btw: "FCont"? In english you'd better choose "FCount" or "FCnt" or "FaceCnt", just as a thought.
Thanks for the tip, I will make changes to the script and then post it here.
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-07-04T10:52:57+00:00
- Post Title: Hot Wheels World Race NGC Script Help

> Reply from reh ↑Wed Jul 01, 2020 12:06 pm at Wed Jul 01, 2020 12:06 pm
>
> 
Here is the script plus some sample files:
Script + rom .zip

Can you tell me how did you extract the .bah/bad archive files?

Here I attached the converted file in Wavefront .obj format.
[Hot.Wheels.World.Race_rom_to_obj.zip](https://xentaxbackup.github.io/file/18422_Hot.Wheels.World.Race_rom_to_obj.zip)
## Post #6
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-05T04:58:44+00:00
- Post Title: Hot Wheels World Race NGC Script Help

> Reply from Karpati ↑Sat Jul 04, 2020 6:52 pm at Sat Jul 04, 2020 6:52 pm
>
> 
Can you tell me how did you extract the .bah/bad archive files?
I extracted the files with the script found [here](https://zenhax.com/viewtopic.php?t=215).

Here is the script for the templates, so far with the files I tested it worked fine.


 fmt_HotWheelsWorldRace_rom_shm_NGC.zip
(932 Bytes) Downloaded 14 times
## Post #7
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-05T05:31:46+00:00
- Post Title: Hot Wheels World Race NGC Script Help

Now, my question is how to get the textures? In the link where I found the scripts to extract, they say they are dds files, but the best thing I can do when trying to extract with Texturefinder was the following:
[textures.jpg](https://xentaxbackup.github.io/file/18428_textures.jpg)
## Post #8
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-05T05:53:29+00:00
- Post Title: Hot Wheels World Race NGC Script Help

If anyone wants to help   , I'll post some samples [here](http://www.mediafire.com/file/c9jzaezzxrj9ei1/Examples_Textures.rar/file).
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-07-11T18:22:01+00:00
- Post Title: Hot Wheels World Race NGC Script Help

I have finished my Hot Wheels: World Race .rom loader module and I have released the following program as web updates:

- 3D Object Converter v7.034 (Windows)

How to get the 3D Object Converter:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v7.034.
## Post #10
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-16T04:40:21+00:00
- Post Title: Hot Wheels World Race NGC Script Help

I was trying to add the material name, with this code:

```
MaterialNames = (bs.readBytes(16).decode("ASCII").rstrip("....ÿÿÿÿ"))
```


My intention was to ignore the "....ÿÿÿÿ" that appeared after the name, but I am getting this error:
UnicodeDecodeError: 'ascii' codec can't decode byte 0xff in position 8: ordinal not in range(128)

How should I ignore these characters?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-07-16T07:40:10+00:00
- Post Title: Hot Wheels World Race NGC Script Help

Without showing the hex bytes you're reading no one can tell.
I assume the problem might be the "..." - rstrip() doesn't use them as wildcards, does it?
## Post #12
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-16T16:40:42+00:00
- Post Title: Hot Wheels World Race NGC Script Help

> Reply from shakotay2 ↑Thu Jul 16, 2020 3:40 pm at Thu Jul 16, 2020 3:40 pm
>
> 
Without showing the hex bytes you're reading no one can tell.
I assume the problem might be the "..." - rstrip() doesn't use them as wildcards, does it?
Would these be:



somethin_med.png (11.57 KiB) Viewed 108 times
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-07-16T18:37:36+00:00
- Post Title: Hot Wheels World Race NGC Script Help

well, you simply need a function which reads zero-terminated strings, don't you?
Seems you need to create it for yourself - found a base in fmt_Torchlight_mesh.py,
modified:

```
	name = b''
	b = bs.readBytes(1)
	while b != b'\x00':
		name+=b
		b = bs.readBytes(1)
	return noeStrFromBytes(name)
```


use it like so before your for i in range(1): loop

```
	print(ReadStringZeroT(bs))
```


(btw: for some unknown reason while b != 0: doesn't work, why?)
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-07-16T23:35:45+00:00
- Post Title: Hot Wheels World Race NGC Script Help

```
MaterialNames = bs.readString()
```

should suffice.
## Post #15
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-18T04:40:41+00:00
- Post Title: Hot Wheels World Race NGC Script Help

Thank you very much, I will test these tips    

Edit: The first code that Shakotay posted until it works, but if the model has more than one material, how would I do it?
I tried to put it in a loop, but it didn't work.

How would I use this code?

> Reply from Acewell ↑Fri Jul 17, 2020 7:35 am at Fri Jul 17, 2020 7:35 am
>
> 
Code: Select allMaterialNames = bs.readString()
