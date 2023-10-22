## Post #1
- Username: IuriDrago
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 06, 2020 3:13 pm
- Post datetime: 2020-05-06T07:43:36+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

Hello guys, i'm new on 3ds Max and i would like to know if anyone has any scripts to import .msh files and apply .dds texture. And if possible I would also like to know some way to save models as .msh and texture in .dds to use in the game in question (Lost Saga Online).

Note 1: I am using 3ds Max 2019, 3ds Max 2010, Blender 2.63 and Blender 2.82, that is, it can be a script for any of these programs, mainly 3ds max.
Note 2: I will be linking a file (on Google Drive) with 2 examples of .msh files and 2 .dds textures of the respective.
[https://drive.google.com/open?id=1OD0Cn ... MQNDI4EYy8](https://drive.google.com/open?id=1OD0Cn6ZbtvSyaxeihlWxWhMQNDI4EYy8)

Edit:
Link for more samples:
[https://drive.google.com/file/d/1IqEjXN ... XE9pQ/view](https://drive.google.com/file/d/1IqEjXNxTLlqm1DDOmSVHJ5PNkU0XE9pQ/view)

Thanks, guys
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-06T12:11:21+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

mephisto_weapon.png (131.04 KiB) Viewed 284 times

(by hex2obj, view 2nd link in my sig)
(My time for writing scripts is limited but the format looks simple. Should not be too hard to write one for yourself.  )
## Post #3
- Username: IuriDrago
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 06, 2020 3:13 pm
- Post datetime: 2020-05-06T16:59:18+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

> Reply from shakotay2 ↑Wed May 06, 2020 8:11 pm at Wed May 06, 2020 8:11 pm
>
> 
mephisto_weapon.png(by hex2obj, view 2nd link in my sig)
(My time for writing scripts is limited but the format looks simple. Should not be too hard to write one for yourself.  )
Well, as i said i'm new (can't make a script properly), but i will check your link. If you can give me a script i would thank you so much
## Post #4
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-06T21:29:03+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

> Well, as i said i'm new (can't make a script properly), but i will check your link. If you can give me a script i would thank you so much

you should check out the tutorial section its filled with great stuff by many users including   shakotay2 ,Bigchillghost and chrox which i found very helpful.

Please upload at least 2-3 more samples, i have the format sorted out except for start of vertex buffer and i need more samples to find the pattern
## Post #5
- Username: IuriDrago
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 06, 2020 3:13 pm
- Post datetime: 2020-05-06T22:02:08+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

> Reply from jayn23 ↑Thu May 07, 2020 5:29 am at Thu May 07, 2020 5:29 am
>
> 
Well, as i said i'm new (can't make a script properly), but i will check your link. If you can give me a script i would thank you so much 

you should check out the tutorial section its filled with great stuff by many users including   shakotay2 ,Bigchillghost and chrox which i found very helpful.

Please upload at least 2-3 more samples, i have the format sorted out except for start of vertex buffer and i need more samples to find the pattern
OK, i will try checking.
I uploaded 4 more samples... pls check and tell me if you get any script working   

