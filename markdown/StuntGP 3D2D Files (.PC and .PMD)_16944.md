## Post #1
- Username: Matsilagi
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Aug 31, 2014 12:39 pm
- Post datetime: 2017-08-30T17:14:41+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

So, a friend of mine started working on StuntGP files [https://yethiel.wordpress.com/2017/04/2 ... ructure-1/](https://yethiel.wordpress.com/2017/04/28/stuntgp-an-attempt-to-read-the-file-structure-1/) to try and make the vehicles and tracks work in another RC racing game, and so far he needs to figure out the 3D and 2D file formats of them.

Source files can be found here for experimenting: [http://files.re-volt.io/sgp/game_assets.7z](http://files.re-volt.io/sgp/game_assets.7z)

Any help is welcome.
## Post #2
- Username: Matsilagi
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Aug 31, 2014 12:39 pm
- Post datetime: 2017-11-23T22:15:56+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

Bump.

Its been some time, pretty please?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-11-24T11:57:55+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

> Reply from Matsilagi
>
> Bump.

Its been some time,yeah, it surely has. While it's easy to get some decent point cloud (277 vertices) the face indices are a mess. You have to find out how they have to be used.



car1_PMD.JPG (80.19 KiB) Viewed 309 times


I tried out triangle strips with some lines commented out (#) seeming unlogical to me but they are part of the "system", resulting mesh is still a mess.
f 3 2 1
f 2 6 1
f 1 6 5
f 6 4 5
f 5 4 9
f 4 8 9
f 9 8 7
f 8 12 7
f 7 12 11
f 12 10 11
f 11 10 12
f 10 13 12
#f 12 13 11
f 11 13 14
f 13 9 14
f 14 9 15
f 9 11 15
#f 15 11 13
f 13 11 7
f 11 10 7
f 7 10 15
f 10 9 15
f 15 9 7
f 9 16 7
f 7 16 8
f 16 14 8
f 8 14 10
f 14 17 10
f 10 17 12
f 17 7 12
f 12 7 8
f 7 16 8
f 8 16 10
f 16 7 10
#f 10 7 17
f 17 7 16
f 7 18 16
f 16 18 20
f 18 1 20
f 20 1 19
f 1 3 19
f 19 3 21
f 3 2 21
f 21 2 22
f 2 12 22
f 22 12 1
f 12 2 1
f 1 2 23
f 2 1 23
f 23 1 12
f 1 22 12
f 12 22 24
f 22 27 24
f 24 27 26
f 27 25 26
f 26 25 12
f 25 30 12
f 12 30 29
f 30 28 29
f 29 28 14
f 28 25 14
f 14 25 26
f 25 31 26
f 26 31 33
f 31 32 33
#f 33 32 14
f 14 32 34
f 32 29 34 
# line with 34 29 35 missing?
f 29 34 35
f 35 36 37
f 37 36 40
f 36 39 40
f 40 39 28
#f 39 38 28
f 28 38 43
f 38 42 43
#f 43 42 41
f 41 42 43
f 42 44 43
f 43 44 47
f 44 46 47
#f 47 46 45
f 45 46 49
f 46 48 49
f 49 48 51
f 48 45 51
## Post #4
- Username: Matsilagi
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Aug 31, 2014 12:39 pm
- Post datetime: 2017-11-24T22:41:05+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

> Reply from shakotay2
>
> Matsilagi wrote:Bump.

Its been some time, yeah, it surely has. While it's easy to get some decent point cloud (277 vertices) the face indices are a mess. You have to find out how they have to be used.
car1_PMD.JPG
I tried out triangle strips with some lines commented out (#) seeming unlogical to me but they are part of the "system", resulting mesh is still a mess.
f 3 2 1
f 2 6 1
f 1 6 5
f 6 4 5
f 5 4 9
f 4 8 9
f 9 8 7
f 8 12 7
f 7 12 11
f 12 10 11
f 11 10 12
f 10 13 12
#f 12 13 11
f 11 13 14
f 13 9 14
f 14 9 15
f 9 11 15
#f 15 11 13
f 13 11 7
f 11 10 7
f 7 10 15
f 10 9 15
f 15 9 7
f 9 16 7
f 7 16 8
f 16 14 8
f 8 14 10
f 14 17 10
f 10 17 12
f 17 7 12
f 12 7 8
f 7 16 8
f 8 16 10
f 16 7 10
#f 10 7 17
f 17 7 16
f 7 18 16
f 16 18 20
f 18 1 20
f 20 1 19
f 1 3 19
f 19 3 21
f 3 2 21
f 21 2 22
f 2 12 22
f 22 12 1
f 12 2 1
f 1 2 23
f 2 1 23
f 23 1 12
f 1 22 12
f 12 22 24
f 22 27 24
f 24 27 26
f 27 25 26
f 26 25 12
f 25 30 12
f 12 30 29
f 30 28 29
f 29 28 14
f 28 25 14
f 14 25 26
f 25 31 26
f 26 31 33
f 31 32 33
#f 33 32 14
f 14 32 34
f 32 29 34 
# line with 34 29 35 missing?
f 29 34 35
f 35 36 37
f 37 36 40
f 36 39 40
f 40 39 28
#f 39 38 28
f 28 38 43
f 38 42 43
#f 43 42 41
f 41 42 43
f 42 44 43
f 43 44 47
f 44 46 47
#f 47 46 45
f 45 46 49
f 46 48 49
f 49 48 51
f 48 45 51

Hmm, for the faces i can recognize the car but indeed, the final result is still not optimal.

I'll look a bit inside the format to see if i find info that may help.
## Post #5
- Username: martin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 15, 2018 12:42 am
- Post datetime: 2018-11-18T00:52:57+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

StuntGP yeah I remember those burned hours while playing the game back in the young times. In past I have successful attempt to figure out model format (hmm at least most significant parts of it), it just seems to me that nobody else tried it yet or succeed. 
As I remember while vertex coordinates were easy to figure out, faces definitions not at first shoot. Later on it occurred that vertices and faces lists are a single chunks defined for all surfaces and levels of detail (dfferent bodies). Those lists and some others like polygons definitions list are sliced into smaller ones within ranges specified by surface definition structure. All the referring indexes are valid for these sub lists slices. 

The faces are not defined in common triplets manner, but as polygons with varying amount of vertices used of course. Faces definition sublist, as I keep naming it, is accessed in polygon definition struct. To confuse things, faces list is not pointing vertex directly but further another listed structure (with UVs and some other infos) which is finally points them.

I have dig out some snippets, I can publish current result after a few tweaks. This is work in progress so there are some things left to figure out.


StuntGP meshes preview sgp_meshes.jpeg (161.67 KiB) Viewed 283 times
## Post #6
- Username: martin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 15, 2018 12:42 am
- Post datetime: 2018-11-22T21:43:44+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

Hey folks I hope you like seeing some progress don't you? Basically I'm done with textures as well. About a good stuff I got them all   : 



SGP imported meshes and textures preview. sgp_meshes_textured.jpeg (205.07 KiB) Viewed 269 times


Things looked so simple back in the old days, ehh. Since I don't fell well with compression algorithms and there is some backyard invention RLE derivative being used (I guess due to patents in 00's) I had to play with the assembly code for whole day, but it was worth the effort (took less time than asking orig devs for source code). Moreover there are some small issues like determining texture transparency or rotation matrices - because of problems with conversion from left to right handed coordinate system, but those can be easily fixed when manually editing the models.
After a polishing touches, everything should be available within a days in one package in hope that it will be useful for everyone nailing on this problem.
## Post #7
- Username: martin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 15, 2018 12:42 am
- Post datetime: 2018-11-23T22:12:17+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

As I promised here are the results what I got so far, meantime I switched to other projects. For whatever reason I prefer to share it there rather than between other code repositories. Because forum is limited to 1 attachment per post I had created new reply, hope that's not a problem.  Attached archive contains files worth brief description:
Binary template for sweetscape hex editor for PMD files.
Python 3 crude script for blender >= 2.76 for importing those PMD files. Just paste it into blender's scripting mode, change files paths and run. Script requires textures images, if any of required ones is missing exception is raised. If you don't want any textures this can be skipped by commenting out relevant code parts.
Binary executable in elf format for converting PC files into ordinary bitmap files.
C and x86 ASM sources of the converter, if you want to build it under windows (untested) mingw and  The Netwide Assembler are required.
BASH shell scripts for batch image files conversion.

Utilities for wad extraction, which is file system format used by the game, are available for the long time. Well that’s all, there are just a few short steps left to make things work in other/modern game engines.
Note for gamers: there occurred to be some extras left not used in game, example: horn upgrades in catalogue pages, any player should recognize that it is absent in final product.
If there is anyone seriously interested in compression and is able to read asm then may take a look and post something about it. This is only 400 lines of code with many parts redundant, algorithm is not building any dictionary, only remembers the sub-array to repeat into output when relevant code number occurs.
[sgpToolset.zip](https://xentaxbackup.github.io/file/15226_sgpToolset.zip)
## Post #8
- Username: Halamix2
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 6:45 am
- Post datetime: 2020-02-22T22:53:05+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

I just started to experiment with Stunt GP files without knowing about previous knowledge on the topic, so I made .wad extractor from scratch (although there is one segment that I don't know what it does).
Source code here: [url][https://github.com/Halamix2/stunt_gp_formats](https://github.com/Halamix2/stunt_gp_formats)[/url]

Your code for converting .pc files is working (I'm trying to understand .asm to remake it in something higher level), although if you change line 56 in image.c to "hdrinfo->colorsMask[3] = 0x8000;" then you also get 1bit alpha channel.

After that I might try to understand and describe in text .pmd files

EDIT: It turns out the 4 parts of the dec.asm are identical, after changing loc_420264 to loc_42017A and removing lines 413-439 and 121-387 it still works, so it's now far easier to understand as now it fits in about 150 lines
## Post #9
- Username: Halamix2
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 6:45 am
- Post datetime: 2020-02-26T19:06:01+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

.pc converter is done, it's written in Python and support 1bit alpha channel.
Pros:

 Easy to read

Cons:

only .png output
 no 1:1 16 bit A1R5G5B5 output, only converted 32bpp RGBA

Download: [https://github.com/Halamix2/stunt_gp_formats](https://github.com/Halamix2/stunt_gp_formats)
## Post #10
- Username: crysis150
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 09, 2014 1:53 am
- Post datetime: 2020-03-01T20:36:33+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

how use .pc converter on windows ? on my python27 i have error:

C:\Users\mtabi>C:\python27\python.exe C:\Users\mtabi\OneDrive\Pulpit\STUNDGP\pc_unpack.py
Traceback (most recent call last):
  File "C:\Users\mtabi\OneDrive\Pulpit\STUNDGP\pc_unpack.py", line 9, in <module>
    from pathlib import Path
ImportError: No module named pathlib
## Post #11
- Username: Halamix2
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 6:45 am
- Post datetime: 2020-03-02T18:56:24+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

The script was made for Python 3, version 2.7 support stopped three months ago, so I never bothered with compability/rewrite of that script
## Post #12
- Username: Halamix2
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 6:45 am
- Post datetime: 2021-01-03T21:05:47+00:00
- Post Title: StuntGP 3D/2D Files (.PC and .PMD)

Update on what was done for texture format:

 Now unpacker was rewritten from python to Go, it's 40x faster (still might be slower than martin solution, but it's now readable)
 no Python required, there is just a standalone .exe
 It also suppports Dreamcast textures (read/write)
 supports Playstation ones (read)
 can pack PC and Dreamcast textures

[https://github.com/Halamix2/stunt_gp_formats/releases](https://github.com/Halamix2/stunt_gp_formats/releases)
