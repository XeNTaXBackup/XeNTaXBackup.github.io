## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2023-03-08T23:51:15+00:00
- Post Title: Star Ocean: The Divine Force Tool

Tool for viewing/extracting models from the PC/PS4 version of the game. The main focus is on character and monster models. Supports meshes, textures, skeleton, and skinning.

Tool overview



How to use

Extract

Files are packed in CPK  archives. I use this for extracting [YACpkTool](https://github.com/Brolijah/YACpkTool), but there are many programs available that can get the job done. After that, you can find the ASF  models in appropriate folders.

Note : The tool is able to load the original ASF  files directly. There is no need for manual decryption/decompression and it is not recommended.

Load

ASF : Loads a single model file (.asf).
Force Bind Pose: This is enabled by default. The skeleton is not stored in bind pose for most models. However, the tool will try to set it to bind pose when this option is enabled. This should be desirable in most situations.
Export

NUX: Exports the model in custom binary format (.nux), intended to be loaded by Noesis. Noesis script for this format : NUX Script
Textures: Textures will be exported as PNG.
Note  : Models and textures will be exported into the folder Export.
Download : [https://www.mediafire.com/file/crz9f611 ... 1.zip/file](https://www.mediafire.com/file/crz9f611szy6uw0/SO6Viewer_U1.zip/file)

Example exported model
## Post #2
- Username: sonicocel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 09, 2023 5:40 pm
- Post datetime: 2023-03-11T17:51:37+00:00
- Post Title: Star Ocean: The Divine Force Tool

looks superb, looking forward for ur progress
## Post #3
- Username: foulveins
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 7:19 am
- Post datetime: 2023-03-12T02:40:36+00:00
- Post Title: Star Ocean: The Divine Force Tool

if you still need pc files, here's a sample i uploaded way back in november to the xentax discord: [https://cdn.discordapp.com/attachments/ ... 101_02.asf](https://cdn.discordapp.com/attachments/493153303551541258/1037481672595218492/ch_p101_02.asf)
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2023-03-13T22:56:48+00:00
- Post Title: Star Ocean: The Divine Force Tool

The tool is released along with instructions on how to use it. You can check out the first post.

> Reply from foulveins ↑Sun Mar 12, 2023 10:40 am at Sun Mar 12, 2023 10:40 am
>
> 
here's a sample i uploaded

Thanks for the sample. It seems to load fine without issues.
## Post #5
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-03-14T01:40:29+00:00
- Post Title: Star Ocean: The Divine Force Tool

Doesn't seem to be working for all the files, this one from both PC and PS4 has the UV all jumbled (is not the only one like that) and I'm not sure if the noesis script is supposed to load the textures too but is not doing it, I'm using Noesis 4.466 btw which I think is the latest, and the nux script from this thread, some meshes show up with body parts in weird places or deformed inside the viewer, also when exporting from noesis to another format it mixes all the surfaces into a single one regardless of the format chosen (fbx, obj, etc.):




sodf.jpg (124.07 KiB) Viewed 571 times



sample of the same file from both PS4 and PC here:

[https://mega.nz/folder/gK4QGIba#Q88SsqMIjVQpjGbCBO7VhQ](https://mega.nz/folder/gK4QGIba#Q88SsqMIjVQpjGbCBO7VhQ)
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2023-03-14T09:39:08+00:00
- Post Title: Star Ocean: The Divine Force Tool

> Reply from GDL ↑Tue Mar 14, 2023 9:40 am at Tue Mar 14, 2023 9:40 am
>
> 
this one from both PC and PS4 has the UV all jumbled

Thanks for the samples. UVs are a bit tricky. I updated the tool to improve UV support. Also updated the download link in the first post. "ch_p004_01" looks fine now, but "ch_p000_07" doesn't seem to have any UV data at all inside the vertex buffer. I don't know what the deal is with that model, but UVs won't work.

> Reply from GDL ↑Tue Mar 14, 2023 9:40 am at Tue Mar 14, 2023 9:40 am
>
> 
I'm not sure if the noesis script is supposed to load the textures too

Nope, that is not supported. I haven't worked on material mappings.

> Reply from GDL ↑Tue Mar 14, 2023 9:40 am at Tue Mar 14, 2023 9:40 am
>
> 
some meshes show up with body parts in weird places or deformed inside the viewer,

Most likely because of bind pose not being applied properly. Hopefully, the skinning should still be correct so it can be fixed manually by rotating the bones inside a 3D software. I don't have an easy fix for this atm.

> Reply from GDL ↑Tue Mar 14, 2023 9:40 am at Tue Mar 14, 2023 9:40 am
>
> 
when exporting from noesis to another format it mixes all the surfaces into a single one

That seems to be because all the meshes had the same material reference. The updated tool should fix that too.
## Post #7
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-03-14T22:07:24+00:00
- Post Title: Star Ocean: The Divine Force Tool

> Reply from akderebur ↑Tue Mar 14, 2023 5:39 pm at Tue Mar 14, 2023 5:39 pm
>
> 
but "ch_p000_07" doesn't seem to have any UV data at all inside the vertex buffer. I don't know what the deal is with that model, but UVs won't work.

Well, the uv seems to work, kind of, check this out:




uv.jpg (225.76 KiB) Viewed 484 times



apparently the uv is segmented and it doesn't match the texture associated with it, in this case the "body" part, looks like the uv is misaligned, almost like is swizzled/rotated but not quite, to me it looks like it was cut into smaller segments for some reason and the tool is exporting those pieces in weird places, in this picture you can see where it should align with the texture but the uv is offset to the center, also, I noticed that the uv is stretched or resized as the pieces don't quite align manually with eachother or with the texture when I tried to reconstruct it with another program.
## Post #8
- Username: BiteMeUniverse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 19, 2018 8:59 am
- Post datetime: 2023-03-15T08:22:20+00:00
- Post Title: Star Ocean: The Divine Force Tool

you are a 4D Being!
## Post #9
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-15T18:13:51+00:00
- Post Title: Star Ocean: The Divine Force Tool

First of all, THANK YOU for this tool!

However, it looks like some of the normals aren't getting extracted properly:



I had this issue with the SOA normals extracted with SOAImgEx, but was able to get a script written to properly decompress the KTX files with PVRTexTool. Since these extract straight to PNG, though, there is no way to fix them.

I can send you the script through DM if you think it would be helpful.
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2023-03-15T19:27:52+00:00
- Post Title: Star Ocean: The Divine Force Tool

> Reply from Mihna ↑Thu Mar 16, 2023 2:13 am at Thu Mar 16, 2023 2:13 am
>
> 
Since these extract straight to PNG, though, there is no way to fix them.
The same procedure should apply for unpacking. I have attached a small program to do that. Just drag and drop the PNG file on the exe.
[NMUnpCLI.zip](https://xentaxbackup.github.io/file/23561_NMUnpCLI.zip)
## Post #11
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-16T19:52:34+00:00
- Post Title: Star Ocean: The Divine Force Tool

> Reply from akderebur ↑Thu Mar 16, 2023 3:27 am at Thu Mar 16, 2023 3:27 am
>
> 
The same procedure should apply for unpacking. I have attached a small program to do that. Just drag and drop the PNG file on the exe.

Ahh, perfect, thank you!!

I'm having one other issue: Some of the hair textures (so far it's been only blond ones) are extracting as blue:



What it should look like:



Inverting it gets me closer, but it's still not quite right.
## Post #12
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-21T18:24:35+00:00
- Post Title: Star Ocean: The Divine Force Tool

It's actually doing the same thing with blue hair textures too—Marielle's comes out blonde. And again, inverting doesn't make it correct.
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2023-03-21T19:59:57+00:00
- Post Title: Star Ocean: The Divine Force Tool

> Reply from Mihna ↑Wed Mar 22, 2023 2:24 am at Wed Mar 22, 2023 2:24 am
>
> 
It's actually doing the same thing with blue hair textures too—Marielle's comes out blonde. And again, inverting doesn't make it correct.

I don't think they are supposed to have colors anyway. Tri-ace has been using custom shaders for hair for some time. Anamnesis didn't have any hair color textures either. It is probably a similar case with SO6.
## Post #14
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2023-03-21T23:17:43+00:00
- Post Title: Star Ocean: The Divine Force Tool

I don't know about this game as I don't have the files, but akderebur is right, the hair color was not correct as of SOA,
I think Tri-ace is coloring it with shaders etc.
If you want to get a closer color, convert to monochrome and adjust the hue or layer the colors yourself to get closer to the correct color.
## Post #15
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-22T10:17:08+00:00
- Post Title: Star Ocean: The Divine Force Tool

> Reply from akderebur ↑Wed Mar 22, 2023 3:59 am at Wed Mar 22, 2023 3:59 am
>
> 
I don't think they are supposed to have colors anyway. Tri-ace has been using custom shaders for hair for some time. Anamnesis didn't have any hair color textures either. It is probably a similar case with SO6.

Well, some of them do have (correct) colors—it's just some of the blonde and blue ones that are not extracting correctly. I can edit them, I just wanted to make sure it wasn't a problem with the extraction tool.
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2023-03-22T10:35:15+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

> Reply from Mihna ↑Wed Mar 22, 2023 6:17 pm at Wed Mar 22, 2023 6:17 pm
>
> 
I can edit them, I just wanted to make sure it wasn't a problem with the extraction tool.

I see. It is very unlikely that the textures are exported incorrectly in terms of color channels. If it looks like complete nonsense then it is probably a texture type I haven't encountered and is wrongly exported. However, if the texture looks somewhat ok then it is most likely correct and that is how the texture is actually used in-game.
## Post #17
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-22T14:56:14+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

Example: Theo's hair diffuse is red and extracted normally. This issue is ONLY happening with blonde/light brown and blue hair diffuse textures.
## Post #18
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-22T15:10:38+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

> Reply from akderebur ↑Wed Mar 22, 2023 6:35 pm at Wed Mar 22, 2023 6:35 pm
>
> 
I see. It is very unlikely that the textures are exported incorrectly in terms of color channels. If it looks like complete nonsense then it is probably a texture type I haven't encountered and is wrongly exported. However, if the texture looks somewhat ok then it is most likely correct and that is how the texture is actually used in-game.

That's so weird... I've tried messing around with channels and inverting, but so far I haven't been able to figure out how to get it correct. If this is how they show up in game, I feel like there SHOULD be a solution. I'll keep poking at them.
## Post #19
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-24T15:15:51+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

Yeah I'm COMPLETELY lost. I was going to try looking at the files in RawTex, but I can't do that since there's no tool to decompress the files and I can't figure that out on my own, so I'll just photoshop the ones that come out wrong.

I've had another issue pop up, this time with one of Malkya's UVs:





Is this a glitch with the extraction tool? The rest of her UVs are fine (and I haven't run into this issue on any other models so far), it's just the UVs that go with this material. The Lightmap UV is identical to the Diffuse UV, so that's not the problem.
## Post #20
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-03-24T16:01:30+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

That model seems to have a separate file with uv modifications, usually they do that if the uv is animated for some sort of special effect or something similar.
## Post #21
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-24T17:08:44+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

> Reply from GDL ↑Sat Mar 25, 2023 12:01 am at Sat Mar 25, 2023 12:01 am
>
> 
That model seems to have a separate file with uv modifications, usually they do that if the uv is animated for some sort of special effect or something similar.

Ohh interesting, I hadn’t seen that before but that makes a lot of sense—this is where the sparkly parts on her body are.
## Post #22
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-24T17:46:34+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

> Reply from GDL ↑Sat Mar 25, 2023 12:01 am at Sat Mar 25, 2023 12:01 am
>
> 
That model seems to have a separate file with uv modifications, usually they do that if the uv is animated for some sort of special effect or something similar.

Do you know which file it's stored in? I've been doing some hunting, but haven't found it yet.
## Post #23
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2023-03-24T17:47:48+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

> Reply from GDL ↑Sat Mar 25, 2023 12:01 am at Sat Mar 25, 2023 12:01 am
>
> 
That model seems to have a separate file with uv modifications

I will try to look at them when I have the time. Probably over the next week.

> Reply from Mihna ↑Wed Mar 22, 2023 11:10 pm at Wed Mar 22, 2023 11:10 pm
>
> 
If this is how they show up in game, I feel like there SHOULD be a solution.

The texture Is used in a shader which also has other color inputs for stuff like base color, highlights, etc. That is why it ends up looking correct inside the game. So there is no way to get the correct output unless the shader is reverse-engineered too.
## Post #24
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-03-24T19:18:15+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

> Reply from akderebur ↑Sat Mar 25, 2023 1:47 am at Sat Mar 25, 2023 1:47 am
>
> 
I will try to look at them when I have the time. Probably over the next week.

Thank you! I appreciate all your hard work on this.

> Reply from akderebur ↑Sat Mar 25, 2023 1:47 am at Sat Mar 25, 2023 1:47 am
>
> 
The texture Is used in a shader which also has other color inputs for stuff like base color, highlights, etc. That is why it ends up looking correct inside the game. So there is no way to get the correct output unless the shader is reverse-engineered too.

That makes sense. It's just bizarre that they did this for only yellow and blue hair but not the rest. Maybe it had something to do with lighting... who knows. Photoshopping is good enough for me.
## Post #25
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2023-05-11T11:09:51+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

Where is the npc and character at in the  chunk files. what number to look from.
## Post #26
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2023-05-13T04:27:30+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

uh hello
## Post #27
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-05-13T06:29:52+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

> Reply from blacknight411 ↑Thu May 11, 2023 7:09 pm at Thu May 11, 2023 7:09 pm
>
> 
Where is the npc and character at in the  chunk files. what number to look from.

I've found most in chunk 0 and 1,the rest seem to be buildings and stuff
## Post #28
- Username: 4fantas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 06, 2023 3:30 am
- Post datetime: 2023-06-05T19:50:09+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

What is the process for unpacking textures separately from .asf files? (.aif)
I tried following process similar to what described from getting SOA textures but that didn't work
## Post #29
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-09-08T20:19:17+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

> Reply from akderebur ↑Sat Mar 25, 2023 1:47 am at Sat Mar 25, 2023 1:47 am
>
> 
I will try to look at them when I have the time. Probably over the next week.

Just checking to see if you were ever able to find a fix for this?
## Post #30
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2023-09-15T15:45:49+00:00
- Post Title: Re: Star Ocean: The Divine Force Tool

I did FINALLY figure out what was going on with the color-swapped textures: some of them have the red and blue channels swapped. Swapping them back fixed the issue.
