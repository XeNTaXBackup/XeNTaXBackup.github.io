## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-15T14:53:45+00:00
- Post Title: Tian Xia 3 models

Hello! finally a script works to get the files from this game, thanks to Ekey who made it and ikskoks to point me to it! I have been checking the files (.dat) and some seem like they have mesh info and some bones info too, was playing a bit with hex2obj but had no result, still checking other kinds of files because they are many. Hope someone can take a look at this, or tell me if these are not meshes related files, to start checking other files more deeply. Thanks in advance and have a good day!

[https://www.mediafire.com/file/bk8jhjwu ... s.zip/file](https://www.mediafire.com/file/bk8jhjwuldwlcec/TX3_Samples.zip/file)

UPDATE: I was checking more files, and found these, if the first samples have not any mesh, these could have    
https://www.mediafire.com/file/xr779nks ... 2.zip/file
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-15T21:16:53+00:00
- Post Title: Tian Xia 3 models

> Reply from moonpaladin ↑Tue Feb 15, 2022 10:53 pm at Tue Feb 15, 2022 10:53 pm
>
> 
Hello! finally a script works to get the files from this game, thanks to Ekey who made it and ikskoks to point me to it!We were lost if we hadn't Ekey, weren't we?   
Here's a result from a eNjBxyznuvi dat:
.



eNjBxyznuvi-0000000f-dat.png (102.14 KiB) Viewed 593 times
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-15T21:35:41+00:00
- Post Title: Tian Xia 3 models

> Reply from shakotay2 ↑Wed Feb 16, 2022 5:16 am at Wed Feb 16, 2022 5:16 am
>
> 
We were lost if we hadn't Ekey, weren't we?
absolutely  

> Reply from shakotay2 ↑Wed Feb 16, 2022 5:16 am at Wed Feb 16, 2022 5:16 am
>
> 
Here's a result from a eNjBxyznuvi dat:
Thanks!  shakotay2!:D
## Post #4
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-16T02:31:27+00:00
- Post Title: Tian Xia 3 models

> Reply from shakotay2 ↑Wed Feb 16, 2022 5:16 am at Wed Feb 16, 2022 5:16 am
>
> 
Thanks shakotay2!! btw could you check the other files if them have any kind of mesh info please, cause are not many of this kind of files (header (eN Blist))
## Post #5
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2022-02-16T14:23:27+00:00
- Post Title: Tian Xia 3 models

> Reply from moonpaladin ↑Tue Feb 15, 2022 10:53 pm at Tue Feb 15, 2022 10:53 pm
>
> 
Hello! finally a script works to get the files from this game, thanks to Ekey who made it and ikskoks to point me to it! I have been checking the files (.dat) and some seem like they have mesh info and some bones info too, was playing a bit with hex2obj but had no result, still checking other kinds of files because they are many. Hope someone can take a look at this, or tell me if these are not meshes related files, to start checking other files more deeply. Thanks in advance and have a good day!

https://www.mediafire.com/file/bk8jhjwu ... s.zip/file

UPDATE: I was checking more files, and found these, if the first samples have not any mesh, these could have    
https://www.mediafire.com/file/xr779nks ... 2.zip/file

Can u share the unpacker?
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-16T14:52:35+00:00
- Post Title: Tian Xia 3 models

> Reply from KingJuls ↑Wed Feb 16, 2022 10:23 pm at Wed Feb 16, 2022 10:23 pm
>
> 
Can u share the unpacker?
[http://aluigi.org/bms/1gab_2gab_bag.bms](http://aluigi.org/bms/1gab_2gab_bag.bms)
## Post #7
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-18T17:28:47+00:00
- Post Title: Tian Xia 3 models

Update
Hello, I updated the game today and understood a little more about what kind of files are each depending of his header. 

(EN¡b): This file list the textures(.tga, .bmp, .dds), effects (.fx)and animations (.action) that a "model" uses, besides that seems that contain bone information too, or could be wrong, but check these samples:
[https://www.mediafire.com/file/ediit1ss ... 9.zip/file](https://www.mediafire.com/file/ediit1ssoavt57s/samples_%2528EN%25C2%25A1b%2529.zip/file)

(eN¡Blist): Confirmed that this one contain mesh information, I was able to pull meshes from this kind of file (thanks to shakotay2). It is made up of submeshes.

(eN¡Bxyznuvi): This one contains mesh information too, the main difference to the (eN¡Blist), is that the values of the indices are below the values of the vertices.

(AHED): This one contains animation (.action) information.

(NOCMP): This one contain animation (.action) information too, but these one seems a slight different could be a list of animation for characters or other models that have many, generally the size of these files are bigger than AHED.

(GARBAGE FILES): It is generated because the (eN¡Blist) contain information about all files related to the model, so sometimes it cut any dd4 information or skin information, hopefully it not destroy any mesh file, really hope so xD.

Thanks for reading, and I really hope anyone gets interesting in this game. I was getting the meshes one by one but are ALOT of files, so it's gonna take alot of time to finish at that rate.
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-18T18:09:49+00:00
- Post Title: Tian Xia 3 models

> Reply from shakotay2 ↑Wed Feb 16, 2022 5:16 am at Wed Feb 16, 2022 5:16 am
>
> 
Hello shakotay! could you please take a look at this sample. I have doubts about the FVF size value   . Thanks!
[https://www.mediafire.com/file/025z7wrg ... a.dat/file](https://www.mediafire.com/file/025z7wrgntbzu90/sample_tianxia.dat/file)

ignore the "h" don't get mad xD
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-18T18:24:40+00:00
- Post Title: Tian Xia 3 models

Use 20E0 as start_of_vertices and 24 for uv pos (offset).
## Post #10
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-18T18:32:05+00:00
- Post Title: Tian Xia 3 models

> Reply from shakotay2 ↑Sat Feb 19, 2022 2:24 am at Sat Feb 19, 2022 2:24 am
>
> 
Use 20E0 as start_of_vertices and 24 for uv pos (offset).
Thank you!
## Post #11
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-20T06:09:51+00:00
- Post Title: Tian Xia 3 models

Finally after 178 iterations found a creature mesh and his texture  , the two things that change are the FVF size and UV post, the other values are repetitive. 
postdata: thanks shakotay
## Post #12
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-20T16:56:53+00:00
- Post Title: Tian Xia 3 models

Hello! if someone is interesting in this game and can make a script for this gonna be really helpfull! I'm attaching samples with the hex2obj values, literally the FVB size and UV post are the values that can change in some submeshes of the same file (head or weapon), also the uv position should be mirror to Y axis, I do this step manually after export as .obj.  . Thanks!

[https://www.mediafire.com/file/j8dfhaqa ... h.zip/file](https://www.mediafire.com/file/j8dfhaqab5vidou/samples_with_hex2obj_values_of_each_submesh.zip/file)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-20T18:26:36+00:00
- Post Title: Tian Xia 3 models

> Reply from moonpaladin ↑Mon Feb 21, 2022 12:56 am at Mon Feb 21, 2022 12:56 am
>
> 
Hello! if someone is interesting in this game and can make a script for this gonna be really helpfull!Guess you're ready to write your own scripts, aren't you?  

Noesis script template to be found here:

> Reply from shakotay2 ↑Sat Oct 06, 2018 3:05 pm at Sat Oct 06, 2018 3:05 pm
>
> 
Needs changes, of course, to work withTian Xia 3.
(Instead of VertBuf, noesis.RPGEODATA_USHORT use VertBuf, noesis.RPGEODATA_FLOAT, uvs use floats, too, and other changes required.
 The '6' is valid for USHORT only.)

Counts for eNiBlist-type are here:
.



eNiBlist.png (26.81 KiB) Viewed 152 times
## Post #14
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-20T18:34:09+00:00
- Post Title: Tian Xia 3 models

> Reply from shakotay2 ↑Mon Feb 21, 2022 2:26 am at Mon Feb 21, 2022 2:26 am
>
> 
Noesis script template to be found here:
Thanks shakotay2, gonna give it a try, do you have that sample file from JX3 HD? I wanna compare them
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-20T18:44:55+00:00
- Post Title: Tian Xia 3 models

Well, you're the lucky one   (found it on my old HD) - updated the concerning JX3 post.
## Post #16
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-20T19:47:43+00:00
- Post Title: Re: Tian Xia 3 models

i made lugin for Noesis



sample.mesh.png (26.28 KiB) Viewed 22 times


[link plugin](https://vladikdurik256.wixsite.com/plugins/product-page/tian-xia-3-pc)
## Post #17
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-20T20:38:28+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Mon Feb 21, 2022 3:47 am at Mon Feb 21, 2022 3:47 am
>
> 
start simple.

```
	bs = NoeBitStream(data)
	file = bs.readUInt()

	if file == 0x42A14E65:
		return 1
	else:
		return 0

```


This part of code check my file (0x654EA142), dunno why it should be at inverse in the function
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-20T20:47:38+00:00
- Post Title: Re: Tian Xia 3 models

Little endian data definition: a value of 0x1234ABCD for example is CDAB3412 in the file(s). Don't ask me why, accept it.  
(In big endian formats the value would be stored as 1234ABCD, surprise. High word (1234), then low word (ABCD) so humans can read it without headaches  .) If they know hex.
## Post #19
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-20T21:16:10+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from shakotay2 ↑Mon Feb 21, 2022 4:47 am at Mon Feb 21, 2022 4:47 am
>
> 

```
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    
    
    #rapi.rpgClearBufferBinds()
    bs.seek(0x20DC, NOESEEK_ABS)
    vertsCount = bs.readUInt()
    faceCount = bs.readUInt()
    bs.seek(0x44, NOESEEK_ABS)
    uvAddr = bs.readUInt()
    uvAddr += 12
    bs.seek(0xB4, NOESEEK_ABS)
    FIaddr = bs.readUInt()

    bs.seek(0x12C, NOESEEK_ABS)
    VertBuf = bs.readBytes(vertsCount * 12)
    bs.seek(uvAddr, NOESEEK_ABS)
    uv1Buf = bs.readBytes(vertsCount * 8)
    bs.seek(FIaddr, NOESEEK_ABS)
    idxBuf = bs.readBytes(faceCount * 12)
    
    
    rapi.rpgBindPositionBufferOfs(VertBuf, noesis.RPGEODATA_FLOAT, 12, 0)
    rapi.rpgBindUV1Buffer(uv1Buf, noesis.RPGEODATA_FLOAT, 12)
    rapi.rpgCommitTriangles(idxBuf, noesis.RPGEODATA_UINT, faceCount*3, noesis.RPGEO_TRIANGLE, 1)

    mdl = rapi.rpgConstructModel()
    mdlList.append(mdl)

    return 1
    
```


Still trying to understand what is bs.seek  and the rpgCommitTriangles
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-20T22:16:41+00:00
- Post Title: Re: Tian Xia 3 models

Long way to go - google for python seek()

Noesis functions to be found in pluginshare.h (see pluginsource.zip)
void	(*rpgCommitTriangles)(void *idxData, rpgeoDataType_e dataType, int numIdx, rpgeoPrimType_e primType, bool usePlotMap);

It's to understand the parameters only - keep in mind that .h is a C header file.
(Dunno whether there's a commented Noesis python functions parameter list, but the above should do.)
## Post #21
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-21T01:30:04+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from moonpaladin ↑Mon Feb 21, 2022 5:16 am at Mon Feb 21, 2022 5:16 am
>
> 
Still trying to understand what is bs.seek  and the rpgCommitTriangles
"bs" - NoeBitStream()
"seek" - sets the position within the current stream.
(NOESEEK_REL-from current position and NOESEEK_ABS- from the beginning of the file)
"rpgCommitTriangles" collects faces from bytes (args=bytes for index buffer, dataType, numIdx, primType)

in files (00000726.dat) and (000000000000c4fe.dat) have swapped vertices with faces.
using the (iSize and vSize) it can be easily solved.
## Post #22
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-21T02:18:30+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Mon Feb 21, 2022 9:30 am at Mon Feb 21, 2022 9:30 am
>
> 
"seek" - sets the position within the current stream.
Yep! but is the position I have been using in the hex2obj is slighty different so need to know why I need to use different values there, gonna review your script.

> Reply from Durik256 ↑Mon Feb 21, 2022 9:30 am at Mon Feb 21, 2022 9:30 am
>
> 
in files (00000726.dat) and (000000000000c4fe.dat) have swapped vertices with faces.
using the (iSize and vSize) it can be easily solved.
Yep I was worried for it too, but seems that for someone skilled doing scripts is a very easy xD, thanks for it, gonna learn the basis with this script, I know these models are basic because it have a very easy pattern.  Again thanks and sorry for so many requests.
## Post #23
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-21T03:17:51+00:00
- Post Title: Re: Tian Xia 3 models

There is a nice tutorial on how to make a noesis script describing this exact thing in my server. You must of left it.
## Post #24
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-21T03:21:15+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Mon Feb 21, 2022 9:30 am at Mon Feb 21, 2022 9:30 am
>
> 
Well there is much to learn

```
    bs = NoeBitStream(data)
    if bs.readInt64() != 8391166444416618085:
        return 0
    return 1
```


At least are some values that I'm understanding like these one
eN¡Blist :  7473696C42A14E65 = 8391166444416618085

The other value that I'm not sure is :

```
 bs.seek(16, NOESEEK_REL)
```

According about your descripction (current position) should be this?


and how about the 

```
bs.seek(64, NOESEEK_REL)
```

and

```
bs.seek(4)
```


So in order that the script load the other type of mesh , I need to change the noepyCheckType to it can load the other type of .dat file and change that iSize and vSize, is listed in the script but is not being used yet
## Post #25
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-21T03:25:37+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Sharppy ↑Mon Feb 21, 2022 11:17 am at Mon Feb 21, 2022 11:17 am
>
> 
There is a nice tutorial on how to make a noesis script describing this exact thing in my server. You must of left it.

Good to know , I was checking the chrrox tutorial
## Post #26
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-21T04:26:24+00:00
- Post Title: Re: Tian Xia 3 models

Well is really weird I'm getting around four different types of errors xD, and this meshes have same pattern, I tried to tweak the script a bit to it not thrown error but still getting errors, or is my noesis? I had this kind of "C error" time ago :salty:

[https://www.mediafire.com/file/ofnw5r2b ... 2.zip/file](https://www.mediafire.com/file/ofnw5r2bnf5vixk/samples_20-02-2022.zip/file)
## Post #27
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-21T08:47:13+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from moonpaladin ↑Mon Feb 21, 2022 10:18 am at Mon Feb 21, 2022 10:18 am
>
> 
the position I have been using in the hex2obj is slighty different
position is the same. 

> Reply from moonpaladin ↑Mon Feb 21, 2022 10:18 am at Mon Feb 21, 2022 10:18 am
>
> 
models are basic because it have a very easy pattern.
not so simple. 

> Reply from moonpaladin ↑Mon Feb 21, 2022 11:21 am at Mon Feb 21, 2022 11:21 am
>
> 
At least are some values that I'm understanding like these one
eN¡Blist :  7473696C42A14E65 = 8391166444416618085

"def noepyCheckType(data):" and "def noepyLoadModel(data, mdlList):"
two different methods that noesis calls in turn.
the first one is to check the file the second one is to load the model.
in each of them a new thread is assigned "bs = NoeBitStream(data)".
so the position starts from the beginning of in every new stream.

in general, the header in the file is:(eNЎB)
but since there are inverted files i check the first 8 bytes(eNЎBlist) by reading the integer64 value.

use debug. eg: print(bs.getOffset()). will print the current position.
## Post #28
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-21T12:41:23+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from moonpaladin ↑Mon Feb 21, 2022 12:26 pm at Mon Feb 21, 2022 12:26 pm
>
> 
i tried to tweak the script a bit to it not thrown error
what did yout ried to tweak there?  
I'm already annoyed by these "broken" files  
(there may be extra null bytes in the same places. Because of this, checks have to be made.)

one of the problems solved:
At the end of the file, information is not only about faces and vertices, there may also be materials.
(indentation is now used using (iSize и vSize) 

(you need to immediately do a normal unpacker so that you don’t suffer with models later)
## Post #29
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-21T13:53:26+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Mon Feb 21, 2022 4:47 pm at Mon Feb 21, 2022 4:47 pm
>
> 
use debug. eg: print(bs.getOffset()). will print the current position.
This one is really helpfull! xD

> Reply from Durik256 ↑Mon Feb 21, 2022 4:47 pm at Mon Feb 21, 2022 4:47 pm
>
> 
I'm already annoyed by these "broken" file
I get it, I don't want to see these .dat files again for a while  

> Reply from Durik256 ↑Mon Feb 21, 2022 4:47 pm at Mon Feb 21, 2022 4:47 pm
>
> 
(indentation is now used using (iSize и vSize)
Thank you Durik!
## Post #30
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-21T13:54:13+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from moonpaladin ↑Mon Feb 21, 2022 10:18 am at Mon Feb 21, 2022 10:18 am
>
> 
in files (00000726.dat) and (000000000000c4fe.dat) have swapped vertices with faces.
final  , support swapped model.
(I did not bother, I just duplicated the reading of faces and vertices and swapped them.)



sample.mesh.png (28.28 KiB) Viewed 17 times


Old plugin : [fmt_TianXia3.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_TianXia3.py)

Update plugin (open all model), (click up arrow)

> Reply from Durik256 ↑Mon Feb 21, 2022 3:47 am at Mon Feb 21, 2022 3:47 am
>
> 
fmt_TianXia3.py
## Post #31
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-21T14:28:10+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Mon Feb 21, 2022 9:54 pm at Mon Feb 21, 2022 9:54 pm
>
> 
(I did not bother, I just duplicated the reading of faces and vertices and swapped them.)
haha believe me or not, I tried to duplicate the function xd
## Post #32
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-21T16:09:25+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Mon Feb 21, 2022 9:54 pm at Mon Feb 21, 2022 9:54 pm
>
> 
Hello Durik! could you reupload the script please? I don't know what I move that some meshes looks broken and it doesn't show anything in the log, have doubts   

[https://www.mediafire.com/file/m3ff2tvl ... 2.zip/file](https://www.mediafire.com/file/m3ff2tvlxjcjtp4/samples_21-02-2022.zip/file)
## Post #33
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-21T16:36:20+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from moonpaladin ↑Tue Feb 22, 2022 12:09 am at Tue Feb 22, 2022 12:09 am
>
> 
some meshes looks broken
I have the same
## Post #34
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-21T16:38:32+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Tue Feb 22, 2022 12:36 am at Tue Feb 22, 2022 12:36 am
>
> 
I have the same
oh well, maybe are broken meshes after unpacking
## Post #35
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-21T16:45:34+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Mon Feb 21, 2022 3:47 am at Mon Feb 21, 2022 3:47 am
>
> 
 try to make a plugin for this model.
if you don't do it. then I post the solution.
## Post #36
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-21T16:48:28+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Tue Feb 22, 2022 12:45 am at Tue Feb 22, 2022 12:45 am
>
> 
 try to make a plugin for this model.
XD! I were inspecting shakotay script first, sorry
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-21T20:03:37+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from moonpaladin ↑Tue Feb 22, 2022 12:48 am at Tue Feb 22, 2022 12:48 am
>
> 
Durik256 wrote: ↑Tue Feb 22, 2022 12:45 am
 try to make a plugin for this model. 

XD! I were inspecting shakotay script first, sorrythat was meant as a "template" only. Seems Durik did more investigations on Tian Xia 3 models than me so it would be safe to follow him.  

btw, great, that you try scripting. One way would be to use Duriks script to understand the basic, understand each line of it.
You're on a good way!
## Post #38
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-22T14:55:01+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Tue Feb 22, 2022 12:45 am at Tue Feb 22, 2022 12:45 am
>
> 
Hello Durik! could you please post your noesis script?
## Post #39
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-22T19:33:47+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from moonpaladin ↑Tue Feb 22, 2022 10:55 pm at Tue Feb 22, 2022 10:55 pm
>
> 
post your noesis script?
already post
## Post #40
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-22T20:00:11+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from Durik256 ↑Mon Feb 21, 2022 9:54 pm at Mon Feb 21, 2022 9:54 pm
>
> 
final  , support swapped model.
I was talking about this script xD! don't play with my feelings
## Post #41
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-04T00:35:26+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from moonpaladin ↑Tue Feb 15, 2022 10:53 pm at Tue Feb 15, 2022 10:53 pm
>
> 

hi
I've also played this game. I have an older version of the client
## Post #42
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-04T09:43:12+00:00
- Post Title: Re: Tian Xia 3 models

> Reply from ptg1121 ↑Fri Mar 04, 2022 8:35 am at Fri Mar 04, 2022 8:35 am
>
>  
I've also played this game. I have an older version of the client
Hello! That is really COOL you have the game unpacked? With their filenames?
