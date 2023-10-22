## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-03T12:29:37+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

I have this BMS script from old ps23dformat blog of 3dformat for converting PCSX2 eeMemory.bin to 3ds

It actually works for both Gran Turismo 3 and 4 but not quite. Something a little bit wrong in bytes order maybe?
here's the issues:
there's no UV
meshes are jumbled together in a single mesh

Maybe you guys can help me to improve it? Simple model separated to meshes with UVs would be pretty cool.

Here's example of model I'm trying to obtain:


Here's what I get, basically it happens to every model:



Here's files for GT3: [DOWNLOAD](https://drive.google.com/open?id=1MPVAzznjKytqaZIXszmdyXtfFEKT4L1Z)
Here's files for GT4: [DOWNLOAD](https://drive.google.com/open?id=1GV2q-ARPItGCrgM_Kbga0j_zeGJ_W0k7)
bms script is also attached below


 GT4eememoryto3ds_r2012_10_30.zip
(1.32 KiB) Downloaded 27 times



p.s.: just open eeMemory.bin file with GT4eememoryto3ds.BMS and save outpu somewhere, you should get a bunch of 3ds files
I found other researches of eeMemory.bin:
[viewtopic.php?t=14402](https://forum.xentax.com/viewtopic.php?t=14402)
[https://zenhax.com/viewtopic.php?f=5&t=7305](https://zenhax.com/viewtopic.php?f=5&t=7305)
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-04T15:54:03+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

I split eeMemory and got several MDLS files. Here's the car:
[https://drive.google.com/open?id=11TU_t ... UWupcbd-eC](https://drive.google.com/open?id=11TU_tA_LYZB1C3Kma0D1cBUWupcbd-eC)
here's the disk:
[https://drive.google.com/open?id=1N648I ... VuY1SLj8B0](https://drive.google.com/open?id=1N648IE5mr9utQiiubj3O6wVuY1SLj8B0)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-05T19:57:09+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

Funny to see people using FurryFan's bms scripts after all the years.  
Format/ data arrangement has changed a little bit for GT4 so another patch required for getting uvs:
.



1_3DS_GT4.png (203.16 KiB) Viewed 253 times


(Sadly I've got a 4-bytes-offset problem at some point which I couldn't understand so far.)

This would be an easy fix with 'C' or another higher language, I guess. So this is what I will never understand:
why do coders use a bms script for extracting 3D  models? (A no go for me.  )

Quickbms is great, really, for unpacking archives/repacking, decompressing, whatever.

But this script does a simple logging (apart from some other more complex things):
log MEMORY_FILE2 0 0 ;

(And with no indents it's unreadable, more or less.)

And you need some humor for lines like this one:
Math JumpJump = Snake ;

But at the "end of fun" (eof  ) you'll realize that you have to translate every single one of these nonsense terms to understand what's going on.
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-05T21:29:37+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

glad you've came to the light, shakotay2. I was aware you've already tried this format some while ago.
I tried every possible ways of ripping these models out of the ps2 emulators for 2 weeks now and nothing works.
turns out these eeMomory consist of the same data that can be obtained by unpacking/decrypting the games data itself

I think the coders use the language they most comfortable with  

p.s.: not sure what's up with your message box, I've sent you examples via PM

p.p.s.: here's what FurryFun wrote about gt3 (maybe it's fair for gt4 as well) on his site:

```
Main section:
SubMeshFormat
00 C0 XX 68
4ByteFloatingPointVertexes(X,Y,Z)
UnknownBytes
80 C0 XX 68
4ByteFloatingPointNormalMappings(X,Y,Z)
UnknownBytes
```


p.p.p.s.: also here's guide from FurryFun on how to get gt3 models but I don't get it at all:


 GT3ModelGuide.7z
(150.32 KiB) Downloaded 19 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-05T22:30:50+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

Yeah, thanks, but "GT3ModelGuide.txt" treats some basics only. He doesn't deal with the uvs.
I had a solution for Wild Arms 3 uvs already:

> Reply from shakotay2 ↑Mon Jan 25, 2021 7:55 am at Mon Jan 25, 2021 7:55 am
>
> 
but as I mentioned, for GT4 details changed (didn't check GT3).

btw: I didn't mean to be ungrateful for FurryFan's work. Without him we would have nothing.
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-06T05:26:59+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

> Reply from shakotay2 ↑Wed Oct 06, 2021 6:30 am at Wed Oct 06, 2021 6:30 am
>
> 
Yeah, thanks, but "GT3ModelGuide.txt" treats some basics only. He doesn't deal with the uvs.yeah, it doesn’t. It’s just a part of everything I could find from ff’s website 

> Reply from shakotay2 ↑Wed Oct 06, 2021 6:30 am at Wed Oct 06, 2021 6:30 am
>
> 
I had a solution for Wild Arms 3 uvs already:
shakotay2 wrote: ↑Mon Jan 25, 2021 7:55 am
but as I mentioned, for GT4 details changed (didn't check GT3).that’s the reason why I start messing with eeMemory it’s because I saw your research and thought well I have little bit of a chance. Because there was no other way but turned out eeMemory contains the same data as the original files

I knew FurryFan’s scripts can be pain to deal with but I didn’t realize it could be that bad
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-06T07:52:30+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

I have this source code but for gt2. I dunno if it can help anyhow:
[https://drive.google.com/open?id=1Ecxjq ... WhT13S4QgW](https://drive.google.com/open?id=1Ecxjq0OsZ0wW7F8rfwjmyZWhT13S4QgW)

here's interesting file from this source to read CDO file. this CDO file contains "GT" as its magic


 gt2_cdo_delphi.zip
(1.78 KiB) Downloaded 14 times


and decrypted model from gt3 contains "GT" as well
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-10T11:17:28+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

I found these docs regarding gt4 formats:
[https://github.com/Nenkai/GT-File-Speci ... ormats/GT4](https://github.com/Nenkai/GT-File-Specifications-Documentation/tree/master/Formats/GT4)

@shakotay2, maybe it somehow help to convert models?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-10T12:38:05+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

Well, thanks, but I didn't find a hint in GT4_CAR4_CarInfo.bt or GT4_MDLS_ModelSet.bt.
Guess Furryfan's script is the nearest hit, against all odds.  

Sooner or later I'll find the trick with the uvs, I hope:
.



GT4_uvs.png (67.65 KiB) Viewed 208 times


(It looks as it were just a matter of suiting addresses.)
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-10T19:01:14+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

> Reply from shakotay2 ↑Sun Oct 10, 2021 8:38 pm at Sun Oct 10, 2021 8:38 pm
>
> 
Well, thanks, but I didn't find a hint in GT4_CAR4_CarInfo.bt or GT4_MDLS_ModelSet.bt.weird that they didn’t help   

> Reply from shakotay2 ↑Sun Oct 10, 2021 8:38 pm at Sun Oct 10, 2021 8:38 pm
>
> Sooner or later I'll find the trick with the uvs, I hope:
.
GT4_uvs.png
(It looks as it were just a matter of suiting addresses.)this looks very promissing, thank you for looking into that
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-10T21:52:13+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

Well, there's some oddities which are hard to track because there's so many small sub meshes:
.



GT4_hard2track.png (209.81 KiB) Viewed 194 times
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-10T22:23:09+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

> Reply from shakotay2 ↑Mon Oct 11, 2021 5:52 am at Mon Oct 11, 2021 5:52 am
>
> 
Well, there's some oddities which are hard to track because there's so many small sub meshes:
.
GT4_hard2track.png
wow man. this is the best result from 2004. does these small parts conform to the same rules?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-15T21:15:53+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

which "rules"?

btw, still struggeling with uvs:
.



GT4_1_.jpg (243.58 KiB) Viewed 176 times


(Dozens of others look really weird/wrong.)
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-15T22:35:36+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

I mean do you apply same rules for convert car parts all together or you need to manually find the offset and apply it to convert each part?
btw here's textures of that honda: [https://drive.google.com/open?id=1Hga_3 ... q-ydiaWnN-](https://drive.google.com/open?id=1Hga_3yN-ihFqCCW3Izc9tcq-ydiaWnN-)
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-16T04:33:32+00:00
- Post Title: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

> Reply from Tosyk ↑Sat Oct 16, 2021 6:35 am at Sat Oct 16, 2021 6:35 am
>
> 
I mean do you apply same rules for convert car parts all together or you need to manually find the offset and apply it to convert each part?Yeah, very good description of the problem I'm facing. Usually you'd think the uvs  to start after their signature. And this signature to start (vertexcount[previous sub mesh]*(12+4+12+4)) bytes after the previous vertex block signature, something like this.

Sadly some uv blocks don't follow that rule (might have to do something with the +4 (weighting float, whatever)).

So yes, all the time I tried to find the correct uvs' offset for some blocks using hex2obj.
(And all the time I had a stupid bug, this index-1 thingie, so all uvs' block started "one too early" which I realized just yesterday.)
(Didn't understand the problem, so inserted a dummy block to fix this.  )

Still some weird uv blocks, though.

> btw here's textures of that honda: https://drive.google.com/open?id=1Hga_3 ... q-ydiaWnN-Thanks!   That's what I would have asked for next.
## Post #16
- Username: Cornalito
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 19, 2018 5:52 am
- Post datetime: 2021-10-16T06:44:30+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

I used to extract the GT PSP models using ninja reaper, every model has two meshes, one for the body (textures), and the other one for reflection, also at the moment of apply textures some UVs had issues and had to correct the UVs manually
## Post #17
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-16T09:05:32+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

@shakotay2, I see that the issues with polygons crosses the entire model are still present. Is this another problem you don't know how to solve or you just don't care much about it at the moment?
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-16T10:51:46+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

I don't care, I don't know...
(well, I hope it's a matter of how the faces are built)

The formula used basically is like such (loop):
f a  a+1 a+2
a += 1 ;

Result:
f 1 2 3
f 2 3 4
...

But when you compare to those in the 3ds files created by the bms script there's some differences.

Maybe auto generated triangles strips will do better. As you can see here: 
> Reply from shakotay2 ↑Sun Oct 10, 2021 8:38 pm at Sun Oct 10, 2021 8:38 pm
>
> 
Say
f 1/1 2/2 3/3
f 2/2 4/4 3/3
f 3/3 4/4 5/5

or 
f 1 2 3
f 2 4 3
f 3 4 5
f 4 6 5
...
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-17T20:28:15+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

well, finally, I decided to create a Make_H2O version for Gran Turismo 4. 
Credits go to FurryFan for his Gran Turismo 4 quickbms script. (I've added creation of uvs to the tool, which were missing. But, many are weird, still. See notes in zip file.)

(There's other posts where I described how to use the Multi mesh feature of hex2obj, File/SaveAs Mmesh)
Most important: hex2obj has to be switched to "Strip" and "Fake" here to successfully use the H2O files (from Make_H2O) for obj creation.
.


 MakeH2O-bins-GranT4.zip
(185.57 KiB) Downloaded 19 times


Tested with one 32 MB eeMemory.bin file only, so don't blame me, if it doesn't work for others.

You may use "Remove Doubles" from the meshes (in blender, for example). Didn't notice any advantage, though.

H2O file _143 (_43.obj), rearBumper a), wrong uvs:

0x0 3
Vb1
12 99
0x145c2d4 62
021000
0x145c4bc 8

uvs correction (maybe), replace last line by
145C6C0 12

Address is after signature [40C0 count 68], count is 0x3E= 62 here (same as vertex count)

rearBumper parts which seem to be "ok", _75 and _76 (_140.obj, _141.obj):

0x0 3
Vb1
12 99
0x14462E4 50
021000
0x144679C 8

and 

0x0 3
Vb1
12 99
0x1446964 62
021000
0x1446F3C 8
## Post #20
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-18T17:28:22+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

thanks @shakotay2, I'm trying to understand the process.
rn I'm getting the list of OBJX files:


If I rename them into OBJ and try to import into blender v2.74 I get this error:


I woud suggest you to use original gt4 files of cars because they are basically the same binary files that included to eeMemory.bin but with own header. here's the files: [https://drive.google.com/open?id=1ya_uo ... Tx7C3vSRcd](https://drive.google.com/open?id=1ya_uoqmZ3NLH9TfSb19w2iTx7C3vSRcd)
FurryFan's bms script work with original files the same way it work with eeMemory.bin and extracts the same 3ds object.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-19T06:38:00+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

> Reply from Tosyk ↑Tue Oct 19, 2021 1:28 am at Tue Oct 19, 2021 1:28 am
>
> 
thanks @shakotay2, I'm trying to understand the process.
rn I'm getting the list of OBJX files:
Please read my previous post again:

> Reply from shakotay2 ↑Mon Oct 18, 2021 4:28 am at Mon Oct 18, 2021 4:28 am
>
> ...
Most important: hex2obj has to be switched to "Strip" and "Fake" here to successfully use the H2O files (from Make_H2O) for obj creation.(And don't forget to delete/move all obj files of a maybe previous run.)
-----------------------------------------

> Reply from Tosyk ↑Tue Oct 19, 2021 1:28 am at Tue Oct 19, 2021 1:28 am
>
> FurryFan's bms script work with original files the same way it work with eeMemory.bin and extracts the same 3ds object.Without uvs.

btw: Make_H2O... ignores the eeMemory header (if any). (So does hex2obj.)

Known problems are the face indices, maybe they are indexed?
.



GT4_windowScreen.png (201.56 KiB) Viewed 130 times
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-19T22:21:22+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

thanks! seems like a found why I couldn't follow you instructions. it's because I see this when I open h2o:


Anyways. I did everything and get the objects. Some of them has UVs, but most are mess unfortunately. Here's best matches:

another one:


Most of the object's UVs are like this:


I tried this method with 'pk0100_out\00006008.car' file of original gt4 game ([link](https://drive.google.com/open?id=1ya_uoqmZ3NLH9TfSb19w2iTx7C3vSRcd)) and was able to get only a tire in different LODs but seems like all of their UVs are fine:
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-20T06:48:04+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

> Reply from Tosyk ↑Wed Oct 20, 2021 6:21 am at Wed Oct 20, 2021 6:21 am
>
> Anyways. I did everything and get the objects. Some of them has UVs, but most are mess unfortunately."Some of them?" Well, comments like these tend me to stop my investigations. It's more than 100 out of 165 uvs which are not a mess.

Also it seems that ..._72.obj (derived from _172.H2O, yes _172) shouldn't have uvs as a simple calculation and "check of eeMemory.bin in hexeditor" shows:

vertices at 0x1464a50 - 0x1464774 = 0x2DC (block size)
(732/12= 61 verts)
Then signature 80C03D6E, 3D=count, 61*4=244= 0xF4
0x1464a50+8 + 0xF4= 0x1464B4C
so no uvs block here before
next vertex block at 0x1464B78

Make_H2O_GranT4.exe doesn't "realize" that there's no uvs. That's the reason why it creates H2O files then which make hex2obj show parts of vertex data as "messy uvs".
## Post #24
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-10-20T07:11:40+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

I didn't want to sound ungrateful. I appreciate for your help! Its' just a complicated stuff for me. Here' what I get from the h2o:
[https://drive.google.com/open?id=1Hrvuz ... Ety0NT09En](https://drive.google.com/open?id=1Hrvuzwcu41rPv51D_dyR8NEty0NT09En)

I'll try to complete the process one more time today.
## Post #25
- Username: furutaka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 04, 2022 9:22 pm
- Post datetime: 2022-01-04T13:34:00+00:00
- Post Title: Re: Gran Turismo 3/4 eeMemory.bin to 3ds/obj

Hey, glad I found this topic.

After reading all of you guys talk about I still don't get it how to do it, yes, I wanted to extract the GT4 car models too but I don't know about coding, only know about 3D Modelling. Where and how should I start to extract Gran Turismo 4 car 3d models?

I want to extract them only for reference to learn how they create a low poly car with good such good shading, shape, and textures.
