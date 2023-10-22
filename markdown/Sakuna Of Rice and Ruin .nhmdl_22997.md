## Post #1
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-11-12T13:12:10+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

this new game "Sakuna Of Rice and Ruin" is made by Edelweiss , and edelweiss.bms can extract its .arc file for no problem but the models , textures and animations are come with ".nhanm" ".nhmdl" ".nhtex" which is a new extension never seen b4 , could someone please help?

[https://drive.google.com/file/d/10g67U4 ... sp=sharing](https://drive.google.com/file/d/10g67U4RRIsqoorfEqVJKpUWwqAy5s70G/view?usp=sharing)
## Post #2
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2020-11-24T23:26:52+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

There is wrong extraction. Looks like peaces of compressing data. You can use my tool for extract files
[https://github.com/LinkOFF7/sakunaTool](https://github.com/LinkOFF7/sakunaTool)
## Post #3
- Username: Habanero
- Rank: n00b
- Number of posts: 19
- Joined date: Thu May 02, 2019 2:36 am
- Post datetime: 2020-11-28T21:27:26+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

> Reply from LinkOFF ↑Wed Nov 25, 2020 7:26 am at Wed Nov 25, 2020 7:26 am
>
> 
There is wrong extraction. Looks like peaces of compressing data. You can use my tool for extract files
https://github.com/LinkOFF7/sakunaTool
Thanks. I tried your tool and it seems to extract the same files (nhmdl, nhtex, etc.), so I think I'm in the same boat as OP.
[https://mega.nz/folder/Y0ZyQZQK#xunysYE-_Hnhk7LlJvhICQ](https://mega.nz/folder/Y0ZyQZQK#xunysYE-_Hnhk7LlJvhICQ)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-11-29T12:15:49+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

No, you are not.  (Contents of extracted files is different. Same size, though.)
.



Sakuna_first_submesh.png (27.32 KiB) Viewed 457 times


Small submeshes, much fiddling required...
## Post #5
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-02-08T07:03:51+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

Hello, has there been any progress in a tool that can read nhmdl files?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-08T14:06:35+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

I don't know of any and I wouldn't expect one too soon. Too much trouble:
.



Sakura.png (34.67 KiB) Viewed 373 times


Too less contributors.
## Post #7
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-02-08T18:03:06+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

i see, thanks for replying. i guess the least i can do is wait, hopefully i or others find out something in the future.
## Post #8
- Username: Tekkamanchronos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 24, 2015 1:50 am
- Post datetime: 2022-03-01T01:04:52+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

I know it's been awhile but has anyone made any progress with the .nhmdl format or is this still dead in the water?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-03-01T12:28:56+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

dead like a dead fish in dead waters  
Thing is there's a problem with the face indices which I had no interest in fiddling around with, also mesh too low poly, etc.
## Post #10
- Username: Turk645
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2022 5:25 pm
- Post datetime: 2022-06-13T09:31:11+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

The file format is definitely a pain. The vertex format changes size depending on how many weights are on that one vertex. Vert data also gets split in half if the mesh is rigged or not. Mostly poking through trouble shooting different meshes. My code is a bit ass though. Also need to find the proper eye texture, what i have in that screenshot is a temp one for the sake of the screenshot 


Other than making sure it doesnt break on other misc models, i still need to make it read the material data for each mesh.
## Post #11
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2022-06-13T11:19:39+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

oh now this is a good thing to wake up to, cool to see some progress on getting assets from this game
## Post #12
- Username: Turk645
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2022 5:25 pm
- Post datetime: 2022-06-15T05:53:23+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

I think i got it good enough for an initial release. If you convert the textures to png first, it will try to auto apply the diffuse to the material on load. Textures are done via noesis, and meshes are done via blender. I'm still learning the noesis api so the mesh import isnt for that directly.

When testing, the mesh import seemed to work for both pc and switch but texture import only works on pc version.

[Github link](https://github.com/Turk645/Sakuna-of-rice-and-ruin-PC)
## Post #13
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2022-06-15T10:05:20+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

cheers dude, great work!
## Post #14
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-06-16T01:57:52+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

What do I need  to  make  this sakunaTools work. To extract its .arc
## Post #15
- Username: Turk645
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2022 5:25 pm
- Post datetime: 2022-06-16T06:29:39+00:00
- Post Title: Sakuna Of Rice and Ruin .nhmdl

> Reply from blacknight411 ↑Thu Jun 16, 2022 9:57 am at Thu Jun 16, 2022 9:57 am
>
> 
What do I need  to  make  this sakunaTools work. To extract its .arc

It's run through the command prompt. When you open the folder of the tool, in the address bar type cmd and hit enter. It will open a command prompt already pointing at that directory. Then its just a matter of typing the exe name, -e to tell it to extract, and then dragging and dropping the arc file you want into the window to auto fill the path to it. 

```
C:\path\to\sakunatool>sakunatool -e "path to .arc here"
```


This will cause the tool to make a folder with the extracted contents
## Post #16
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-06-16T07:04:22+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

Went you open the [https://github.com/LinkOFF7/sakunaTool](https://github.com/LinkOFF7/sakunaTool)  you have LZ4.dll and sakunaTool  is that correct.
## Post #17
- Username: Turk645
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2022 5:25 pm
- Post datetime: 2022-06-16T07:12:22+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

yup. those where the only two files i had in the folder when it was downloaded.
## Post #18
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-06-16T07:34:22+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

Ok  I have sakunaTool,LZ4.dll and Character_Pc_Sakuna02 and a file do I need anything else.
oh one more   thing  went I open the sakunaTool  it  do not open  it.
## Post #19
- Username: Turk645
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2022 5:25 pm
- Post datetime: 2022-06-16T07:49:29+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

> Reply from blacknight411 ↑Thu Jun 16, 2022 3:34 pm at Thu Jun 16, 2022 3:34 pm
>
> 
Ok  I have sakunaTool,LZ4.dll and Character_Pc_Sakuna02 and a file do I need anything else.

the character folder created by the tool will have the texture and model files
## Post #20
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-06-16T07:59:42+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

went I try to open the sakunaTool it appears and disappears went I click it.
## Post #21
- Username: Samchongsa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 20, 2021 3:13 am
- Post datetime: 2022-07-18T14:50:06+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

Sorry for the question, but i've tried to compile the tool and its telling me that the file "Utils.cs" is missing. But i cannot find said file anywhere inside the Github project LinkOFF posted ([https://github.com/LinkOFF7/sakunaTool](https://github.com/LinkOFF7/sakunaTool)). Thank you in advance for your help!
## Post #22
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2022-07-19T17:07:19+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

> Reply from Samchongsa ↑Mon Jul 18, 2022 10:50 pm at Mon Jul 18, 2022 10:50 pm
>
> 
Sorry for the question, but i've tried to compile the tool and its telling me that the file "Utils.cs" is missing. But i cannot find said file anywhere inside the Github project LinkOFF posted (https://github.com/LinkOFF7/sakunaTool). Thank you in advance for your help!
Thank you for telling about missing file. I uploaded it.
And now tool can extract .arc with drag & drop.
## Post #23
- Username: Samchongsa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 20, 2021 3:13 am
- Post datetime: 2022-07-20T00:31:59+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

Many thanks!
## Post #24
- Username: Pioziomgames
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 20, 2022 10:50 pm
- Post datetime: 2022-07-20T15:07:28+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

I've found another game that use the same format: Azure Reflections. However the blender script does not work on the models from it. I took a look at what exactly dies, and bones seem to work if I delete the if statment at line 120, but there are more things that break, Vertex positions are completly broken and line 259 gives an list index out of range error. Here's some sample files: [https://cdn.discordapp.com/attachments/ ... _models.7z](https://cdn.discordapp.com/attachments/838389597997629494/999331286554529883/Azure_reflections_models.7z)
## Post #25
- Username: scone123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 10, 2019 8:42 pm
- Post datetime: 2023-03-12T19:43:12+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

Big thanks for making models and textures possible to decrypt! Though has anyone able to decrypt the animations (.nhanm) yet?
## Post #26
- Username: onepkvn1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 01, 2021 3:25 pm
- Post datetime: 2023-06-03T04:06:24+00:00
- Post Title: Re: Sakuna Of Rice and Ruin .nhmdl

Is there a way I can port my own model into nhmdl format?
