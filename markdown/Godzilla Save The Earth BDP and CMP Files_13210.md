## Post #1
- Username: mr rocket
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 15, 2015 4:15 am
- Post datetime: 2015-08-18T13:14:28+00:00
- Post Title: Godzilla Save The Earth BDP and CMP Files

Hello! I was wondering if anyone could help me unpack these BDP and CMP files for modding purposes.

Download: [https://mega.nz/#!zcxGgAhC!a4WN5Ogu-_Ow ... Tik8rxizMU](https://mega.nz/#!zcxGgAhC!a4WN5Ogu-_OwJJv60aykLIjFXU8MTnnYQTik8rxizMU)

These files are from the PS2 version of Godzilla Save The Earth.

Any help is greatly appreciated!
## Post #2
- Username: mr rocket
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 15, 2015 4:15 am
- Post datetime: 2015-08-24T19:43:41+00:00
- Post Title: Godzilla Save The Earth BDP and CMP Files

Any help would be appreciated!

I found out that Pipeworks used the same Spigot engine to create a Monopoly game for the PSP, however, it appears to be a different version from Godzilla Save The Earth. Here's the script, just in case it could be of any help in extracting these files: [http://aluigi.altervista.org/papers/bms ... ly_bds.bms](http://aluigi.altervista.org/papers/bms/others/monopoly_bds.bms)

I've been inspecting the files from Godzilla Save The Earth and, keep in mind I suck at scripting/inspecting file formats, I found that the bytes at offset 0x64 always direct to the end of all the files. Yeah, I suck at explaining this stuff, but these pictures should illustrate want I mean:

[http://i.imgur.com/Cq8QDCm.png](http://i.imgur.com/Cq8QDCm.png)
[http://i.imgur.com/U2O6hut.png](http://i.imgur.com/U2O6hut.png)
[http://i.imgur.com/k1TKZ2s.png](http://i.imgur.com/k1TKZ2s.png)
[http://i.imgur.com/L18jCcs.png](http://i.imgur.com/L18jCcs.png)
[http://i.imgur.com/xwVvQUi.png](http://i.imgur.com/xwVvQUi.png)

For example, the bytes "40" and "5a" appear at 0x64, typing them in backwards lead me to the end of the files:

[http://i.imgur.com/LQoGe27.png](http://i.imgur.com/LQoGe27.png)

I *think* this could be useful for file extraction but I'm not at all experienced with BMS scripting so this is just a assumption.

Thanks in advance to anyone who can help me out!
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-08-28T04:09:39+00:00
- Post Title: Godzilla Save The Earth BDP and CMP Files

It doesn't look like we have a lot of Godzilla fans here which is a shame.    I would help you with this but i'm just not good with this stuff.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-28T06:03:05+00:00
- Post Title: Godzilla Save The Earth BDP and CMP Files

Ebirah.cmp contains a mesh: 



Ebirah_cmp.JPG (77.94 KiB) Viewed 152 times


(But the face indices don't seem to fit and I don't have the time to care for them.)

f 1835 2264 1835 
f 2264 1835 2264 
f 1835 2264 1835 
f 2264 1835 2264 
f 1835 2264 1835 
f 2264 1878 4044 
f 1802 4004 1652 
f 4042 1618 3927 
f 1450 3923 1432 
f 3706 1353 3702 
f 1387 3528 1335 
f 3529 1387 3528 
f 1341 3356 1419 
f 3347 1422 3129 
f 1589 3113 1616 
f 2996 1768 3023 
f 1841 2978 1733 
> f 240 1786 92 
f 1943 119 1733 
f 240 1991 236 
f 1943 119 1733 
f 240 1659 73 
f 1554 240 1554 
f 73 1554 240 
f 1454 71 1351 
f 240 1371 56 
f 1351 240 1323 
...

As from the line marked by '>' I thought it might be interleaved indices for position/texture
but seems it's not.
## Post #5
- Username: mr rocket
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 15, 2015 4:15 am
- Post datetime: 2015-08-28T23:40:22+00:00
- Post Title: Godzilla Save The Earth BDP and CMP Files

So the CMP files are just mesh files? I appreciate your help, but I'm honestly not too interested in any of the game models, I'm more so interested in extracting files for editing and then reimporting them.

Maybe I should have mentioned this earlier, but AlphaTwentyThree from Zenhax wrote a QuickBMS script to extract the main archive, a VOL file, which is how I obtained these CMP/BDP files. Maybe his script could be useful for extracting these files?

```
#
# written by AlphaTwentyThree of Zenhax
#
# script for QuickBMS http://quickbms.aluigi.org

idstring "PVOL"
get UNK long
get FILES long
get DATASTART long
xmath NAMEOFF "(0xc * FILES) + (4 * FILES) + 20"
for i = 0 < FILES 
   get OFFSET long
   get SIZE long
   get FID long
   savepos MYOFF
   goto NAMEOFF
   get NAME string
   savepos NAMEOFF
   goto MYOFF
   log NAME OFFSET SIZE
next i
```
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-29T09:25:24+00:00
- Post Title: Godzilla Save The Earth BDP and CMP Files

> Reply from ThatGodzillaFan
>
> So the CMP files are just mesh files?I'd say so. With some scrambled texture data contained.
## Post #7
- Username: mr rocket
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 15, 2015 4:15 am
- Post datetime: 2020-11-29T19:54:06+00:00
- Post Title: Godzilla Save The Earth BDP and CMP Files

Hello, all. Thanks to shakotay2, I've been able to understand much of how the game's meshes work and have been able to replicate his results with another mesh from the game:



However, I've also found myself stuck on figuring out how to get the face indices to fit. I believe that the mesh may be using a triangle strip format. This is backed up by [this post by FurryFan](https://forum.xentax.com/viewtopic.php?p=35137#p35137) (Godzilla Unleashed is the game's sequel which runs on the same engine since it's a lazy rehash compared to the Wii version) as well as the results given by Hex2obj's fake face indices feature when tristrips are enabled vs when they are not:



My current settings are as shown below:



I took the vertex count from one of the files contained in Godzilla2k.cmp. This seems to be correct since the vertex count given for the mesh Ebirah seen three posts above is "5094" - the same vertex count shakotay2 found. I'm not too sure about the indices count. It's probably wrong, but I'll explain how I came to that number. What I've done so far is select all of what I believe are indices (1D8AC0-1DC59F), divided the length of this (3AE0) by two, and then converted it to decimal format.

Here are the Godzilla2k files if anyone would like to take a look at them:

[http://www.mediafire.com/file/lob6fwjxp ... k.zip/file](http://www.mediafire.com/file/lob6fwjxpq58jke/Godzilla2k.zip/file)

I've included what I believe is the entire mesh file as well as some other files I've extracted with my WIP QuickBMS script for Pipeworks Bundles  as found in the Godzilla trilogy (currently extracts most data besides the actual graphic resources themselves). These files contain some information for the mesh (I've only identified file size and vertex count thus far). I also included a BMS script that I obtained from the PS23DFormat website before it went down. This script can extract Anguirus's mesh seemingly without issue from the PS2 version of Godzilla Unleashed as well as Rampage Total Destruction (which the script is intended for) which runs on the same engine. It's difficult to make sense of this script however as it operates on the large .VOL archive containing all of the game's data, but it could be worth looking at. Finally, I included what is likely the entire mesh file separated from the rest of Godzilla2k's bundle, although I've been operating on the bundle itself, so the offsets in my screenshot refer to locations in Godzilla2k.cmp as a whole.

My goal with this is to hopefully be able to import/modify the meshes in the game once the format is understood. While that's still a long way off, I figured this would be a good place to start at least.
