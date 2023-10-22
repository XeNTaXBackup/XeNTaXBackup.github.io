## Post #1
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-12-23T18:17:05+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Hey guys! I've found this universal FLVER importer plugin for Blender on GitHub. (all credit goes to elizagamedev)
>
> 
>
> But it cannot open most FLVER character files. I forked it, and made some fixes on my own, however without the knowledge on how to properly debug a blender python plugin, I can't figure out how to fully fix it. Currently it throws an exception when retrieving weights. (Index out of range, in importer.py, line 164, it's got something to do with bmesh) When not importing the skeleton, it imports the mesh now without any errors, but the mesh looks pretty rough. (Looks like it's flat shaded)
>
> 
>
> If you have any insight, and could help me out, feel free to contribute.

OLD^

I gave up on getting that Blender plugin working. I've wrote a new program that can convert from Sekiro and newer (maybe older too, any flver will work that is a FLVER2) Fromsoftware FLVER into ASCII, in C#, using SoulsFormats. All credit goes to them. [https://github.com/JKAnderson/SoulsFormats](https://github.com/JKAnderson/SoulsFormats)

Issues:
Can't convert bones. Yet. See step 2 below!

Usage:

0. Open the exe. (Yes this has a very basic GUI)
0a. Optional: select a save location.
1. Select the .flver file you want to convert. Once you browse the file, it will convert immediately.
2. Use the Bloodborne tool (all credit goes to daemon1) to get correct bones, and copy them from that ascii to the ascii you got from this. (Replace the 0 at the beginning with the bones from the other (Bloodborne tool converted) ascii -- select everything from the beginning upto the same number you see under the 0)
3. Use XNALaraMesh.2.0.2 BLENDER plugin to open the ascii, make sure "Join MeshParts" is disabled. Noesis is NOT recommended, since most hair/fur have 3 UVs -- Noesis only exports 2 at most. (At least into FBX)
4. Have fun. 
[FlverToAscii0100b.7z](https://xentaxbackup.github.io/file/21490_FlverToAscii0100b.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-23T20:47:17+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

well, my insight is not that much deep, usually I use print lines for debugging py scripts:

```
                weights = inflated_mesh.vertices.bone_weights[vert.index]
                indices = inflated_mesh.vertices.bone_indices[vert.index]
                for index, weight in zip(indices, weights):
                    if weight == 0.0:
                        continue
                    vert[weight_layer][index] = weight;print(weight)
```


Thus it displayed the weights of c2310.flver for me. If you print out vert.index you might get more clues.
(But without the sample flver in question it's hard to judge.)
## Post #3
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-12-23T22:20:53+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from shakotay2 ↑Fri Dec 24, 2021 4:47 am at Fri Dec 24, 2021 4:47 am
>
> 
well, my insight is not that much deep, usually I use print lines for debugging py scripts:
Code: Select allfor vert in bm.verts:
                weights = inflated_mesh.vertices.bone_weights[vert.index]
                indices = inflated_mesh.vertices.bone_indices[vert.index]
                for index, weight in zip(indices, weights):
                    if weight == 0.0:
                        continue
                    vert[weight_layer][index] = weight;print(weight)

Thus it displayed the weights of c2310.flver for me. If you print out vert.index you might get more clues.
(But without the sample flver in question it's hard to judge.)

Thank you! Any Sekiro or newer (...dont wanna mention that game here, but you know the one) FLVER will do really, especially ones that have stuff like hair/alpha materials in them, for making sure it extracts the UVs right.

One other thing that needs to be fixed in the script is storing both UVs from the UV_PAIR (diffuse and lightmap UVs), but I'm not sure how to do that using bmesh.

I can send you a newer FLVER in private message though if that's okay.

EDIT: okay the weights are empty. No wonder it doesn't work.

The problem lies in here:

```
            weights = struct.unpack_from("BBBB", buf, offset)
            return tuple(weight / 32767.0 for weight in weights)

```


I have no idea what format to interpret that BYTE4C as, and what value to divide it with. (if it even needs division)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-23T23:46:27+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from kotn3l ↑Fri Dec 24, 2021 6:20 am at Fri Dec 24, 2021 6:20 am
>
> I have no idea what format to interpret that BYTE4C as,You're in _unpack() of flver.py, aren't you?

Why do you inserted
weights = struct.unpack_from("BBBB", buf, offset)
for .BYTE4C and not for .BONE_WEIGHTS?


I get this log when printing self.data_type:
0xc878 DataType.BONE_INDICES
...
0x1be68 DataType.BONE_INDICES
0x0 DataType.BONE_WEIGHTS
0x28 DataType.BONE_WEIGHTS
...
0x1be68 DataType.BONE_WEIGHTS
0x0 DataType.UV
0x28 DataType.UV
...
0x1be68 DataType.UV
visible backfaces: c2310
0x0 DataType.FLOAT3
0x28 DataType.FLOAT3
...
0x4290 DataType.FLOAT3

-----------------------------------
I don't have insight into the code but there's self.DataType.BONE_WEIGHTS, so why not use (refer to) that?

How do you know what BYTE4C stands for? And why do you think it's weights? 

```
        # Two single-precision floats.
        FLOAT2 = 0x01
        # Three single-precision floats.
        FLOAT3 = 0x02
        # Four single-precision floats.
        FLOAT4 = 0x03
        # Unknown.
        BYTE4A = 0x10
        # Four bytes
        BONE_INDICES = 0x11
        # Two shorts?
        SHORT2_TO_FLOAT2 = 0x12
        # Four bytes.
        BYTE4C = 0x13				<<<
...
```


```
        if self.data_type in {
                self.DataType.BYTE4A,
                self.DataType.BONE_INDICES,
                self.DataType.SHORT2_TO_FLOAT2,
                self.DataType.BYTE4C,			<<<
                self.DataType.UV,
                self.DataType.BYTE4E,
        }:
            return 4
```
## Post #5
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-12-24T12:16:20+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from shakotay2 ↑Fri Dec 24, 2021 7:46 am at Fri Dec 24, 2021 7:46 am
>
> 
kotn3l wrote: ↑Fri Dec 24, 2021 6:20 amI have no idea what format to interpret that BYTE4C as, You're in _unpack() of flver.py, aren't you?

Why do you inserted
weights = struct.unpack_from("BBBB", buf, offset)
for .BYTE4C and not for .BONE_WEIGHTS?
Yes, I'm in that function.

If I delete the BYTE4C if lines, upon importing a newer a FLVER file, I get the exception that BYTE4C data type is not implemented yet for bone weights. (from the end of the if-else statements) It is storing weights, but in BYTE4C format. 

Can you send that flver you're using to me? I only have Bloodborne and newer ones, and they're all using BYTE4C, so I can't print out the BONE_WEIGHTS one since it never enters that if. If I can see how the "original" weights look, I might be able to figure out how to read the BYTE4C data as. Or please send a screenshot of print(weights).

Btw Bloodborne models now import successfully after implementing SHORT_BONE_INDICES, but alas, no weights. And newer FLVER still throws an exception because the index is out of range. Not any Blodoborne model do though. Weird
## Post #6
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-12-25T17:14:43+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

Okay so a working DS1 weights look like this:


Bloodborne BYTE4C weights as 4 unsigned shorts and divided by 65535 (so they will be ranging from 0.0 and 1.0), doesnt throw any exceptions, but weights do nothing:


Sekiro and newer BYTE4C as 4 unsigned shorts and divided by 65535, throws an index out of range exception, weight parts imported do nothing


Looks like they're not ordered? In DS1 models it's mostly the first 2-3 values are not 0, in the other ones its all over the place. I'm not a reverse engineer so I'm out of any ideas :/

Interpreting BYTE4C as 4 unsgined chars and dividing by 255 results in data ranging between 0.0 and 1.0, but alas the weights dont work.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-25T18:15:10+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

what I can tell is that "sum of weights" should be 1.0 (for each vertex). Maybe it's lower (not sure) but never above.

So something like (... ... 1.0 1.0) is no weights, probably. Unless you're using a wrong divider. Additionally divided by 2 you'd get (... ... 0.5 0.5)
## Post #8
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-12-25T19:37:52+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from shakotay2 ↑Sun Dec 26, 2021 2:15 am at Sun Dec 26, 2021 2:15 am
>
> 
what I can tell is that "sum of weights" should be 1.0 (for each vertex). Maybe it's lower (not sure) but never above.

So something like (... ... 1.0 1.0) is no weights, probably. Unless you're using a wrong divider. Additionally divided by 2 you'd get (... ... 0.5 0.5)

Okay okay according to Soulsformats BYTE4C data should be divided by 255 like i thought:

```
                        {
                            for (int i = 0; i < 4; i++)
                                BoneWeights[i] = br.ReadByte() / 255f;
                        }

```

Now I just dont know for sure how to read them in as bytes.

```

```


Whats the correct python format for bytes? I'm a dumbass when it comes to python lmfao even when I read this site: [https://docs.python.org/3/library/struct.html](https://docs.python.org/3/library/struct.html)

Shouldnt BBBB format work?

EDIT: this should work. All weights summed up are 1.0. and it just doesnt work:

```
            weights = struct.unpack_from("BBBB", buf, offset)
            return tuple(weight / 255.0 for weight in weights)

```


I'm out of ideas
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-25T22:52:54+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

It's hard to follow your thoughts. When I use

```
            return tuple(weight / 255.0 for weight in weights)
```

(in flver.py) with c00_000_00.flver (Bloodborne)
I get this error:
struct.error: unpack_from requires a buffer of at least 12 bytes
## Post #10
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-12-25T23:11:44+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from shakotay2 ↑Sun Dec 26, 2021 6:52 am at Sun Dec 26, 2021 6:52 am
>
> 
It's hard to follow your thoughts. When I use
Code: Select all            weights = struct.unpack_from("BBBB", buf, offset)
            return tuple(weight / 255.0 for weight in weights)
(in flver.py) with c00_000_00.flver (Bloodborne)
I get this error:
struct.error: unpack_from requires a buffer of at least 12 bytes

Yes, Bloodborne also needs SHORT_BONE_INDICES implemented:

```
                self.DataType.FLOAT2,
                self.DataType.UV_PAIR,
                self.DataType.BONE_INDICES,
                self.DataType.BONE_WEIGHTS,
                self.DataType.SHORT4_TO_FLOAT4B,
                self.DataType.SHORT_BONE_INDICES, -------- HERE
        }:
            return 8

```


```
                return tuple(struct.unpack_from("HHHH", buf, offset))

```


I pushed these changes up into the repo.

If it still doesn't work try it with a character. I tried with c5400 and c2090.
## Post #11
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2022-01-01T00:42:09+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

I gave up on getting that Blender plugin working. I've wrote a new program that can convert from Sekiro and newer (maybe older too, any flver will work that is a FLVER2) Fromsoftware FLVER into ASCII, in C#, using SoulsFormats. 

Check the first post!
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-01T05:18:22+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from kotn3l ↑Sat Jan 01, 2022 8:42 am at Sat Jan 01, 2022 8:42 am
>
> 
I've wrote a new program that can convert from Sekiro and newerI admire that spirit! Have a good year, Mr Anderson!
## Post #13
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2022-01-01T14:19:54+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from shakotay2 ↑Sat Jan 01, 2022 1:18 pm at Sat Jan 01, 2022 1:18 pm
>
> 
kotn3l wrote: ↑Sat Jan 01, 2022 8:42 am
I've wrote a new program that can convert from Sekiro and newerI admire that spirit! Have a good year, Mr Anderson!

Thank you, I wish the same to you! Thanks for all the help too!!
## Post #14
- Username: bootyflute
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 24, 2021 9:28 am
- Post datetime: 2022-03-08T20:49:50+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from kotn3l ↑Sat Jan 01, 2022 10:19 pm at Sat Jan 01, 2022 10:19 pm
>
> 
shakotay2 wrote: ↑Sat Jan 01, 2022 1:18 pm
kotn3l wrote: ↑Sat Jan 01, 2022 8:42 am
I've wrote a new program that can convert from Sekiro and newerI admire that spirit! Have a good year, Mr Anderson! 


Thank you, I wish the same to you! Thanks for all the help too!!

Is there anyway to do a batch convert? I want to convert tons of files and doing it one by one has been a big hassle. Not sure how much demand there would be for this but it might be useful to others! Thanks again for the tool!
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-03-08T23:18:51+00:00
- Post Title: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from bootyflute ↑Wed Mar 09, 2022 4:49 am at Wed Mar 09, 2022 4:49 am
>
> Is there anyway to do a batch convert?Depends on whether the C# program supports command line parameters. Check this first, please. (If not, adding support should be possible, since the source is given.)
## Post #16
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2022-03-09T01:48:36+00:00
- Post Title: Re: FromSoft FLVER to ASCII (Sekiro and newer)

On some models Daemons bloodborne tool doesn't make ascii models, so I can't transfer the bones to the ascii made from this tool to get proper bones
## Post #17
- Username: bootyflute
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 24, 2021 9:28 am
- Post datetime: 2022-03-09T04:22:46+00:00
- Post Title: Re: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from shakotay2 ↑Wed Mar 09, 2022 7:18 am at Wed Mar 09, 2022 7:18 am
>
> 
bootyflute wrote: ↑Wed Mar 09, 2022 4:49 amIs there anyway to do a batch convert?Depends on whether the C# program supports command line parameters. Check this first, please. (If not, adding support should be possible, since the source is given.)

I wish I knew more programming, but using "C:\FLVERtoASCII.exe C:\1.flver" seems to just load the program. I wanted to hopefully extract all the maps and enemies for a custom Pathfinder campaign and have all the .flvers extracted but would prefer .ascii/.smd files since blender can't properly load all .flver flies.
## Post #18
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2022-03-09T20:54:40+00:00
- Post Title: Re: FromSoft FLVER to ASCII (Sekiro and newer)

since this used soul format, is it possible to get this to work with the older games flver?
## Post #19
- Username: yaqdhan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 19, 2020 7:49 pm
- Post datetime: 2022-03-12T01:47:23+00:00
- Post Title: Re: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from kotn3l ↑Fri Dec 24, 2021 2:17 am at Fri Dec 24, 2021 2:17 am
>
> 
Hey guys! I've found this universal FLVER importer plugin for Blender on GitHub. (all credit goes to elizagamedev)

But it cannot open most FLVER character files. I forked it, and made some fixes on my own, however without the knowledge on how to properly debug a blender python plugin, I can't figure out how to fully fix it. Currently it throws an exception when retrieving weights. (Index out of range, in importer.py, line 164, it's got something to do with bmesh) When not importing the skeleton, it imports the mesh now without any errors, but the mesh looks pretty rough. (Looks like it's flat shaded)

If you have any insight, and could help me out, feel free to contribute.


OLD^

I gave up on getting that Blender plugin working. I've wrote a new program that can convert from Sekiro and newer (maybe older too, any flver will work that is a FLVER2) Fromsoftware FLVER into ASCII, in C#, using SoulsFormats. All credit goes to them. https://github.com/JKAnderson/SoulsFormats

Issues:
Can't convert bones. Yet. See step 2 below!

Usage:

0. Open the exe. (Yes this has a very basic GUI)
0a. Optional: select a save location.
1. Select the .flver file you want to convert. Once you browse the file, it will convert immediately.
2. Use the Bloodborne tool (all credit goes to daemon1) to get correct bones, and copy them from that ascii to the ascii you got from this. (Replace the 0 at the beginning with the bones from the other (Bloodborne tool converted) ascii -- select everything from the beginning upto the same number you see under the 0)
3. Use XNALaraMesh.2.0.2 BLENDER plugin to open the ascii, make sure "Join MeshParts" is disabled. Noesis is NOT recommended, since most hair/fur have 3 UVs -- Noesis only exports 2 at most. (At least into FBX)
4. Have fun.

Hello, the XNALara to Blender python script (2.0.2) doesn't seem to support the elden ring ascii file that I extracted with your tool
(And yes, I disabled join MeshParts)
[Blender Info Log 12_03_2022 02_25_34.png](https://xentaxbackup.github.io/file/21934_Blender Info Log 12_03_2022 02_25_34.png)
## Post #20
- Username: KenseiMyk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 22, 2020 4:10 am
- Post datetime: 2023-02-16T00:25:06+00:00
- Post Title: Re: FromSoft FLVER to ASCII (Sekiro and newer)

> Reply from yaqdhan ↑Sat Mar 12, 2022 9:47 am at Sat Mar 12, 2022 9:47 am
>
> 
Hello, the XNALara to Blender python script (2.0.2) doesn't seem to support the elden ring ascii file that I extracted with your tool
(And yes, I disabled join MeshParts)
Hey, did you ever got a fix for this? I tried doing it with Sekiro (c5400 (SS Isshin)) and also got this error. If there's a solution can somebody help me? Thanks.
