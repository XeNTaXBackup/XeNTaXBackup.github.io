## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-24T23:50:13+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

Here is a tool for loading models from F1 2018. The files are all over the place for this game and loading complete models might be confusing at first. So I recorded an example usage tutorial. You can find the video link below.

Use [EGO ERP Archiver](https://ryder25.itch.io/ego-erp-archiver) for unpacking the .erp files, and for exporting textures.

Tool overview and example exported model



How to use

Video tutorial : [https://youtu.be/k3O4WVo-_F0](https://youtu.be/k3O4WVo-_F0)

Load

Model : Loads a single model file. Files extracted with ERP Archiver have no extension, but model file names end with "^^model".
Folder : Loads all the models inside a folder. You would probably want this for loading car models.
Note  : Folder loading might take some time, depending on models.
Export

NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format : Nex Script
OBJ : Exports the model in OBJ format. Intended for static meshes.
Note  : Models will be exported into the folder Export.
Download : [https://www.mediafire.com/file/mzptexin ... 0.rar/file](https://www.mediafire.com/file/mzptexin617jsnk/F1Viewer_2020.rar/file)

F1 2020

Model formats are same as 18/19, but they are compressed with zstd now. Extract the erp with EGO ERP Archiver as usual. Find the idf folder which will have the model related files. Drag and drop the idf folder on F12020Dec. It will decompress the files as necessary and you can continue the standard process explained in the first post.

F12020Dec : [http://www.mediafire.com/file/ukebxp9jg ... c.rar/file](http://www.mediafire.com/file/ukebxp9jgbiwztc/F12020Dec.rar/file)


Kimi's model textured
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2019-06-04T13:18:31+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

Apologies for the bump, but how were you able to export the textures to something readable? I know there's a Noesis script for headerless .dds files (tga.mipmaps) but that one's for 2016 and tends to corrupt certain textures from what I can attest.
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-04T13:47:21+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

I have used Ego ERP Archiver. It worked fine for 2018 from what I have seen. I have linked it in the first post.
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2019-06-05T00:02:58+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from akderebur ↑Tue Jun 04, 2019 9:47 pm at Tue Jun 04, 2019 9:47 pm
>
> 
I have used Ego ERP Archiver. It worked fine for 2018 from what I have seen. I have linked it in the first post.

I see. Problem is that the texture files in incardriver.erp are ridiculously low-res. :/ Mind if you tell me where did you get the textures for let's say Kimi or Lewis?
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-05T01:40:22+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from huckleberrypie ↑Wed Jun 05, 2019 8:02 am at Wed Jun 05, 2019 8:02 am
>
> 
texture files in incardriver.erp are ridiculously low-res
Make sure to set your game folder in the "Settings" menu.
## Post #6
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2019-06-05T04:18:52+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from akderebur ↑Wed Jun 05, 2019 9:40 am at Wed Jun 05, 2019 9:40 am
>
> 
huckleberrypie wrote: ↑Wed Jun 05, 2019 8:02 am
texture files in incardriver.erp are ridiculously low-res

Make sure to set your game folder in the "Settings" menu.

I see. Where can I find the hand, eyes and shoe textures though?
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-05T11:42:58+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from huckleberrypie ↑Wed Jun 05, 2019 12:18 pm at Wed Jun 05, 2019 12:18 pm
>
> 
I see. Where can I find the hand, eyes and shoe textures though?
I don't remember the locations exactly. Hands and eyes probably in a erp called something like "male_generic". Shoes probably same location as other clothes. Maybe in team erp files.
## Post #8
- Username: cbender
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 30, 2019 10:22 am
- Post datetime: 2019-07-16T14:29:56+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

How do I take the mask? When down the face it comes with the mascara and cap.
## Post #9
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-16T15:18:48+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from cbender ↑Tue Jul 16, 2019 10:29 pm at Tue Jul 16, 2019 10:29 pm
>
> 
How do I take the mask? When down the face it comes with the mascara and cap.
I didn't quite get the question. If there is any mesh that you don't want, you can delete it in a 3D software.
## Post #10
- Username: cbender
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 30, 2019 10:22 am
- Post datetime: 2019-07-16T22:26:34+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

Thks. 

Is possible download Senna and Prost head on F1 2019? I can´t find...
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-17T11:13:17+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from cbender ↑Wed Jul 17, 2019 6:26 am at Wed Jul 17, 2019 6:26 am
>
> 
Senna and Prost head on F1 2019?
I don't have the 2019 game. So I don't know where there are located. Maybe someone else can tell.
## Post #12
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2019-07-24T13:20:48+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

Also, are you able to get the normal maps and certain other textures properly? For some reason I end up with a garbled mess whenever I try to open certain files in Noesis:


I could have used Ninja Ripper even just for the textures, but I'm not that bothered to do so atm.
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-24T13:29:10+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from huckleberrypie ↑Wed Jul 24, 2019 9:20 pm at Wed Jul 24, 2019 9:20 pm
>
> 
Also, are you able to get the normal maps and certain other textures properly?
If you are talking about 2018, yes. I was able to get all the textures properly with ERP tool. If it is 2019 I have no idea.
## Post #14
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2019-07-24T23:50:00+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from akderebur ↑Wed Jul 24, 2019 9:29 pm at Wed Jul 24, 2019 9:29 pm
>
> 
huckleberrypie wrote: ↑Wed Jul 24, 2019 9:20 pm
Also, are you able to get the normal maps and certain other textures properly?

If you are talking about 2018, yes. I was able to get all the textures properly with ERP tool. If it is 2019 I have no idea.
Yes, I am referring to 2018. And it's strange that you were able to get them yet on my end they show up as garbled.
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-25T02:47:08+00:00
- Post Title: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from huckleberrypie ↑Thu Jul 25, 2019 7:50 am at Thu Jul 25, 2019 7:50 am
>
> 
on my end they show up as garbled.
Do they appear fine in the preview of ERP tool?
## Post #16
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2019-07-26T00:37:22+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

> Reply from akderebur ↑Thu Jul 25, 2019 10:47 am at Thu Jul 25, 2019 10:47 am
>
> 
huckleberrypie wrote: ↑Thu Jul 25, 2019 7:50 am
on my end they show up as garbled.

Do they appear fine in the preview of ERP tool?
Glad you mentioned... It does. Guess something must've messed up along the way.
## Post #17
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-26T05:54:09+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

> Reply from huckleberrypie ↑Fri Jul 26, 2019 8:37 am at Fri Jul 26, 2019 8:37 am
>
> 
Guess something must've messed up along the way.
Maybe Noesis can't view the tga properly for some reason. Can you post one of the not working tga here?
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-10T13:55:26+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

F1 2020

Model formats are same as 18/19, but they are compressed with zstd now. Extract the erp with EGO ERP Archiver as usual. Find the idf folder which will have the model related files. Drag and drop the idf folder on F12020Dec. It will decompress the files as necessary and you can continue the standard process explained in the first post.

F12020Dec : [http://www.mediafire.com/file/ukebxp9jg ... c.rar/file](http://www.mediafire.com/file/ukebxp9jgbiwztc/F12020Dec.rar/file)
## Post #19
- Username: jburon72
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 15, 2020 10:30 pm
- Post datetime: 2020-07-15T14:37:29+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

Hi. I got the 3dmodel to load up, but I'm getting error when trying to export. Both for obj and nex. Not sure if I'm missing a step as I'm new to the application.
## Post #20
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-15T15:00:52+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

> Reply from jburon72 ↑Wed Jul 15, 2020 10:37 pm at Wed Jul 15, 2020 10:37 pm
>
> 
Hi. I got the 3dmodel to load up, but I'm getting error when trying to export.

F1 2020, right? Also what is the name of the erp file?
## Post #21
- Username: jburon72
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 15, 2020 10:30 pm
- Post datetime: 2020-07-15T16:34:02+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

Yup. F1 2020. its the williams erp
## Post #22
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-15T18:49:41+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

> Reply from jburon72 ↑Thu Jul 16, 2020 12:34 am at Thu Jul 16, 2020 12:34 am
>
> 
Yup. F1 2020. its the williams erp

Thanks for the report. I have updated the tool. You can find the new download link in the first post.

It was a normal/uv issue for some meshes. I should probably revisit this format, using some 2020 samples, but for now the export should work.
## Post #23
- Username: jburon72
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 15, 2020 10:30 pm
- Post datetime: 2020-07-16T00:13:37+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

> Reply from akderebur ↑Thu Jul 16, 2020 2:49 am at Thu Jul 16, 2020 2:49 am
>
> 
jburon72 wrote: ↑Thu Jul 16, 2020 12:34 am
Yup. F1 2020. its the williams erp


Thanks for the report. I have updated the tool. You can find the new download link in the first post.

It was a normal/uv issue for some meshes. I should probably revisit this format, using some 2020 samples, but for now the export should work.

Many thanks man. BTW does it also include data on the decal texture.
## Post #24
- Username: cbender
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 30, 2019 10:22 am
- Post datetime: 2020-07-16T04:55:54+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

Can someone who has F1 2020 lift their heads? and a body? I want to try to do it on the 3d printer.
## Post #25
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-16T09:11:37+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

> Reply from jburon72 ↑Thu Jul 16, 2020 8:13 am at Thu Jul 16, 2020 8:13 am
>
> 
does it also include data on the decal texture.

No. I haven't done any work on texture/material.
## Post #26
- Username: jburon72
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 15, 2020 10:30 pm
- Post datetime: 2020-07-16T19:14:59+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

No worries mate. Thanks for the reply
## Post #27
- Username: ahmedjan87
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 18, 2020 3:48 am
- Post datetime: 2020-07-17T19:53:28+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

hey there
sorry for the noob question as this is my first time trying to extract 3d models from a game
but every time I try to to put a car through via folder option i just get a messed up car like in the picture
i tried with both f1 2019 and 2020 on 2 different PCs but all led to the same result
[](https://ibb.co/LtYfZ0g)
## Post #28
- Username: DanMclion
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 19, 2020 1:11 am
- Post datetime: 2020-07-18T17:18:05+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

> Reply from ahmedjan87 ↑Sat Jul 18, 2020 3:53 am at Sat Jul 18, 2020 3:53 am
>
> 
hey there
sorry for the noob question as this is my first time trying to extract 3d models from a game
but every time I try to to put a car through via folder option i just get a messed up car like in the picture
i tried with both f1 2019 and 2020 on 2 different PCs but all led to the same result

Just export it as .OBJ and import it into Blender for example. In the Blender import window, check on your right side under Geometry that you have split by group activated. After that, you can delete the parts you do not need.

Well, I guess that's how it works
## Post #29
- Username: ahmedjan87
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 18, 2020 3:48 am
- Post datetime: 2020-07-18T19:02:26+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

> Reply from DanMclion ↑Sun Jul 19, 2020 1:18 am at Sun Jul 19, 2020 1:18 am
>
> 
ahmedjan87 wrote: ↑Sat Jul 18, 2020 3:53 am
hey there
sorry for the noob question as this is my first time trying to extract 3d models from a game
but every time I try to to put a car through via folder option i just get a messed up car like in the picture
i tried with both f1 2019 and 2020 on 2 different PCs but all led to the same result



Just export it as .OBJ and import it into Blender for example. In the Blender import window, check on your right side under Geometry that you have split by group activated. After that, you can delete the parts you do not need.

Well, I guess that's how it works

thanks that actually did the trick
now to figuring out how the rest works lol
## Post #30
- Username: ELEMENT
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 19, 2020 9:29 pm
- Post datetime: 2020-07-21T08:21:41+00:00
- Post Title: Re: F1 2018 (Ego Engine) Model Tool

Can it unpack gird2019?
## Post #31
- Username: cbender
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 30, 2019 10:22 am
- Post datetime: 2020-08-04T16:44:55+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

I tried to find the pilots' heads inside the files, but to no avail. Did anyone succeed?
## Post #32
- Username: sderenno
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 30, 2015 10:13 pm
- Post datetime: 2020-09-11T10:37:59+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

is there the possibility to keep the mapping of all the original channels unaltered? Thanks in advance for the reply.
## Post #33
- Username: RyanZang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 06, 2020 9:09 pm
- Post datetime: 2020-11-06T13:11:24+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

Hi is there any way to export with textures? Cars to be exact. Im looking to export all the cars but when I try to apply texture they are all weird and things. Also the halo is always missing. can you provide all the cars textured?
## Post #34
- Username: RyanZang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 06, 2020 9:09 pm
- Post datetime: 2020-11-11T16:16:40+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

Possible to import every idf file in a folder But export as obj But its many parts not one so every idf file is a object not 1 but many
## Post #35
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-11-11T19:29:55+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from RyanZang ↑Fri Nov 06, 2020 9:11 pm at Fri Nov 06, 2020 9:11 pm
>
> 
Hi is there any way to export with textures?
Nope. I haven't worked on materials, so you have to texture manually.

> Reply from RyanZang ↑Thu Nov 12, 2020 12:16 am at Thu Nov 12, 2020 12:16 am
>
> 
Possible to import every idf file in a folder But export as obj But its many parts not one so every idf file is a object not 1 but many
I don't see how this is a problem. Any 3D software should be able to import multiple OBJ files at once.
## Post #36
- Username: RyanZang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 06, 2020 9:09 pm
- Post datetime: 2020-11-27T07:56:40+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

yes but i have to do the some prosses like 2 billion times.(import 1 idf file, export obj)
## Post #37
- Username: vx110
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 05, 2020 6:13 am
- Post datetime: 2020-12-04T22:17:46+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

Hello Guys,

I've A Question About Extracting F1 2020 Car Models.

I've some problems when I want to extract the 3d-Mesh that not the whole complete 3d-Mesh is showed already in F1 Viewer. There is missing like the front part of the HALO System or the back of the headrest. Also I've serious problems with extracting the textures. It says this are tif files but also when I extract them seperately as dds files, I cant open them?

Will be there a solution?
## Post #38
- Username: Tetrimonio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 16, 2021 12:32 am
- Post datetime: 2021-06-15T16:38:43+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

Im doing this 3d animation 
<blockquote class="imgur-embed-pub" lang="en" data-id="NBqK1MH"  ><a href="//imgur.com/NBqK1MH"></a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>

And i need to extract the hands and boots to finish it (with more details :PP) . I follow the video steps with the new guide for F1 2020 models,  butr when i drag and drop the folder (not the files inside of it) to F12020Dec.exe nothing happpen, the files in the folder are different now? becouse when i opened in F1Viewer nothing is imported, and i searched for the .model file 

Sorry for my english and thank you for this tool
## Post #39
- Username: hamiltonfan1705
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 26, 2021 6:49 am
- Post datetime: 2021-07-25T22:52:30+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

Will there be an update for F1 2021?
## Post #40
- Username: vx110
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 05, 2020 6:13 am
- Post datetime: 2021-08-02T12:45:13+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

Hoping for an Update for 2021 Cars
## Post #41
- Username: Halofan0117
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 20, 2021 7:54 am
- Post datetime: 2021-10-19T23:57:24+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

I wish there was a way to import a 3d model and export it as an IDF file, i think you can pull it off...
## Post #42
- Username: Carbune
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 07, 2021 5:25 am
- Post datetime: 2022-01-12T21:53:05+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

Any word on this getting an update for 2021? F12020Dec doesn't work on the 2021 idf folder. The program just opens and closes instantly without anything being changed.
## Post #43
- Username: Ony
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 08, 2021 5:32 pm
- Post datetime: 2022-05-12T17:15:36+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

Hey there. I'm pretty close to finishing a rip of Fernando Alonso in 3ds max, but I just can't rip the eyelash texture because the mipmap for it is non existent. Also, my other huge problem is that the logos on his suit doesn't appear as they should. I tried flipping the uv map all around, same with the textures, it won't show how I want them to. Did I rip the wrong texture? It's called " 2018-mclaren_logo_01_d.tga (.dds) ". Anyone knows a solution to both my problems? Would be lovely if I could finish it. Thanks in advance!
## Post #44
- Username: diegorl
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 15, 2022 10:47 pm
- Post datetime: 2022-09-15T14:49:37+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

Hi! I´m trying to export the Renault R26 from F1 2020 but when I try to load the folder nothing happens
## Post #45
- Username: MORDORr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 12, 2023 5:16 am
- Post datetime: 2023-07-11T21:18:26+00:00
- Post Title: Re: F1 2018 - 2020 (Ego Engine) Model Tool

> Reply from diegorl ↑Thu Sep 15, 2022 10:49 pm at Thu Sep 15, 2022 10:49 pm
>
> 
Hi! I´m trying to export the Renault R26 from F1 2020 but when I try to load the folder nothing happens

Hi, i was wondering if u managed to solve the problem, many thanks
