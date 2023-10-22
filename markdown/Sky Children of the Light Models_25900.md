## Post #1
- Username: JohnyBoi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2022 2:42 pm
- Post datetime: 2022-10-12T10:45:33+00:00
- Post Title: Sky: Children of the Light Models

I'm pretty early, just wanted to ask if there was a way to open this game's models?
For switch and mobile it's no exception, the data is practically the same.

Models use a .MESH format,
and textures use a .KTX format, which can be opened with PVRTex Tool.

I haven't dug nor came up with a way to open the model files with the skeletons still in tact.
I've provided a [few of the .MESH files](https://mega.nz/folder/N8VAUDhK#AwcQhhbhfVR6Cbm-kqNlCA) for anyone that wants to experiment :I
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-10-12T23:25:47+00:00
- Post Title: Sky: Children of the Light Models

This game is really amazing, i too been looking for ways to convert it's characters/animations and even its very simple map levels, had no luck so far, hoping it will be noticed one day by someone
## Post #3
- Username: JohnyBoi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2022 2:42 pm
- Post datetime: 2022-10-13T11:23:26+00:00
- Post Title: Sky: Children of the Light Models

Yea.. exactly
## Post #4
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2022-10-15T00:14:12+00:00
- Post Title: Sky: Children of the Light Models

These files are compressed, maybe lz4.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-15T21:56:20+00:00
- Post Title: Sky: Children of the Light Models

Well, I used Aluigi's world famous comtype scanner with the first 300 compression types on Stone_dragon_body.mesh and nearest hit were some fake float blocks like these:
.



algo_37.jpg (221.6 KiB) Viewed 263 times

(163.dmp, 167.dmp, 230.dmp were similar, iirc)
Of course I may have missed the correct result (especially short/int vertex blocks are hard to detect) but finally I'd say:
probably you'll need to disassemble the game code to get the decompression algorithm.
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-10-27T19:46:18+00:00
- Post Title: Sky: Children of the Light Models

If it may help, older format of the game was partially reversed back then: [https://www.vg-resource.com/thread-39211.html](https://www.vg-resource.com/thread-39211.html)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-27T21:34:04+00:00
- Post Title: Sky: Children of the Light Models

Well, I created an lz4.exe from the code ([https://github.com/lz4/lz4](https://github.com/lz4/lz4)) and gave Stone_dragon_body.mesh a (what I thought to be decent) lz4 header like so:
.



lz4_test.jpg (155.4 KiB) Viewed 234 times


Added extension .lz4. Sadly the decompressed file has a size of zero bytes.

(Another attempt with the len DWord and "Stone_dragon_body" removed: again 0 bytes...)

Well, maybe I should take longbyte1's code into account (offset 0x52 in unpatched .mesh looks promising):

```
f.seek(0x52)
uncompressed_size = struct.unpack('i', f.read(4))[0]

# read compressed size
f.seek(0x4e)
compressed_size = struct.unpack('i', f.read(4))[0]

# read num lods
f.seek(0x44)
num_lods = struct.unpack('i', f.read(4))[0]

print('compressed_size', compressed_size)
print('uncompressed_size', uncompressed_size)
print('num_lods', num_lods)

# get compressed content
f.seek(0x56)
```
Compressed size 14835 dec., uncompressed size 26259 bytes, number of lods:1, would make sense
Compressed content starting at 0x56. I'll give it a last shot...
## Post #8
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-10-27T22:00:19+00:00
- Post Title: Sky: Children of the Light Models

@shakotay2: You can use this script for decompressing chunk with the first lod, it's direct implementation of longbyte1's code.



 sky_mesh_decompress.zip
(331 Bytes) Downloaded 37 times
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-27T22:03:17+00:00
- Post Title: Sky: Children of the Light Models

ha, bingo, from time to time I seem to have some luck:
.


 Stone_dragon_body-mesh3.zip
(11.43 KiB) Downloaded 27 times



@Spiritovod: thanks - too late.   Worked with the previous mentioned lz4.exe.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-27T22:12:45+00:00
- Post Title: Sky: Children of the Light Models

Hmm, stone dragon body? Strange:
.



Stone_dragon_body.jpg (122.19 KiB) Viewed 218 times
## Post #11
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2022-12-25T08:04:38+00:00
- Post Title: Sky: Children of the Light Models

will there be any more updates on this? even extracting models without armature (without using hex2obj) would still be nice
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-25T15:06:30+00:00
- Post Title: Sky: Children of the Light Models

Since the thread opener seems to have lost interest I didn't see a reason to continue...
## Post #13
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2022-12-25T22:03:22+00:00
- Post Title: Sky: Children of the Light Models

ohh ok, wanted to ask because I am interested in the model but alg if you don't want to continue!
## Post #14
- Username: eblansson
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 18, 2021 2:20 am
- Post datetime: 2023-07-04T15:43:51+00:00
- Post Title: Sky: Children of the Light Models

I guess the thread is pretty much dead, but there has been some good progress made when it comes to meshes!
[https://github.com/oldmud0/SkyEngineTools](https://github.com/oldmud0/SkyEngineTools)
I found this on VGResource. this is not my github, i don't understand how mesh file formats work
This gh has a python blender script that works for importing most of static meshes.

The most interesting thing is the imhex folder which describes the mesh format.

Not all of the meshes are supported yet though, the ones not supported have flags Cine, StripAnim, Anim and Col.
I also suspect that some of them may not be compressed, but most of them are with lz4.

I don't really understand how to read rigs and skeletons and stuff from mesh format, so any insight would be really appreciated!
Here's an archive with meshes in case someone would like to check out the formats:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/11lLvir3CtpylUex7UxzCbLt30umvyvF8?usp=sharing)
