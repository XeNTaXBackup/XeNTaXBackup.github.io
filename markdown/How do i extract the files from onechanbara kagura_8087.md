## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-20T06:45:02+00:00
- Post Title: How do i extract the files from onechanbara kagura

Hi, all
I'd like to extract cat file from Onechanbara Z Kagura.
May be cat file is encrypted.
the first 4 bytes
```
.х.н
```

 
Could anyone please take a look?
Here is a sample.
[delete](delete)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-20T08:21:51+00:00
- Post Title: How do i extract the files from onechanbara kagura

copy&paste from another post of mine:
---
job for xbdecompress.exe (Xbox SDK)
when you see a file that starts with the bytes 0f f5 12 that one is the tool you need

remember these 3 bytes and make it your new religion because you will see them a lot in many x360 games :)
---
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-20T08:46:34+00:00
- Post Title: How do i extract the files from onechanbara kagura

> Reply from aluigi
>
> copy&paste from another post of mine:
---
job for xbdecompress.exe (Xbox SDK)
when you see a file that starts with the bytes 0f f5 12 that one is the tool you need

remember these 3 bytes and make it your new religion because you will see them a lot in many x360 games 
---

Thank your for your assistance	
I clean forgot about it until now.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-20T11:35:38+00:00
- Post Title: How do i extract the files from onechanbara kagura

Dont post like this.
please say how do i extract the files from onechanbara kagura.
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-20T11:56:25+00:00
- Post Title: How do i extract the files from onechanbara kagura

> Reply from chrrox
>
> Dont post like this.
please say how do i extract the files from onechanbara kagura.
O.K. I'll be more careful.
It combines  decrypted file and encrypted file in a single file, and fix the title, so just calm down.
[delete](delete)
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-20T19:13:36+00:00
- Post Title: How do i extract the files from onechanbara kagura

nice... i see see obvious index and vertex buffers. i'm sure somebody is gonna reverse this one soon. looks easy peazy.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-21T00:30:14+00:00
- Post Title: How do i extract the files from onechanbara kagura

Geometry very easy to find. Wonder if the textures are swizzled...
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-21T01:44:41+00:00
- Post Title: How do i extract the files from onechanbara kagura

they are swizzled but they are standard xpr files.
just use the sdk tool unbundler on them
## Post #9
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-21T04:48:20+00:00
- Post Title: How do i extract the files from onechanbara kagura

> Reply from howfie
>
> Geometry very easy to find. Wonder if the textures are swizzled...
Really fast.
How to extract *_.cat file?
## Post #10
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-21T13:47:48+00:00
- Post Title: How do i extract the files from onechanbara kagura

@howvie : great job you've done there !

I also managed to get the mesh's vertices just like your picture.
However I'm totally clueless about the UV coordinates data, have you locate them??
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-21T22:46:04+00:00
- Post Title: How do i extract the files from onechanbara kagura

Did you try normalized unsigned shorts for uv coords? Also try to read vertex data that is not word aligned. If that doesn't work try looking at I think Surveyor's old Onechanbara thread; it might use a similar vertex structure and there might have been a trick. I don't have too much time to work on this. I am working on like 3 other games atm. I did the above in like 10 minutes just to try out the xbdecompress thing.
## Post #12
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-22T01:17:27+00:00
- Post Title: How do i extract the files from onechanbara kagura

Thanks for the hint, I'll check it up right away!
And Good luck for your work on those 3 games!
## Post #13
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-22T02:01:52+00:00
- Post Title: How do i extract the files from onechanbara kagura

actually i am about to give up on finding the bones on tekken hybrid, so if you get stuck let me know so we can bash heads on this one. i am currently redumping onechanbara from my home machine so i'll take a look again at it sometime tonight. btw welcome to the forums.
## Post #14
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-22T02:43:39+00:00
- Post Title: How do i extract the files from onechanbara kagura

The UV is written in unsigned shorts indeed, just need to normalize them to view properly (thanks to howfie).
Now just need to find the Material id and split the UVs.
## Post #15
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-22T06:52:29+00:00
- Post Title: How do i extract the files from onechanbara kagura

About the textures, I decompressed them and can see the "XPR2" Header from the Hex data.
But strangely, I tried "XPR Express" "MiteeXpr" "XPRextract" tools, none of them were able to extract the .xpr files into .dds textures as written in the hex.

Anyone has an idea?

EDIT : 
After hours of info searching, Those tools above seem to work on XPR, but these textures are XPR2, that's why they didn't work.
Finally managed to extract these XPR2 files, using the xdk tool unbundler.exe. (Ah, chrrox mentioned it above, how could I miss that   )
## Post #16
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-22T11:05:27+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

