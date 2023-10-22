## Post #1
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2022-09-11T10:27:25+00:00
- Post Title: iRacing .dat

Hello everyone,
I'm interesed in model from iRacing, format is .dat file, this script didn't work [http://aluigi.altervista.org/bms/iracing_alpha.bms](http://aluigi.altervista.org/bms/iracing_alpha.bms)
Anybody know, how to import models with all LODs and textures? 
Sample: [https://www.mediafire.com/file/jfxyv8tn ... r.rar/file](https://www.mediafire.com/file/jfxyv8tn8zqq7e3/porschemissionr.rar/file)
## Post #2
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2022-09-11T19:57:12+00:00
- Post Title: iRacing .dat

well im not 100% if that is already how it should be unpacked, it looks like it is indeed raw information, but needs to be separated in the files that are indexed in the header
## Post #3
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2022-09-12T09:13:25+00:00
- Post Title: iRacing .dat

well, decided to have a look more in depth into the header file and not sure exactly what are the positions marked on each file but i guess if we check all the sizes and compare to the full container size or the blocks of information there will be some way to figure out what is the offset/size for splitting the different files, the .stp im not sure if those are step files for 3d models directly or just some special format they use... at least the sounds are in RIFF WAV(.wav) files from what i saw
[porschemissionr_low.JPG](https://xentaxbackup.github.io/file/22807_porschemissionr_low.JPG)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-12T09:27:52+00:00
- Post Title: iRacing .dat

> Reply from zimex25 ↑Sun Sep 11, 2022 6:27 pm at Sun Sep 11, 2022 6:27 pm
>
> 
Hello everyone,
...
Anybody know, how to import models with all LODs and textures?Hello, I used offzip on the porsche-rar, got a few .dat files sized around 100 kB. But all I found in them were AnimKeys, afaics.
## Post #5
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2022-09-12T10:09:04+00:00
- Post Title: iRacing .dat

on closer inspection, the header does contain information regarding the position and also the size of each item, size for the string of the name and probably a compressed size, the sizes stop matching after the second one more likely cause the main data is compressed, if the alpha used deflate it doesnt seem to work now at least from what i tried with the places cut, so maybe if someone can get the correct decomp method for the main block the 3d model/textures could be converted...
## Post #6
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2022-09-12T15:24:18+00:00
- Post Title: iRacing .dat

> Reply from Machinedramon ↑Mon Sep 12, 2022 5:13 pm at Mon Sep 12, 2022 5:13 pm
>
> 
well, decided to have a look more in depth into the header file and not sure exactly what are the positions marked on each file but i guess if we check all the sizes and compare to the full container size or the blocks of information there will be some way to figure out what is the offset/size for splitting the different files, the .stp im not sure if those are step files for 3d models directly or just some special format they use... at least the sounds are in RIFF WAV(.wav) files from what i saw

lol that's look like normal files like .png and .bl. DAT of iRacing looking like compressed files aka rar, zip, 7z etc.
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-09-12T20:59:12+00:00
- Post Title: iRacing .dat

has 3 compress type (5-not compressed, 2181-deflate, 3333-unk compress), scanned with qbms.
Specification .dat:

```
uint numFile
uint sizeInfoBlock

for numFile:
	ushort typeCompress
	uint unzipSize
	uint zipSize
	uint offset
	ubyte lenName
	string Name >> (lenName)

*(if compressed, indent first 8 bytes in file data)
**(its 8 bytes [uint unzip size, uint zip size] not always correct)

```


(decompress Deflate, with qbms) "wheel_options.png":


i made plugin for Noesis, unpacks without decompress and sorts into folders depending on the type of compression.
[fmt_RACING_DAT.zip](https://xentaxbackup.github.io/file/22814_fmt_RACING_DAT.zip)
## Post #8
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2022-09-15T18:09:06+00:00
- Post Title: iRacing .dat

Okay we get 3do files (models) and textures in tga/mip. 3DSimEd crashing when I tried open files, Photoshop and PVRTexTool didn't open textures. 
Models samples: [https://mega.nz/file/KpNmlKaJ#HvkaSYghG ... w2wiKYNmSU](https://mega.nz/file/KpNmlKaJ#HvkaSYghGGr9fXCEk2QKeXMDhjySciY09w2wiKYNmSU)
Texture samples: [https://mega.nz/file/bwUiXJiD#NPz3jjYBi ... 1dxWTeZIZs](https://mega.nz/file/bwUiXJiD#NPz3jjYBithWcUZYDZMY-_61U31P46wFv1dxWTeZIZs)
[https://mega.nz/file/OgtwlIbA#XxYGNNUW2 ... jX-VxGFFQk](https://mega.nz/file/OgtwlIbA#XxYGNNUW2okG8SGWjRrbgCmZly8cgdRJzjX-VxGFFQk)
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-09-15T18:52:48+00:00
- Post Title: iRacing .dat

> Reply from zimex25 ↑Fri Sep 16, 2022 2:09 am at Fri Sep 16, 2022 2:09 am
>
> 
Okay we get 3do files (models) and textures in tga/mip. 3DSimEd crashing when I tried open files, Photoshop and PVRTexTool didn't open textures.
what do you get... i think you should re-read the post.
files are compressed...
update for my previous post: image is broken into chunks:

```
	uint unzipSize
	uint zipSize
	bytes zipData

```

car_pattern_024.tga decompress and resize (2048x2048 >> 256x256)



car_pattern_024_DECOMP.tga.jpg (85.32 KiB) Viewed 204 times
## Post #10
- Username: iddan787
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 21, 2021 2:25 am
- Post datetime: 2022-09-29T19:15:21+00:00
- Post Title: iRacing .dat

Как вы импортируете 3д модели?
## Post #11
- Username: Vojtech
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 03, 2022 11:56 pm
- Post datetime: 2023-09-17T08:46:31+00:00
- Post Title: iRacing .dat

So, any updates on the extraction? or how to rip the models from the game?
