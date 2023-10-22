## Post #1
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2022-03-13T02:40:47+00:00
- Post Title: Ragnarok Web

Could anyone help reverse engineer these files?
I've seen games that use this extension, but I've tested some scripts and without success.

The game currently uses adobe flash, so I downloaded the assets, but I need help to be able to import  

Unfortunately my graphics knowledge is almost nil, I would love to be able to use these files in a Unity 3D project. 

Game: [https://roweb2.gnjoy.com.tw/](https://roweb2.gnjoy.com.tw/)
Files: [https://drive.google.com/file/d/1Jaf0XY ... sp=sharing](https://drive.google.com/file/d/1Jaf0XY0F6YpeEMHyGot2FYrjLOxioF-K/view?usp=sharing)

Cheers.
## Post #2
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-13T05:15:16+00:00
- Post Title: Ragnarok Web

> Reply from ilovechii ↑Sun Mar 13, 2022 10:40 am at Sun Mar 13, 2022 10:40 am
>
> 
Hello ilovechii!, well for atf textures, you can use this tool : [https://vamapaull.com/atf-to-png-converter-tool/](https://vamapaull.com/atf-to-png-converter-tool/)
for those .p3d files, seems compressed, I have used offzip to get this .x3p file : [https://www.mediafire.com/file/t84any1m ... n.xp3/file](https://www.mediafire.com/file/t84any1m44yz9cf/baiyangzuonan.xp3/file), don't know if it is totally uncompressed but I can see some info about bones, vertices and faces. good luck!
## Post #3
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2022-03-13T13:27:08+00:00
- Post Title: Ragnarok Web

> Reply from moonpaladin ↑Sun Mar 13, 2022 1:15 pm at Sun Mar 13, 2022 1:15 pm
>
> 
ilovechii wrote: ↑Sun Mar 13, 2022 10:40 am

Hello ilovechii!, well for atf textures, you can use this tool : https://vamapaull.com/atf-to-png-converter-tool/
for those .p3d files, seems compressed, I have used offzip to get this .x3p file : https://www.mediafire.com/file/t84any1m ... n.xp3/file, don't know if it is totally uncompressed but I can see some info about bones, vertices and faces. good luck!

Thanks for answering!

Regarding the P3D file, it seems to be really compressed, but now in the XP3 format is there any tool that maybe it can read?
## Post #4
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2022-03-15T22:24:38+00:00
- Post Title: Ragnarok Web

Bump.
## Post #5
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2022-03-16T05:16:15+00:00
- Post Title: Ragnarok Web

Apparently it's compressed + AML. 

I've tried some AML libs to try to do the reading, but to no avail.
## Post #6
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2022-03-16T14:39:12+00:00
- Post Title: Ragnarok Web

```
{"Trait":{"ClassName":"","IsAnonymous":true,"IsDynamic":true,"IsExternalizable":false,"Members":[]},"Values":[],"DynamicMembersAndValues":{"bolimao":{"Trait":{"ClassName":"","IsAnonymous":true,"IsDynamic":true,"IsExternalizable":false,"Members":[]},"Values":[],"DynamicMembersAndValues":{"type":0,"meshes":{"Trait":{"ClassName":"","IsAnonymous":true,"IsDynamic":true,"IsExternalizable":false,"Members":[]},"Values":[],"DynamicMembersAndValues":{"$def":{"Trait":{"ClassName":"","IsAnonymous":true,"IsDynamic":true,"IsExternalizable":false,"Members":[]},"Values":[],"DynamicMembersAndValues":{"surfaces":{"StrictDense":[{"Trait":{"ClassName":"","IsAnonymous":true,"IsDynamic":true,"IsExternalizable":false,"Members":[]},"Values":[],"DynamicMembersAndValues":{"ibegin":0,"icount":480}}],"SparseAssociative":{}},"renderedBoneArray":{"StrictDense":["Bone0001"],"SparseAssociative":{}},"index":"AAABAAIAAwAEAAUAAwAFAAYAAwAGAAcAAwAHAAgAAAAJAAoACgALAAwACgAMAA0ADgAKAA0ADwAOAA0AEAARABIAEAASABMAEwAFABAABQATABQAFAAGAAUABgAUABUAFQAHAAYABwAVABYAFgAIAAcACAAWABcAGAAJABkACgAJABgACgAYABoACgAaAAsACwAbABwAHAAMAAsADAAcAB0AHQANAAwADQAdAB4AHgAPAA0AEQAfACAAIAASABEAEgAgACEAIQATABIAEwAhACIAIgAUABMAFAAiACMAIwAVABQAFQAjACQAJAAWABUAFgAkACUAJQAmABYAGQAnACgAKAAYABkAGAAoACkAKQAaABgAGgApACoAKgALABoAKgArACwALAAcACoAHAAsAC0ALQAdABwAHQAtAC4ALgAeAB0ALwAwADEAMQAgAC8AIAAxADIAMgAhACAAIQAyADMAMwAiACEAIgAzADQANAA1ACIANQA0ADYANgA3ADUANwA2ADgAOAA5ADcAOgA7ADwAPAAoADoAKAA8AD0APQApACgAKQA9ACsAKwAqACkAKwA+AD8APwAsACsALAA/AEAAQAAtACwALQBAAEEAQQAuAC0AMABCAEMAQwAxADAAMQBDAEQARAAyADEAMgBEAEUARQAzADIAMwBFAEYARgA0ADMANABGAEcARwA2ADQANgBHAEgASAA4ADYASQBKAEsASwA8AEkAPABLAEwATAA9ADwAPQBMAD4APgArAD0AXABdAF4AXABeAF8AYABhAGIAYABiAGMAYABjAGQAYABkAGUAXABmAGcAXABnAGgAaQBqAGgAaABrAGkAbABtAGoAagBpAGwAbgBiAGEAYQBvAG4AcABjAGIAYgBuAHAAcQBkAGMAYwBwAHEAcgBzAGQAZABxAHIAdABnAGYAZgB1AHQAawBoAGcAZwB0AGsAdgBpAGsAawB3AHYAeABsAGkAaQB2AHgAeQBuAG8AbwB6AHkAewBwAG4AbgB5AHsAfABxAHAAcAB7AHwAfQByAHEAcQB8AH0AfgB0AHUAdQB/AH4AdwBrAHQAdAB+AHcAgAB2AHcAgAB4AHYAgQB5AHoAgQB7AHkAgQB8AHsAgQB9AHwAgAB+AH8AgAB3AH4ATQBOAE8ATwBQAE0AUQBSAFMAUwBUAFEAUgBVAFYAVgBTAFIAVQBNAFAAUABWAFUAVwBYAFAAUABPAFcAWQBaAFQAVABTAFkAWwBZAFMAUwBWAFsAWABbAFYAVgBQAFgA","numVertices":130,"attrib":{"Trait":{"ClassName":"","IsAnonymous":true,"IsDynamic":true,"IsExternalizable":false,"Members":[]},"Values":[],"DynamicMembersAndValues":{"Position/Texcoord1/BoneIndex/BoneWeight":"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"}}}}}},"skin":{"Trait":{"ClassName":"","IsAnonymous":true,"IsDynamic":true,"IsExternalizable":false,"Members":[]},"Values":[],"DynamicMembersAndValues":{"Particle View 01":{"Trait":{"ClassName":"","IsAnonymous":true,"IsDynamic":true,"IsExternalizable":false,"Members":[]},"Values":[],"DynamicMembersAndValues":{"s":[1.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,1.0],"m":[1.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,1.0],"p":null}},"Bone0001":{"Trait":{"ClassName":"","IsAnonymous":true,"IsDynamic":true,"IsExternalizable":false,"Members":[]},"Values":[],"DynamicMembersAndValues":{"s":[1.0,-4.65714744546375E-10,-5.551752383069694E-17,0.0,4.65714744546375E-10,1.0,1.1920928955078125E-07,0.0,0.0,-1.1920928955078125E-07,1.0,0.0,-0.0,-0.0,-0.0,1.0],"m":[1.0,4.65714744546375E-10,0.0,0.0,-4.65714744546375E-10,1.0,-1.1920928955078125E-07,0.0,-5.551752383069694E-17,1.1920928955078125E-07,1.0,0.0,0.0,0.0,0.0,1.0],"p":null}}}},"name":"bolimao"}}}}
```


i managed to get the data from the file, i converted to json, the problem now is to perform the magic for converting to 3d.
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-16T22:28:16+00:00
- Post Title: Ragnarok Web

> Reply from ilovechii ↑Sun Mar 13, 2022 10:40 am at Sun Mar 13, 2022 10:40 am
>
> 
I have used offzip to get this .x3p



baiyangzuonan.xp3.png (62.75 KiB) Viewed 310 times
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-17T02:41:53+00:00
- Post Title: Ragnarok Web

> Reply from ilovechii ↑Wed Mar 16, 2022 10:39 pm at Wed Mar 16, 2022 10:39 pm
>
> 
i converted to json
how did you do it? you have correct index and vertex values.
I made a plugin with "crutches"(edit: not relevant)

for those in the know:
how to find out 'destination size' for decompressed in Noesis?
## Post #9
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2022-03-17T03:16:33+00:00
- Post Title: Ragnarok Web

Wow, what progress! Thank you! 

About my values, I just read the serialization of the files in AMF and just converted to json naturally. This is the lib I used for reading and the function called. 

Link: [https://github.com/mtanksl/amf.net/blob ... er.cs#L395](https://github.com/mtanksl/amf.net/blob/b52e40b0c458d057e85855eac034d8e46c263d2d/mtanksl.ActionMessageFormat/Serialization/AmfReader.cs#L395)
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-17T17:13:49+00:00
- Post Title: Ragnarok Web

> Reply from ilovechii ↑Thu Mar 17, 2022 11:16 am at Thu Mar 17, 2022 11:16 am
>
> 
i converted to json, the problem now is to perform the magic for converting to 3d.
use 'b64decode()' for data conversion.

> Reply from ilovechii ↑Thu Mar 17, 2022 11:16 am at Thu Mar 17, 2022 11:16 am
>
> 
Link: https://github.com/...
borrowed the amf3 integer reading method 'ReadAmf3UInt29()' and converted to python.
(now I can read the number of indexes and vertices.)
## Post #11
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2022-03-17T17:38:59+00:00
- Post Title: Ragnarok Web

Hey Durik256,
thanks again for the progress with the script!

There was a problem with some models, they gave an error to read and some models may have some reading error, the 3d is totally weird.
A question, in relation to rigged models, is it difficult to add?
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-17T17:53:37+00:00
- Post Title: Ragnarok Web

> Reply from ilovechii ↑Fri Mar 18, 2022 1:38 am at Fri Mar 18, 2022 1:38 am
>
> 
add rigged
you only need to add bones.
## Post #13
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-18T17:32:21+00:00
- Post Title: Ragnarok Web

> Reply from ilovechii ↑Fri Mar 18, 2022 1:38 am at Fri Mar 18, 2022 1:38 am
>
> 
some models may have the 3d is totally weird.
some models have a second uv channel('Texcoord2'). because of this, stride was calculated incorrectly.

> Reply from ilovechii ↑Fri Mar 18, 2022 1:38 am at Fri Mar 18, 2022 1:38 am
>
> 
ith some models, they gave an error.
some models gave an error due to incorrect "destination size" so the model was not fully unpacked.
(indicated 6 times more than the original file, with a margin.)
now exactly all models open:

[fmt_p3d.zip](https://xentaxbackup.github.io/file/21962_fmt_p3d.zip)
## Post #14
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2022-03-18T22:04:51+00:00
- Post Title: Ragnarok Web

Hey @Durik256,
Sorry I removed the quotes. xD

Thanks for further progress! Regarding the textures, are they loading automatically? Did you export (atf2png) or are you already reading the *.atf? I tested and the textures didn't load, maybe I'm doing something wrong.

Regarding bones, sorry, I'm really bad with 3d modeling, but I'll be trying in a way, because I still need to see how to read the animations.

Anyway, you are amazing and you helped a lot. )
## Post #15
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-19T19:46:42+00:00
- Post Title: Ragnarok Web

so, I  written *.json parsing.
loads all submeshes and bones. 
converter .p3d to .json and viewer tree [converter.zip](https://drive.google.com/file/d/1NfmRUnrzm6YcghvCLxdMiqaioA8V3BMU/view?usp=sharing).
(@ilovechii build windows form exe, library: [amf](https://github.com/liuyunxiong/rtmpsharp) and [json](https://www.newtonsoft.com/json) )

[fmt_p3d_json.zip](https://xentaxbackup.github.io/file/21984_fmt_p3d_json.zip)
## Post #16
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2022-03-19T19:53:39+00:00
- Post Title: Re: Ragnarok Web

wow, amazing!

could the problem be for some specific reason? as problem in parser?
## Post #17
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-21T22:12:06+00:00
- Post Title: Re: Ragnarok Web

using [amf3reader.py](https://github.com/gpeacock/telemetry-tools/blob/master/amf3reader.py).
i created Noesis plugin for *.p3d
(unpack, parsing amf3 e.t.c inside Noesis, no additional files needed)

(not all models have been tested. in case of error, use the previous .*json plugin, it opens 100% of all models)
[fmt_p3d.zip](https://xentaxbackup.github.io/file/21985_fmt_p3d.zip)