cool, progress is being made he he he almost there.

current problem i'm having: i found the skeleton, but... the skeleton is scaled and the scaling values are somewhere... can't find them. for the first model the skeleton is scaled by about 60% and rotated around X-axis by 90 degrees after outputting the matrices (with translation values modified to relative coordinates) to a DAE file.

[http://www.mediafire.com/?712s3p9dzrami2i](http://www.mediafire.com/?712s3p9dzrami2i)
## Post #17
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-22T13:52:06+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

@howfie : Great job on contructing the bones!
I also have this "Scaling" problem when extracting the UVs (seeing your .obj file, the UV range is still small caused by normalizing the unsigned shorts), 
so far I managed to get some decent result in scaling the UV by :

multiplying them by 64 (a magic number   )

Hope that can be some hint for you.
PS : I still can't find the Material ID anywhere, might work on this some other time I think..
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-22T14:50:43+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

cool thx, i'll go hunting for the material data too in a couple days. need to take a break ha ha ha.
## Post #19
- Username: dj082502
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-23T02:30:52+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

if you want to view the xpr files without having to run them through unbundler this will work.
[viewtopic.php?f=18&t=8102](http://forum.xentax.com/viewtopic.php?f=18&t=8102)
## Post #20
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-24T01:12:33+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

Awesome, the plugin works fine. Thanks chrrox
## Post #21
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-25T07:43:34+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

Fixed the bones thing... Max was converting units so I guess instead of having my program generate an OBJ + DAE I guess I will have to just move to DAE only. All that's left is to find the weights and fix a few vertex formats and it will be ready for a release. Animations are store in the mot directories, and it's tempting to start working on it.
## Post #22
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-25T12:55:50+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

@howfie : great progress!! Where did you find the Material Id to split the UVs?
## Post #23
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-25T13:17:57+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

I didn't. I found material names (all names are 4 characters long) and I found the triangle groups section (how the index buffer is grouped). However, there usually are more groups than there are material names, and I couldn't find out how the groups are linked to the material names. So, in my modeler I just select a group (which I name surface_001, surface_002, and so on) and texture it manually ha ha ha.

For example, in pl00_00_00 [http://www.mediafire.com/?q429cxxgfw1cz7o](http://www.mediafire.com/?q429cxxgfw1cz7o) (my program decompresses and unpacks everything so here is my sample file):

Materials start at 0xA0 and each material is 0x38 bytes long. Data looks like this:

```
143.086
-10.7851
9.53648
163.921
8.07738
8
6
1
face
0
0
0
0
4294967295

```


There are 24 materials in this model.

Triangle groups start at 0x26A0 and end at 0x2767. Each group is 8 bytes. First number is number of triangle in group. Second number is triangle offset. But there is no data here that indicates how to texture the triangle groups. You can use this data to split the UVs. Here are the first two entries:

```
00AC 0000 000006A0

```

#1 There are 0x6A0 triangles in first group, starting at the 0th triangle.
#2 There are 0x0AC triangles in second groups, starting at the 0x6A0th triangle.
Multiply by 6 (sizeof(uint16)*3 points per triangle) to get the right offset.

There are 25 triangle groups in this model (one more group than materials).

BTW, I was using this formula for the player UV map... it works for every group except for one or two in every model! It's a variation of your multiply by 64 technique he he he. It's still pissing me off!

```
v.tv = 1.0f - (v07 % 1024)/1023.0f;

```
## Post #24
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-25T13:46:41+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

@howfie: Awesome   ! I Work on it right away!

EDIT : before the post, I managed to find the material names too, but I can't find how it links with the mesh. 
Your explanation about the "triangle groups" really makes everything clear. 
Thanks a lot howfie   !
## Post #25
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-25T14:10:00+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

Forgot to mention, when you display the material data without the bounding box data you get something like this:

```
 6 4 1 eye  0 0 0 0
10 4 1 eye_ 0 0 0 0
14 4 1 eye_ 0 0 0 0
18 4 0 _mat 0 0 0 0
22 4 1 mout 0 0 0 0
26 4 1 wep_ 0 0 0 0
30 4 1 wep_ 0 0 0 0
34 4 1 body 0 0 0 0
38 4 0 _muf 0 0 0 0
42 4 1 bura 0 0 0 0
46 4 0 _bur 0 0 0 0
50 4 0 _bur 0 0 0 0
54 4 1 pant 0 0 0 0
58 4 1 belt 0 0 0 0
62 4 1 belt 0 0 0 0
66 4 1 leg  0 0 0 0
70 4 0 _leg 0 0 0 0
74 4 0 _bel 0 0 0 0
78 4 0 _bel 0 0 0 0
82 4 1 grab 0 0 0 0
86 4 0 _rib 0 0 0 0
90 4 1 hat  0 0 0 0
94 4 1 hat_ 0 0 0 0

```


Wonder what that first number means? They all increment by 4 except for face with has a 6. All the ones with _name have a 0, the others have a 1. Hmmm... Ha ha ha fun shit trying to figure this stuff out isn't it?
## Post #26
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-25T14:26:24+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

Yeah, that's pretty interesting. If all of them are 4s and only the "face" is 6, then it might work like what u wrote above :

24 materials, 25 groups
4 code = 1 group for 1 material
6 code = 2 groups for 1 material

then it would be the reason why there are 25 groups while there are only 24 materials.
But this is just a hypothesis. 
Might look at this later (I'm still working on your "triangle groups" concept on my program now   )
## Post #27
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-25T22:19:02+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

You're genius ha ha ha! Gave me a good idea where to look. There was a part that I ignored that originally I thought was crap data. Not so! Right after the material section for pl_000_00, there is this data starting at 0x5E0, a sequence of unsigned short values. If you think of all data as shorts and each one of those 4s and 6s is the number of shorts you get this. Notice the ones that start with 0x3000 and that each group ends with 0x1000.

```
 6 4 eye : 2002 4001 3002 1000
10 4 eye_: 2003 4002 3003 1000
14 4 eye_: 2004 4003 3004 1000
18 4 _mat: 2005 4004 3005 1000
22 4 mout: 2006 4005 3006 1000
26 4 wep_: 2007 4006 3007 1000
30 4 wep_: 2008 4007 3008 1000
34 4 body: 2009 4008 3009 1000
38 4 _muf: 200A 4009 300A 1000
42 4 bura: 200B 400A 300B 1000
46 4 _bur: 200C 400B 300C 1000
50 4 _bur: 200D 400C 300D 1000
54 4 pant: 200E 400D 300E 1000
58 4 belt: 200F 400E 300F 1000
62 4 belt: 2010 400F 3010 1000
66 4 leg : 2011 4010 3011 1000
70 4 _leg: 2012 4011 3012 1000
74 4 _bel: 2013 4012 3013 1000
78 4 _bel: 2014 4013 3014 1000
82 4 grab: 2015 4014 3015 1000
86 4 _rib: 2016 4015 3016 1000
90 4 hat : 2017 4016 3017 1000
94 4 hat_: 2018 4017 3018 1000

```


 The face, which has two groups, has two 0x3000 values in it. It also has 2 0x2000 groups in it but if you look at another model, pl_003_00 (Saki), you will see that it's actually the 0x3000 values that associate a triangle group with a material!

```
 4 4 - 2001 4001 3001 1000 (eyeball, only 1 0x3000 value)
 8 6 - 2002 4002 3002 2003 3003 1000 (lips + face, 2 0x3000 values)
14 4 - 2004 4003 3004 1000 (upper small eyelashes, 1 0x3000 value)
18 4 - 2005 4004 3005 1000 (lower small eyelashes, 1 0x3000 value)
22 4 - 2006 4005 3006 1000 (upper large eyelashes, 1 0x3000 value)
26 4 - 2007 4006 3007 1000 (arms, 1 0x3000 value)
30 4 - 2008 4007 3008 1000 (sword, 1 0x3000 value)
34 5 - 2009 4008 3009 200A 300A 1000 (weapon holster + strap, 2 0x3000 values)
40 4 - 200B 4009 300B 1000 (weapon handle, 1 0x3000 value)
44 9 - 200C 400A 300C 200D 400B 300D 400C 300E 1000 (fingertips + hands + gloves, 3 0x3000 values)
53 4 - 200E 400D 300F 1000 (blouse, 1 0x3000 value)
57 6 - 200F 400E 3010 2010 3011 1000  (blouse ribbons + blouse trimmings, 2 0x3000 values)
63 7 - 2011 400F 3012 2012 4010 3013 1000 (upper body straps, upper body stap locks, 2 0x2000 values)
70 6 - 2013 4011 3014 2014 3015 1000 (pants + shoes, 2 0x2000 values)
76 4 - 2015 4012 3016 1000 (pant trimmings, 1 0x2000 value)
80 4 - 2016 4013 3017 1000 (blouse trimming, 1 0x2000 value)
84 4 - 2017 4014 3018 1000 (stomach, 1 0x2000 value)
88 4 - 2018 4015 3019 1000 (part of blouse, 1 0x2000 value)

```


The last 0x3000 value is 0x3019, and the 0x19 part is an index into the triangle group. 0x19 = index 25 and there are 26 triangle groups in model pl_003_00! Got it! Now we know how to name the triangle groups!

However, one triangle group for most models (but not all  of them have a messed up UV). Below is pl_003_00 (Saki). Can you spot the bad UV map, it's on the leg he he he stop looking at the panties man ha ha ha.
## Post #28
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-26T01:36:28+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

@howfie : Wow, I'm glad that can be a hint for you   !

Yes, I noticed some error in the UVs. 
Also, if you check pl_02_00(Aya), some groups' uvs are separated too far away up (y + 1.0).
Our original "UV rescaling calculation" may cause this, and we need to start looking for the real UV scaling value I guess.
## Post #29
- Username: gggrrrhhh2000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 13, 2010 2:34 pm
- Post datetime: 2012-01-26T05:47:10+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

After extracting the XPR textures in pl00_00(kagura) , I got these files (in .png, .tga or .dds):
        - body00 (diffuse, normal, specular)
        - face00 (diffuse, normal, specular)
        - wear00 (diffuse, normal, specular)
        - wear01 (diffuse, normal, specular)
4 Main Textures * 3 (diff, norm , spec), Total : 12 files 

So far, we have reduced : 

          A.Triangle Groups (25 pcs)" --> B.Material Groups (24 pcs)"  

So the idea next would be to convert :

           B.Material Groups (24 pcs)" --> C.Texture Groups (4 pcs, based on the XPR above)"

If we can find these "B->C" links, we can have a correct group of UV coordinates.
## Post #30
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-28T06:48:29+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

yep yep yep, looks like the UVs are being wrapped around a little bit. It's funny though because it doesn't happen to all UVs in the same triangle group. For example, here is group #24 from Aya. For her bra, the bra is fine, but the straps are messed up! All I had to do to fix it so it looks like in game is move the ones close to zero to one.

Before:


After:
## Post #31
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-28T10:37:48+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

lol, just load the u and v as signed 16-bit integers and use the following formula and voila!

```
v.v = -v07/1023.0f;

```
## Post #32
- Username: luciasil
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 24, 2010 9:48 am
- Post datetime: 2012-02-03T01:34:25+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

how do i extract the model file ?
## Post #33
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-03T01:40:53+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

I am not quite done with the ripper yet.
## Post #34
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-03T18:02:26+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

Texturing is now automatic . Almost ready... still can't find weights or normals, but other than that it is ready to go....
## Post #35
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-03T20:29:23+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

what is the problem with weighting? it looks like its just the last 8 bytes in the vertex structure.
## Post #36
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-03T21:15:47+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

Yes, but how they are scaled is weird. Looking at it I thought ok, there are 4 weights, all after the 0xFFFFFFFF. They should sum up to some maximum value. They aren't floats. They aren't half-floats either. It uses some kind of integer format. Using unsigned shorts, the sum of weights should sum up to 65535; but oftentimes, even the first 3 weights go over. Also, when you sum all 4 values, most of the time it comes short of 65535. Also, the first number is always large and over 65535/2 while the other numbers are usually 0 or less than 65535/2, which is kind of odd. It should be a mixed bag.

This if from player pl_00_00:

Example:

```
-6.89348
110.908
6.26402
218
31270
205
-715
4294967295
37230       (this + 513 is short of 65535)
0
513
0

```


```
4.93554
123.052
11.9846
225
13470
962
-42
4294967295
65280 (this + 2560 goes way over 65535)
0
2560
0

```


Also there are 4 bytes between the x-y-z coords and the u-v coords. The first byte is always 0. The next three are what I thought might be normals encoded as signed 8-bit integers, but everything I tried went awry.
## Post #37
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-03T22:01:30+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

looks like its just bytes in pl00_00_00.cat for example here are some examples
A9 56 00 00 01 00 00 00
in this its weight weight weight weight bone bone bone bone
the weights always add up to FF which is basically 1.0  so just divide the weight by 255.
another example
80 7F 00 00 09 06 00 00
the weights add up to ff again
there may be a bone index table for each mesh section because i dont see any values to high for the bone id's.
## Post #38
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-03T22:29:29+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

oh ha ha ha ha wow ha ha ha... you da man chrrox . now it's obvious what to do in the DAE file. yeah, the bones are always less than 200.
## Post #39
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-04T04:33:50+00:00
- Post Title: Re: How do i extract the files from onechanbara kagura

Make a thread in model section when you release a (new) tool.
