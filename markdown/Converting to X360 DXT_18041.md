## Post #1
- Username: mzkoops56
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 06, 2017 6:44 am
- Post datetime: 2018-04-29T11:42:24+00:00
- Post Title: Converting to X360 DXT

I've been trying to convert some DDS textures into the x360 tiled version. If there is a script that can do that based on the file format I've uploaded, that would be great.

Format I want to convert to:
[https://drive.google.com/open?id=1vcqaw ... zGNIee4aoD](https://drive.google.com/open?id=1vcqaw4YOHYfBZg2bNVWNawzGNIee4aoD)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-30T08:24:35+00:00
- Post Title: Converting to X360 DXT

what is the game name? i need to name script   

this Noesis python script will open your ckd samples  


 tex_JustDance2018_X360_ckd.zip
(728 Bytes) Downloaded 35 times


supports dxt1 and dxt5

then you can export the images to usable format and modify as you wish.
then save a modified image as for example test.tga
now you need to find a program named bundler.exe located in the X360 SDK,
i can not link it here because it will make trouble, just google. 
next create a text file and name it test.rdf and paste this inside that file

```
<RDF Version="XPR2">
<Texture
   Name   = "StrName"
   Source = "test.tga"
   Format = "D3DFMT_DXT5"
   Width  = "256"
   Height = "256"
   Levels = "1"
/>
</RDF>
```

set your source file name, format, width, height and levels (mip map levels),
for "Levels" if you set it to 0 bundler.exe will create all mip map levels by default,
if you set it to 1 it will only have top level mip, 
any other number will set custom number of mips i think.

now you should have a folder with your modified image, the rdf file and bundler.exe:
test.tga
test.rdf
bundler.exe

next just drag and drop the test.rdf file on bundler.exe and it will create test.xpr
open test.xpr in a Hex editor and go to 0x80c and copy the data from there to the end.
then open the corresponding original ckd file (make a backup first) in hex editor 
and go to 0x60 and paste that data overwriting the original and you should be good
as long as you didn't change the width, height and format to something different than original.
## Post #3
- Username: mzkoops56
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 06, 2017 6:44 am
- Post datetime: 2018-04-30T10:03:06+00:00
- Post Title: Converting to X360 DXT

Thank you so much! I've had the X360 SDK for awhile, I just never knew which program to use. The game name is Just Dance 2018
