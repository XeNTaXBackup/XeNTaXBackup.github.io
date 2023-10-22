## Post #1
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-03-07T13:01:59+00:00
- Post Title: Power Rangers Legacy Wars Android

I need help to extract models from Power Rangers Legacy Wars. File in format .sassets (unity 5.5.0p4)

[http://www.mediafire.com/file/w45tfjbw4 ... T1_red.rar](http://www.mediafire.com/file/w45tfjbw4cn8o6g/RngM_MOV_T1_red.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-07T22:33:10+00:00
- Post Title: Power Rangers Legacy Wars Android

rngm_mov_t1_red_skeleton.png (251.8 KiB) Viewed 691 times


same process as here
[viewtopic.php?p=125969#p125969](http://forum.xentax.com/viewtopic.php?p=125969#p125969)
## Post #3
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-03-08T19:03:50+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> rngm_mov_t1_red_skeleton.png
same process as here
viewtopic.php?p=125969#p125969
I am having many error messages and the program is crashing, could you give me the link of the versions that you use? Thank you.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-08T21:05:27+00:00
- Post Title: Power Rangers Legacy Wars Android

what error and what is crashing?
i am using no special techniques here, the last version of UABE and Unity Studio,
just have to follow the instruction i linked to already.
## Post #5
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-03-08T22:24:37+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> what error and what is crashing?
i am using no special techniques here, the last version of UABE and Unity Studio,
just have to follow the instruction i linked to already.

In the tutorial you use two versions of UAB, one for export the .dat file and another to import, I have the 2.1, which versions should I use? I try to import the .dat file into one old version but the program hangs.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-09T00:47:50+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from dswd2015
>
> In the tutorial you use two versions of UAB, one for export the .dat file and another to import
no just the last version like i said before, where do you see that i'm using 2 versions of UABE?
## Post #7
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-03-09T02:02:16+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> dswd2015 wrote:In the tutorial you use two versions of UAB, one for export the .dat file and another to import
no just the last version like i said before, where do you see that i'm using 2 versions of UABE?

When you referred to export and then import I thought it was two different versions, I must have misunderstood. In that case should I export and then import the .dat to the same version, correct? If you can post pictures of the procedure I could understand. Here are the error images I get when importing .dat.
[error.rar](https://xentaxbackup.github.io/file/12582_error.rar)
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-09T02:50:55+00:00
- Post Title: Power Rangers Legacy Wars Android

i thought you already understood the process after the posts you made in the other thread, but lets try this again   

before you do anything make sure you have an old unity file that Unity Studio can open,
this unity file should already contain a mesh type so we can overwrite it with UABE later.
i will call this old unity file "CAB-123"

1. open "RngM_MOV_T1_red.sasset" with UABE
2. find the model in the list, in this case select "rngm_mov_t1_red_skeleton.fbx"
3. now click "Export Raw" and save it as "somename.dat" and close "RngM_MOV_T1_red.sasset"
4. now open "CAB-123" with UABE
5. select a file of the same type (mesh) from the list so we can overwrite it
6. click "Import Raw", now find and select the "somename.dat" that you exported earlier
7. now click File > Save and give it a name like "CAB-mynewfile"
8. now open "CAB-mynewfile" with Unity Studio and export the mesh as fbx
## Post #9
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-03-09T03:29:22+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> i thought you already understood the process after the posts you made in the other thread, but lets try this again   

before you do anything make sure you have an old unity file that Unity Studio can open,
this unity file should already contain a mesh type so we can overwrite it with UABE later.
i will call this old unity file "CAB-123"

1. open "RngM_MOV_T1_red.sasset" with UABE
2. find the model in the list, in this case select "rngm_mov_t1_red_skeleton.fbx"
3. now click "Export Raw" and save it as "somename.dat" and close "RngM_MOV_T1_red.sasset"
4. now open "CAB-123" with UABE
5. select a file of the same type (mesh) from the list so we can overwrite it
6. click "Import Raw", now find and select the "somename.dat" that you exported earlier
7. now click File > Save and give it a name like "CAB-mynewfile"
8. now open "CAB-mynewfile" with Unity Studio and export the mesh as fbx

Thank you so much, now I understand where I'm going wrong. Now I will extract and edit for XNAlara. Thanks.
## Post #10
- Username: Sakuraba
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Mar 14, 2016 4:23 am
- Post datetime: 2017-03-10T17:33:05+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> i thought you already understood the process after the posts you made in the other thread, but lets try this again   

before you do anything make sure you have an old unity file that Unity Studio can open,
this unity file should already contain a mesh type so we can overwrite it with UABE later.
i will call this old unity file "CAB-123"

1. open "RngM_MOV_T1_red.sasset" with UABE
2. find the model in the list, in this case select "rngm_mov_t1_red_skeleton.fbx"
3. now click "Export Raw" and save it as "somename.dat" and close "RngM_MOV_T1_red.sasset"
4. now open "CAB-123" with UABE
5. select a file of the same type (mesh) from the list so we can overwrite it
6. click "Import Raw", now find and select the "somename.dat" that you exported earlier
7. now click File > Save and give it a name like "CAB-mynewfile"
8. now open "CAB-mynewfile" with Unity Studio and export the mesh as fbx

I understand the whole process I use UABE to extract models from kamen rider, but in this question I do not know how pegr the updated version of UABE, I entered the website of your signature and I still did not understand.
## Post #11
- Username: Sakuraba
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Mar 14, 2016 4:23 am
- Post datetime: 2017-03-10T18:01:24+00:00
- Post Title: Power Rangers Legacy Wars Android

before you do anything make sure you have an old unity file that Unity Studio can open,
this unity file should already contain a mesh type so we can overwrite it with UABE later.
i will call this old unity file "CAB-123"

I did not understand this part

[https://ibb.co/fgdUbF](https://ibb.co/fgdUbF)

The mesh is compressed.
## Post #12
- Username: Leucionio
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 10, 2017 11:54 pm
- Post datetime: 2017-03-10T20:32:19+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> i thought you already understood the process after the posts you made in the other thread, but lets try this again   

before you do anything make sure you have an old unity file that Unity Studio can open,
this unity file should already contain a mesh type so we can overwrite it with UABE later.
i will call this old unity file "CAB-123"

1. open "RngM_MOV_T1_red.sasset" with UABE
2. find the model in the list, in this case select "rngm_mov_t1_red_skeleton.fbx"
3. now click "Export Raw" and save it as "somename.dat" and close "RngM_MOV_T1_red.sasset"
4. now open "CAB-123" with UABE
5. select a file of the same type (mesh) from the list so we can overwrite it
6. click "Import Raw", now find and select the "somename.dat" that you exported earlier
7. now click File > Save and give it a name like "CAB-mynewfile"
8. now open "CAB-mynewfile" with Unity Studio and export the mesh as fbx

You have one "old unity file" to post, do not know how to do. thank you
## Post #13
- Username: Sakuraba
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Mar 14, 2016 4:23 am
- Post datetime: 2017-03-10T21:09:05+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> i thought you already understood the process after the posts you made in the other thread, but lets try this again   

before you do anything make sure you have an old unity file that Unity Studio can open,
this unity file should already contain a mesh type so we can overwrite it with UABE later.
i will call this old unity file "CAB-123"

1. open "RngM_MOV_T1_red.sasset" with UABE
2. find the model in the list, in this case select "rngm_mov_t1_red_skeleton.fbx"
3. now click "Export Raw" and save it as "somename.dat" and close "RngM_MOV_T1_red.sasset"
4. now open "CAB-123" with UABE
5. select a file of the same type (mesh) from the list so we can overwrite it
6. click "Import Raw", now find and select the "somename.dat" that you exported earlier
7. now click File > Save and give it a name like "CAB-mynewfile"
8. now open "CAB-mynewfile" with Unity Studio and export the mesh as fbx

I was successful with the process just can not now work with the texture

[https://ibb.co/mv9wOv](https://ibb.co/mv9wOv)
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-10T22:59:36+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from Leucionio
>
> You have one "old unity file" to post, do not know how to do. thank you
there is several websites that distribute older apks for android games that have files supported by Unity Studio
but i will share this one to save you the time since you asked 


 CAB-char_b1_pre.zip
(55.81 KiB) Downloaded 92 times



> Reply from Sakuraba
>
> I was successful with the process just can not now work with the texture
https://ibb.co/mv9wOv
looks like you just need to flip the UVs vertically and you are good to go
## Post #15
- Username: Sakuraba
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Mar 14, 2016 4:23 am
- Post datetime: 2017-03-11T00:36:23+00:00
- Post Title: Power Rangers Legacy Wars Android

> Reply from Sakuraba
>
> I was successful with the process just can not now work with the texture
https://ibb.co/mv9wOv
looks like you just need to flip the UVs vertically and you are good to go  [/quote]

Thanks for replying to me, your tip did not work right here continues without the texture applied correctly.
## Post #16
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-11T15:15:46+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

Hello AceWell,can you make a noesis script for Marvel Ultimate Alliance 1 PC remastered .Igb files?
Samples here: [https://mega.nz/#!DhhABKoK!hDoRduYShV3K ... flGv1kOybs](https://mega.nz/#!DhhABKoK!hDoRduYShV3KE9YGWHuebX3jobbfbGdLuflGv1kOybs)
Thanks in advance.
P.S I know what i post this in wrong topic,but i can't send Messages to you..
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-12T00:53:15+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from Sakuraba
>
> Thanks for replying to me, your tip did not work right here continues without the texture applied correctly.
i don't know then, just keep trying to line up the UVs with the texture however you need to, 
you'll get it right eventually since there is only so many ways you can orient them. 


> Reply from Rutabaga
>
> Hello AceWell,can you make a noesis script for Marvel Ultimate Alliance 1 PC remastered .Igb files?
i took a look at your samples and at first glance they look chaotic, so probably not
## Post #18
- Username: rballad
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 11, 2014 9:40 am
- Post datetime: 2017-03-12T12:54:45+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

@ acewell, does the method  keeps the model rigging?
it would  be easier to use unity studio's extract bundle command.  when searching for bundles, scroll down to  all files option
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-12T22:57:42+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from rballad
>
> does the method  keeps the model rigging?i've never seen a non proprietary 3d software format store rigging, so i would say no

> Reply from rballad
>
> it would  be easier to use unity studio's extract bundle command.  when searching for bundles, scroll down to  all files optionif it works better for you then go for it, doesn't really matter as long as it gets done.   
DerPopo said he will add compressed mesh support to UABE within the next 3-4 months so the process here is temporary anyway.
## Post #20
- Username: Leucionio
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 10, 2017 11:54 pm
- Post datetime: 2017-03-13T13:31:15+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from dswd2015
>
> I need help to extract models from Power Rangers Legacy Wars. File in format .sassets (unity 5.5.0p4)

http://www.mediafire.com/file/w45tfjbw4 ... T1_red.rar

What process did you use to extract .sassets files? Do you have any tutorials to tell me?

Thank
## Post #21
- Username: Sakuraba
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Mar 14, 2016 4:23 am
- Post datetime: 2017-03-14T01:08:50+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from Leucionio
>
> dswd2015 wrote:I need help to extract models from Power Rangers Legacy Wars. File in format .sassets (unity 5.5.0p4)

http://www.mediafire.com/file/w45tfjbw4 ... T1_red.rar

What process did you use to extract .sassets files? Do you have any tutorials to tell me?

Thank

The whole topic is related to this, take it easy.
## Post #22
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-03-14T01:24:47+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from Leucionio
>
> dswd2015 wrote:I need help to extract models from Power Rangers Legacy Wars. File in format .sassets (unity 5.5.0p4)

http://www.mediafire.com/file/w45tfjbw4 ... T1_red.rar

What process did you use to extract .sassets files? Do you have any tutorials to tell me?

Thank

Read the post, AceWell explained how the process works.
## Post #23
- Username: markrodil29
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 12, 2017 12:46 am
- Post datetime: 2017-03-14T05:09:26+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> i thought you already understood the process after the posts you made in the other thread, but lets try this again   

before you do anything make sure you have an old unity file that Unity Studio can open,
this unity file should already contain a mesh type so we can overwrite it with UABE later.
i will call this old unity file "CAB-123"

1. open "RngM_MOV_T1_red.sasset" with UABE
2. find the model in the list, in this case select "rngm_mov_t1_red_skeleton.fbx"
3. now click "Export Raw" and save it as "somename.dat" and close "RngM_MOV_T1_red.sasset"
4. now open "CAB-123" with UABE
5. select a file of the same type (mesh) from the list so we can overwrite it
6. click "Import Raw", now find and select the "somename.dat" that you exported earlier
7. now click File > Save and give it a name like "CAB-mynewfile"
8. now open "CAB-mynewfile" with Unity Studio and export the mesh as fbx


Hello AceWell can you check out what went wrong with my procedure... my fbx file wont work     

[http://i1259.photobucket.com/albums/ii5 ... obcjfb.jpg](http://i1259.photobucket.com/albums/ii545/xtian_ibm/red%20ranger_zpsnyobcjfb.jpg)


Thank you in advance.. More Power!!!!
## Post #24
- Username: rizky81
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 14, 2016 7:35 pm
- Post datetime: 2017-03-14T15:24:13+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from markrodil29
>
> AceWell wrote:i thought you already understood the process after the posts you made in the other thread, but lets try this again   

before you do anything make sure you have an old unity file that Unity Studio can open,
this unity file should already contain a mesh type so we can overwrite it with UABE later.
i will call this old unity file "CAB-123"

1. open "RngM_MOV_T1_red.sasset" with UABE
2. find the model in the list, in this case select "rngm_mov_t1_red_skeleton.fbx"
3. now click "Export Raw" and save it as "somename.dat" and close "RngM_MOV_T1_red.sasset"
4. now open "CAB-123" with UABE
5. select a file of the same type (mesh) from the list so we can overwrite it
6. click "Import Raw", now find and select the "somename.dat" that you exported earlier
7. now click File > Save and give it a name like "CAB-mynewfile"
8. now open "CAB-mynewfile" with Unity Studio and export the mesh as fbx


Hello AceWell can you check out what went wrong with my procedure... my fbx file wont work     

http://i1259.photobucket.com/albums/ii5 ... obcjfb.jpg


Thank you in advance.. More Power!!!!

Nothing is wrong, you just need one more step to open the file in blender. Download "Noesis", open and export the .fbx file into .obj and you will be able to open the file on blender.
## Post #25
- Username: markrodil29
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 12, 2017 12:46 am
- Post datetime: 2017-03-15T04:16:36+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from rizky81
>
> markrodil29 wrote:AceWell wrote:i thought you already understood the process after the posts you made in the other thread, but lets try this again   

before you do anything make sure you have an old unity file that Unity Studio can open,
this unity file should already contain a mesh type so we can overwrite it with UABE later.
i will call this old unity file "CAB-123"

1. open "RngM_MOV_T1_red.sasset" with UABE
2. find the model in the list, in this case select "rngm_mov_t1_red_skeleton.fbx"
3. now click "Export Raw" and save it as "somename.dat" and close "RngM_MOV_T1_red.sasset"
4. now open "CAB-123" with UABE
5. select a file of the same type (mesh) from the list so we can overwrite it
6. click "Import Raw", now find and select the "somename.dat" that you exported earlier
7. now click File > Save and give it a name like "CAB-mynewfile"
8. now open "CAB-mynewfile" with Unity Studio and export the mesh as fbx


Hello AceWell can you check out what went wrong with my procedure... my fbx file wont work     

http://i1259.photobucket.com/albums/ii5 ... obcjfb.jpg


Thank you in advance.. More Power!!!! 

Nothing is wrong, you just need one more step to open the file in blender. Download "Noesis", open and export the .fbx file into .obj and you will be able to open the file on blender.

Thanks a lot that helps a lot.. another question, Hows the process to get the textures? 

Thanks in advance rizky81...
## Post #26
- Username: Leucionio
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 10, 2017 11:54 pm
- Post datetime: 2017-03-20T13:09:46+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

Thanks a lot that helps a lot.. another question, Hows the process to get the textures? 

Thanks in advance rizky81...    

I need the same explanation
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-20T15:59:15+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

select the textures in UABE then click "Plugins" and select an export option
## Post #28
- Username: deinmodel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 14, 2017 5:53 pm
- Post datetime: 2017-04-19T22:14:18+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> select the textures in UABE then click "Plugins" and select an export option

I'm trying to export these models from the newer, more realistic version, can it help?
I can see the textures in Unity, but I can not find the mesh

[https://www.4shared.com/folder/tyWM5uIQ ... _MMPR.html](https://www.4shared.com/folder/tyWM5uIQ/Extrao_MMPR.html)
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-20T01:43:16+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

i can't access whatever files you linked to, best to use another file host like mega, mediafire, 
dropbox, google drive, one drive, sendspace etc

the instruction for converting the mesh is on the first page of this thread but if you don't even
see a mesh type listed in UABE then there is no mesh to extract.
## Post #30
- Username: deinmodel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 14, 2017 5:53 pm
- Post datetime: 2017-04-20T11:36:40+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> i can't access whatever files you linked to, best to use another file host like mega, mediafire, 
dropbox, google drive, one drive, sendspace etc

the instruction for converting the mesh is on the first page of this thread but if you don't even
see a mesh type listed in UABE then there is no mesh to extract.

[http://www.mediafire.com/file/f3hafgngi ... angers.obb](http://www.mediafire.com/file/f3hafgngiga2g0u/main.6.com.lionsgate.powerrangers.obb)
## Post #31
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-21T01:42:10+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

you have uploaded an obb file, you can extract it with 7-zip to get files that can be opened in UABE.
## Post #32
- Username: deinmodel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 14, 2017 5:53 pm
- Post datetime: 2017-04-21T02:18:26+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> you have uploaded an obb file, you can extract it with 7-zip to get files that can be opened in UABE.

Yes, I uploaded the .OBB file. Inside it contains the folder "Assets", I preferred to send it complete to avoid error

Folder: Assets> Bin> "file.assets"
## Post #33
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-21T02:47:00+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

i'm not sure what you're asking, you have the files you need and the instruction to process them is in this thread.
i don't know anything about this game, if you are looking for something specific maybe someone else can help.
## Post #34
- Username: deinmodel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 14, 2017 5:53 pm
- Post datetime: 2017-04-22T00:01:42+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> i'm not sure what you're asking, you have the files you need and the instruction to process them is in this thread.
i don't know anything about this game, if you are looking for something specific maybe someone else can help.

This is a type of game in augmented reality (VR) with the theme Power ranger. I believe it was built with the same process as the Legacy war game, or similar.

I used the method that you showed in the Legacy war game and it worked, but I'm trying to do the same with this (VR) and can not find the mesh. So far I've only found the textures using Unity

[https://play.google.com/store/apps/deta ... werrangers](https://play.google.com/store/apps/details?id=com.lionsgate.powerrangers)
## Post #35
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-22T02:29:48+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

looks like the mesh and textures you might want are in the "sharedassets*.assets" 1-10 files 



blueranger.png (249.7 KiB) Viewed 148 times


nothing special was done here, just opened all 10 of those .assets at the same time with UABE and
exported mesh as obj and textures as tga, many would not convert, but at least the important ones did.  
you can use Unity Studio or UnityEx to convert the meshes and textures too.
## Post #36
- Username: deinmodel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 14, 2017 5:53 pm
- Post datetime: 2017-04-26T15:45:21+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> looks like the mesh and textures you might want are in the "sharedassets*.assets" 1-10 files 
blueranger.png
nothing special was done here, just opened all 10 of those .assets at the same time with UABE and
exported mesh as obj and textures as tga, many would not convert, but at least the important ones did.  
you can use Unity Studio or UnityEx to convert the meshes and textures too.

Hello again, I tried "everything" and only had a mistake.
I followed the same process that you explained to the game (Legacy War) and applied the method in the one I need.

I opened the 10 .assets (.assets1 ~ .assets10), in the "Type" part it does not show me anything other than codes (ex: 0x00000096). I can not find the mesh of the models.

When I import the 10.assets to UNITY I can only see the textures. Knit do not see.
The "Type" that appears to me inside it is:
* Textute2D
* TextAsset
* Shader
* Font
* AudioClip

Would it be possible to help me by sending print from step by step or only the models in 3D already help me.

Thanks for the strength so far.
## Post #37
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-26T20:29:23+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

different games may store data differently, my reply to you was about "Power Rangers Command Center"
[https://play.google.com/store/apps/deta ... werrangers](https://play.google.com/store/apps/details?id=com.lionsgate.powerrangers)
i guess now you are talking about "Power Rangers Legacy Wars" again?
[https://play.google.com/store/apps/deta ... legacywars](https://play.google.com/store/apps/details?id=com.nway.powerrangerslegacywars)
i don't know anything about which files store which models in these games, you have to ask those who 
know or just start opening them until you find what you need and always use the latest version of tools.
## Post #38
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2017-06-03T23:23:50+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from dswd2015
>
> I need help to extract models from Power Rangers Legacy Wars. File in format .sassets (unity 5.5.0p4)

http://www.mediafire.com/file/w45tfjbw4 ... T1_red.rar

How do you copy those asset files from game cache folder? I have been trying to do it from sooo many methods from youtube and hasn't come up with anything. Any help would be appreciated.
## Post #39
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-06-04T14:45:47+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from sasimiv11
>
> dswd2015 wrote:I need help to extract models from Power Rangers Legacy Wars. File in format .sassets (unity 5.5.0p4)

http://www.mediafire.com/file/w45tfjbw4 ... T1_red.rar

How do you copy those asset files from game cache folder? I have been trying to do it from sooo many methods from youtube and hasn't come up with anything. Any help would be appreciated.

In your smartphone, the way is, Android - data - com.nway.powerrangerslegacywars - Assetbundles - Android - Characters. Copy the Characters folder, this is where the models are.
## Post #40
- Username: verdehombre
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 08, 2017 11:16 am
- Post datetime: 2017-11-08T03:20:02+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

This is going to sound stupid to try to revive a 5+ month old thread, but it seems that I have been having some problems with the process as several people mentioned above. Whenever I try to load a .sasset file, it brings me to basically dump the file out. There is no OBJ files, the only thing that is exportable is a CAB file similar to the old asset file that people want before. I don't know whether i'm in the right folder or not, could you give a dude some helpful advice? (Note: It may be because i'm completely new to using this program, but I can export other stuff easily.)
## Post #41
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2017-11-08T03:51:55+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from verdehombre
>
> This is going to sound stupid to try to revive a 5+ month old thread, but it seems that I have been having some problems with the process as several people mentioned above. Whenever I try to load a .sasset file, it brings me to basically dump the file out. There is no OBJ files, the only thing that is exportable is a CAB file similar to the old asset file that people want before. I don't know whether i'm in the right folder or not, could you give a dude some helpful advice? (Note: It may be because i'm completely new to using this program, but I can export other stuff easily.)

Have you tried clicking the "mesh" file than clicking on "export raw" and importing into an older .assets file???
## Post #42
- Username: verdehombre
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 08, 2017 11:16 am
- Post datetime: 2017-11-08T12:26:07+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from Ecelon
>
> verdehombre wrote:This is going to sound stupid to try to revive a 5+ month old thread, but it seems that I have been having some problems with the process as several people mentioned above. Whenever I try to load a .sasset file, it brings me to basically dump the file out. There is no OBJ files, the only thing that is exportable is a CAB file similar to the old asset file that people want before. I don't know whether i'm in the right folder or not, could you give a dude some helpful advice? (Note: It may be because i'm completely new to using this program, but I can export other stuff easily.)

Have you tried clicking the "mesh" file than clicking on "export raw" and importing into an older .assets file???

Whenever I try to click info after I dump the compressed file, it goes to being not responding (probably trying to load the file) then throws me this error that says "This file isn't a valid assets file." I'll attatch a file of what I have so far:
[https://imgur.com/a/CsJZb](https://imgur.com/a/CsJZb)
Would this seem correct to you with what I have at least?
## Post #43
- Username: verdehombre
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 08, 2017 11:16 am
- Post datetime: 2017-11-08T22:22:45+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

Sorry, apparently i was using 2.0 and when i upgraded to 2.1d it worked fine.
## Post #44
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2017-11-11T01:42:44+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from verdehombre
>
> Sorry, apparently i was using 2.0 and when i upgraded to 2.1d it worked fine.

Glad to hear you got it all sorted out mate, and sorry I didn't help you figure it out! XD
## Post #45
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-03-30T13:07:14+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

New metod for extraction:



Content: Tutorial in images + instructions + programs

Download: [http://www.mediafire.com/file/ic8zbm100 ... torial.rar](http://www.mediafire.com/file/ic8zbm100497w3m/New+Tutorial.rar)

Need to download to view the textures: [https://community.imgtec.com/developers ... nstallers/](https://community.imgtec.com/developers/powervr/offline-installers/)
## Post #46
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-30T19:25:56+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from dswd2015
>
> I need help to extract models from Power Rangers Legacy Wars. File in format .sassets (unity 5.5.0p4)
http://www.mediafire.com/file/w45tfjbw4 ... T1_red.rar
Perfare's fork of Unity Studio can open and export all these files now,
no need to use the temporary process used before.
## Post #47
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-04-01T00:41:13+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from AceWell
>
> dswd2015 wrote:I need help to extract models from Power Rangers Legacy Wars. File in format .sassets (unity 5.5.0p4)
http://www.mediafire.com/file/w45tfjbw4 ... T1_red.rar
Perfare's fork of Unity Studio can open and export all these files now,
no need to use the temporary process used before.

Currently yes, but without your tutorial we would not have anything, I thank you for helping us, thank you very much.
## Post #48
- Username: TheRaspu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 08, 2018 3:55 am
- Post datetime: 2018-06-07T20:49:59+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from dswd2015
>
> AceWell wrote:dswd2015 wrote:I need help to extract models from Power Rangers Legacy Wars. File in format .sassets (unity 5.5.0p4)
http://www.mediafire.com/file/w45tfjbw4 ... T1_red.rar
Perfare's fork of Unity Studio can open and export all these files now,
no need to use the temporary process used before.  

Currently yes, but without your tutorial we would not have anything, I thank you for helping us, thank you very much.

Hi... 
what is the latest version? (Unity Studio)
## Post #49
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-06-08T01:16:46+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from TheRaspu
>
> what is the latest version? (Unity Studio)
here, now called "AssetStudio"
[https://ci.appveyor.com/project/Perfare ... /artifacts](https://ci.appveyor.com/project/Perfare/assetstudio/branch/master/artifacts)

source is here
[https://github.com/Perfare/AssetStudio](https://github.com/Perfare/AssetStudio)
## Post #50
- Username: TheRaspu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 08, 2018 3:55 am
- Post datetime: 2018-06-08T20:11:24+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

Hello, guys, I need help! I want to extract these models (PRLW) from Bluestacks ... before I have extracted models from other games in Bluestaks using Ninja Ripper and Noesis but with this game (PRLW) it did not work. I do not know much about programs and I do not understand this post very well; but I really need these 3D models ... could someone explain to me step by step how and with what programs can I use models of this game (PRLW) using Bluestacks ... if you can pass me images of the process step by step ... or some link from youtube! Well guys I hope you can help me! Thank you.
[img]Help.jpg[/img]
[Help.jpg](https://xentaxbackup.github.io/file/14450_Help.jpg)
## Post #51
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2018-08-09T15:13:16+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

I have a problem with unity studio program. When I want to export those models it shows unable to load PVRunwrap.dll and program crashed on me so I can't export the texture. Does anyone know how to fix this? Any help would be appreciated
Thank you in advance
## Post #52
- Username: Sonicality
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 01, 2017 1:37 pm
- Post datetime: 2018-09-18T22:38:57+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

I know this thread's been abandoned for a while, but this is driving me crazy so I figure I may as well ask. Even if it makes me feel and or sound like an idiot.

This thread is great at telling me what to do with the .sasset files. Except I've extracted the APK for the game and I can't find a single .sasset file anywhere. How do you get to those in the first place?
## Post #53
- Username: Larxian
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 09, 2018 1:47 am
- Post datetime: 2018-09-19T00:29:08+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

> Reply from Sonicality
>
> I know this thread's been abandoned for a while, but this is driving me crazy so I figure I may as well ask. Even if it makes me feel and or sound like an idiot.

This thread is great at telling me what to do with the .sasset files. Except I've extracted the APK for the game and I can't find a single .sasset file anywhere. How do you get to those in the first place?

I personally got them in the cache folder in my phone, not in the APK
## Post #54
- Username: Favour Aloy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 28, 2020 5:12 pm
- Post datetime: 2020-02-28T09:18:36+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

After installing the app, i tried updating it, and then it showed me error: asset files (13). Please help me i don't know what to do.
## Post #55
- Username: Toonboyii
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 10, 2017 2:50 pm
- Post datetime: 2022-05-05T06:12:56+00:00
- Post Title: Re: Power Rangers Legacy Wars Android

Hi all,

Sorry i know the last post for this chat was 2 years ago.
If anyone is still wondering on how to extract the models with the bones, i have created a tutorial in my DeviantArt journal.
It's quite lengthy but i try to make it as detailed as possible.
Link: [https://www.deviantart.com/toonboyii/jo ... -915046552](https://www.deviantart.com/toonboyii/journal/Power-Rangers-Legacy-Wars-extract-tutorial-915046552)
All you need for software is actually just AssetStudio. The rest is more on the files that are crucial in order to achieve the results.
Hope this helps.