More samples link:
[https://drive.google.com/open?id=1IqEjX ... PNkU0XE9pQ](https://drive.google.com/open?id=1IqEjXNxTLlqm1DDOmSVHJ5PNkU0XE9pQ)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-07T05:17:47+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

H2O files for midnight_weapon:

0x10FFC 2808
Vb1
12 99
0x54 766
020000
0x6624 8

0x125EC 1224
Vb1
12 99
0x54 1086
020000
0x6624 8

formulaes (poorly checked):

UVaddr = vAddr + vCnt_arr[SMcnt]*24 ;
FIaddr, first submesh = UVaddr + vCnt_arr[SMcnt]*40 +8 + 16*SMcnt ;

SMcnt is the maximum submesh count. So for weapons with 2 submeshes use SMcnt=2 only.
(submeshes seem to share the same vertex addr and uv addr, afaics. )

For first H2O above:
(vAddr= 0x54)
UVaddr = 0x54 + 1086(!)*24 (dec.)= 0x6624 (for both submeshes)
FIaddr_SM1 = 0x6624 + 1086(!)*40 (dec.) + 8 + 32 (dec.)= 0x10FFC

FIaddr_SM2 = FIaddr_SM1 + 2808*2 (dec.) = 0x125EC
## Post #7
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-07T08:12:04+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

> SMcnt is the maximum submesh count. So for weapons with 2 submeshes use SMcnt=2 only.
>
> (submeshes seem to share the same vertex addr and uv addr, afaics. )
>
> 
>
> For first H2O above:
>
> (vAddr= 0x54)
>
> UVaddr = 0x54 + 1086(!)*24 (dec.)= 0x6624 (for both submeshes)
>
> FIaddr_SM1 = 0x6624 + 1086(!)*40 (dec.) + 8 + 32 (dec.)= 0x10FFC
>
> 
>
> FIaddr_SM2 = FIaddr_SM1 + 2808*2 (dec.) = 0x125EC

I got a working script yesterday and noticed some meshes were getting extra faces on UV and consequently textures were shown incorrectly , but was to lazy to debug why (was 1 AM) i should have thought about sub-meshes, thanks for this it will definitely speed up my script fix up.   

IuriDrago Please add some samples for character models, all samples you have provided are static mesh.
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-05-07T10:44:41+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

Here I attached the converted files in Wavefront .obj format.

All of your files except the mephisto_weapon.msh have 2 objects, but I think the second object does not use the main texture.
[Lost_Saga_Online_msh_to_obj.zip](https://xentaxbackup.github.io/file/18102_Lost_Saga_Online_msh_to_obj.zip)
## Post #9
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-07T22:31:19+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

i found a bit of time today to rework the script, one issue i still need to fix uv of second mesh, everything else is working
script has auto texture loading as well, still waiting for skinned charecters....





 fmt_LostSagaOnline.rar
(1.69 KiB) Downloaded 51 times
## Post #10
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-05-08T16:14:00+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

I think the second object's UVs are fine and the second object does not use the main texture.



changeon_Unwrap_UV_and_texture.png (126.98 KiB) Viewed 230 times
## Post #11
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-05-10T12:46:30+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

IuriDrago,

Can you tell me how can I unpack the Lost Saga's map.iop file?
## Post #12
- Username: IuriDrago
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 06, 2020 3:13 pm
- Post datetime: 2020-05-17T06:57:26+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

> Reply from jayn23 ↑Fri May 08, 2020 6:31 am at Fri May 08, 2020 6:31 am
>
> 
i found a bit of time today to rework the script, one issue i still need to fix uv of second mesh, everything else is working
script has auto texture loading as well, still waiting for skinned charecters....
Hey Jayn, i tried using your script but i got the following error, can you please tell me what to do?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-17T11:03:20+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

fmt_LostSagaOnline.py is a script for Noesis, not for blender! Place it into Noesis' subfolder plugins\python.
## Post #14
- Username: IuriDrago
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 06, 2020 3:13 pm
- Post datetime: 2020-05-17T20:00:52+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

> Reply from shakotay2 ↑Sun May 17, 2020 7:03 pm at Sun May 17, 2020 7:03 pm
>
> 
fmt_LostSagaOnline.py is a script for Noesis, not for blender! Place it into Noesis' subfolder plugins\python.
Oh, thanks man! By the way, is there any way to model on noesis, or export in any format that i will be able to re-model those meshs on Blender or 3ds Max (mainly Blender)??
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-17T21:37:59+00:00
- Post Title: Importing/Exporting .msh files and applying .dds texture ??

> Reply from IuriDrago ↑Mon May 18, 2020 4:00 am at Mon May 18, 2020 4:00 am
>
> , or export in any format that i will be able to re-model those meshs on Blender or 3ds Max (mainly Blender)??From Noesis you can export (File/Export) to .obj or .dae for example.

(You may need to check the uvs of mesh1, mesh0 uvs look good.)
## Post #16
- Username: IuriDrago
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 06, 2020 3:13 pm
- Post datetime: 2020-05-17T22:01:30+00:00
- Post Title: Re: Importing/Exporting .msh files and applying .dds texture ??

> Reply from shakotay2 ↑Mon May 18, 2020 5:37 am at Mon May 18, 2020 5:37 am
>
> 
IuriDrago wrote: ↑Mon May 18, 2020 4:00 am, or export in any format that i will be able to re-model those meshs on Blender or 3ds Max (mainly Blender)??From Noesis you can export (File/Export) to .obj or .dae for example.

(You may need to check the uvs of mesh1, mesh0 uvs look good.)
Which format would allow me to import on Blender or 3ds Max and apply the .dds textures without problem? On noesis the .dds texture is working nicely on those .msh files
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-18T07:53:44+00:00
- Post Title: Re: Importing/Exporting .msh files and applying .dds texture ??

Without problems?   I don't know any. Learn how to use materials.
.


 midnight_weapon.zip
(164.75 KiB) Downloaded 15 times


In blender's object mode switch from "Solid" to "Texture".

(In the obj file look for
mtllib midn_w.mtl
o submesh_0
and
o submesh_1
to understand what's going on. 'o' means object.)

And, well, usually you need to add a Lamp/Sun or all you see is black.
## Post #18
- Username: IuriDrago
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 06, 2020 3:13 pm
- Post datetime: 2020-05-18T23:10:40+00:00
- Post Title: Re: Importing/Exporting .msh files and applying .dds texture ??

> Reply from shakotay2 ↑Mon May 18, 2020 3:53 pm at Mon May 18, 2020 3:53 pm
>
> 
Without problems?   I don't know any. Learn how to use materials.
.
midnight_weapon.zip
In blender's object mode switch from "Solid" to "Texture".

(In the obj file look for
mtllib midn_w.mtl
o submesh_0
and
o submesh_1
to understand what's going on. 'o' means object.)

And, well, usually you need to add a Lamp/Sun or all you see is black.

Ok man ty, i will check!
## Post #19
- Username: IuriDrago
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 06, 2020 3:13 pm
- Post datetime: 2020-06-02T22:59:37+00:00
- Post Title: Re: Importing/Exporting .msh files and applying .dds texture ??

Hey guys, i'm sorry for 2x post in a row.
I have another question: Is there a way to convert .dae or .obj into the default format (.msh) after the edits i made on blender or 3ds max?
## Post #20
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-06-05T19:28:48+00:00
- Post Title: Re: Importing/Exporting .msh files and applying .dds texture ??

I don't wait for more sample files and its texture files (or for the working unpacker), so I have released the following program as web update that contain the Lost Saga Online .msh loader module:

- 3D Object Converter v7.031 (Windows)

How to get the 3D Object Converter v7.031:
Download the 3D Object Converter from [http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v7.031.
