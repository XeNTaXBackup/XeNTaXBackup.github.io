## Post #1
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-10-06T15:06:47+00:00
- Post Title: Ring of Elysium Noesis script

Based on this zaramot's script:[viewtopic.php?f=16&t=20691&start=15#p159658](https://forum.xentax.com/viewtopic.php?f=16&t=20691&start=15#p159658)
I rewrite this Noesis script to support skeleton loading. 

Usage: Since skeleton are stored in "Ring of Elysium\SFC\Actors.sfc", you should unpack this file and edit the script line10 "sfc_Actors_folder"

You may need this extractor by LokiReborn to get all files from "data_bas_*.vfs".
[https://zenhax.com/viewtopic.php?f=9&t= ... =20#p49017](https://zenhax.com/viewtopic.php?f=9&t=4299&start=20#p49017)
Mirror:[https://www.mediafire.com/folder/w7x6zo ... kdx/shared](https://www.mediafire.com/folder/w7x6zohroff8dvh,ctt76v0m0c6rkdx/shared)

zaramot's BMS script to extract files from *.sfc files. 
[viewtopic.php?f=10&t=21569#p159192](https://forum.xentax.com/viewtopic.php?f=10&t=21569#p159192)

010editor template included. 
Skeleton weight support.
Some vertex normal support(maybe correct).


```
2022.1.3 v2:Add automatically finding match skel file feature.

```

More tests are welcome, please report bug with samples attached 
[fmt_ROE_v2.zip](https://xentaxbackup.github.io/file/21493_fmt_ROE_v2.zip)
## Post #2
- Username: CQuence
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 13, 2017 12:20 am
- Post datetime: 2022-01-02T18:56:34+00:00
- Post Title: Ring of Elysium Noesis script

Hello.
When unpacking *.sfx files, I get *.dat files. Are all the mashes in them? How can I view them?
## Post #3
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2022-01-03T04:30:41+00:00
- Post Title: Ring of Elysium Noesis script

> Reply from CQuence ↑Mon Jan 03, 2022 2:56 am at Mon Jan 03, 2022 2:56 am
>
> 
Hello.
When unpacking *.sfx files, I get *.dat files. Are all the mashes in them? How can I view them?

For FPP meshes, they are stored in  "data_bas_*.vfs" under the root folder of the game.
For TPP meshes and other meshes, they are stored in *.sfc files. You should be able to get all meshes you want.
## Post #4
- Username: CQuence
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 13, 2017 12:20 am
- Post datetime: 2022-01-03T10:35:52+00:00
- Post Title: Ring of Elysium Noesis script

I found meshes from the first person view. The 1st version of the plugin opens them.
The second version of the plugin gives this error when viewing *.QSG files and *.DAT files. 


Png_0001.png (7.52 KiB) Viewed 548 times


I tried DAT files from Avatars_Skin_X_F_SJ.sfc.
## Post #5
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2022-01-04T08:32:08+00:00
- Post Title: Ring of Elysium Noesis script

Thanks PeterZ for the script, is it possible to align the skeleton with the face\head mesh?



Alignment.png (77.98 KiB) Viewed 523 times
## Post #6
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2022-01-04T15:47:17+00:00
- Post Title: Ring of Elysium Noesis script

> Reply from CQuence ↑Mon Jan 03, 2022 6:35 pm at Mon Jan 03, 2022 6:35 pm
>
> 
I found meshes from the first person view. The 1st version of the plugin opens them.
The second version of the plugin gives this error when viewing *.QSG files and *.DAT files. Png_0001.png
I tried DAT files from Avatars_Skin_X_F_SJ.sfc.

Have you exported "Actors.sfc" to your folder"F:\SteamLibrary\steamapps\common\Ring of Elysium\SFC\Actors\"
which dat file did you try to view
## Post #7
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2022-01-04T15:58:45+00:00
- Post Title: Ring of Elysium Noesis script

> Reply from X3D ↑Tue Jan 04, 2022 4:32 pm at Tue Jan 04, 2022 4:32 pm
>
> 
Thanks PeterZ for the script, is it possible to align the skeleton with the face\head mesh?

Alignment.png

I have noticed it, but I don't know how to fix it, here is why:
"mesh" type .dat file contain boneMtx,boneScale and boneName.
"skeleton" type .dat file contain boneMtx,boneScale,boneName and boneParent.
However, boneMtx in these two types are different.
For normal torso "mesh" type .dat file,vertex use boneMtx that stored in "skeleton" type .dat file.
For face "mesh" type .dat file,vertex seems to use boneMtx that stored in itself file in some strange way.

As you can see I use 010 editor to analyse "00000000000000a2.dat" under folder "Avatars_Face". If you move the extracted mesh around 160 unit, the head vertex should be in the right position.
The problem is: I don't know boneParent in "mesh" type .dat file so that I can't link bones together.And I'm not sure which skeleton should I use,in "mesh" type .dat file or in "skeleton" type .dat file

Btw, what I implemented in v2 script is to compare whether all boneName in mesh file can be found in skeleton file.If so, I'm sure that the skeleton is belong to this mesh.
## Post #8
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2022-01-04T17:41:47+00:00
- Post Title: Ring of Elysium Noesis script

Could you explain the basic process of editing the .dat file within 010 editor, I am not familiar with using hex editors.

Thanks
## Post #9
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2022-01-05T04:12:01+00:00
- Post Title: Ring of Elysium Noesis script

> Reply from X3D ↑Wed Jan 05, 2022 1:41 am at Wed Jan 05, 2022 1:41 am
>
> 
Could you explain the basic process of editing the .dat file within 010 editor, I am not familiar with using hex editors.

Thanks

010 editor is not for "editing" .dat file,but analyse the file structure.

I have attached mesh(QSG) and skeleton(QSS) template in zip file.
to use it, you should do following steps:
1. open .dat file in 010 editor, just drag the file to 010 editor.
2. open .bt template file in 010 editor, just drag the file to 010 editor too, It should show a window which show the content of the template.
3.Around top right corner of the window, you should see a "run" button, click it to make the template run on the .dat file.
## Post #10
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2022-01-05T10:47:17+00:00
- Post Title: Ring of Elysium Noesis script

Thanks for the info PeterZ, concentrating on moving the bone position of the eyes, which should be the best guide for the whole root placement, I found [X 0.0][Y -1.0][Z -63.5] rotates the eyes properly. [the XYZ will differ depending on the software used]
## Post #11
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2022-01-08T14:13:29+00:00
- Post Title: Ring of Elysium Noesis script

001.jpg (25.81 KiB) Viewed 462 times



Components required for above character below, still need to find a backpack and textures for gloves and belt packs etc.
Mesh:
Avatars_Face: 0000000000000344.dat [Head]
Avatars_Skin_X_F_TY: 000000000000079b.dat [Hair]
Avatars_Skin_X_F_SJ: 00000000000000ab.dat [Hair-Alternative]
Avatars_Skin_X_F_TY: 00000000000006b7.dat [Coat]
Avatars_Skin_X_F_TY: 000000000000038f.dat [Top Coat]
Avatars_Skin_X_F_SJ: 0000000000000327.dat [Gloves]
Avatars_Skin_X_F_SJ: 0000000000000089.dat [Legs]
Avatars_Skin_X_F_SJ: 000000000000025e.dfont [Boots]

Textures:
Avatars_Face: 09f.dds
Avatars_Skin_X_F_TY: 17b.dds [HeadDeco]
Avatars_Skin_X_F_TY: 0a0.dds [Hair]
Avatars_Skin_X_F_TY: 32b.dds [Top Coat]
Avatars_Skin_X_F_TY: 42d.dds [Coat]
Avatars_Skin_X_F_TY: 00e.dds [Legs]
Avatars_Skin_X_F_SJ: 110.dds [Boots]

Revision: Corrections
Avatars_Face: 00000000000003ac.dat [Head]
Avatars_Face: 0000000000000447.dds

Can someone confirm that these files are corrupted?
Avatars_Skin_X_F_SJ
00000000000002b0.dat
000000000000087d.dat
0000000000000881.dfont
0000000000000886.dat
## Post #12
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2022-01-10T09:23:13+00:00
- Post Title: Ring of Elysium Noesis script

Compiling these models is a challenge but I do like them.



02.jpg (38.5 KiB) Viewed 441 times


Still searching for the glove texture 
Can somebody please confirm if the mesh list in the above post are corrupt? Thanks
## Post #13
- Username: ziliangya
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 29, 2023 11:21 pm
- Post datetime: 2023-03-11T16:51:36+00:00
- Post Title: Ring of Elysium Noesis script

Extraction succeeded. Thank you very much
## Post #14
- Username: LordRorsch
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 22, 2023 1:26 pm
- Post datetime: 2023-04-23T09:24:04+00:00
- Post Title: Ring of Elysium Noesis script

> Reply from X3D ↑Mon Jan 10, 2022 5:23 pm at Mon Jan 10, 2022 5:23 pm
>
> 
Compiling these models is a challenge but I do like them.
02.jpg
Still searching for the glove texture 
Can somebody please confirm if the mesh list in the above post are corrupt? Thanks
No, they are not corrupt. Those are just some insane hair styles.
## Post #15
- Username: cleorabraun
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 26, 2023 2:38 pm
- Post datetime: 2023-04-26T06:42:30+00:00
- Post Title: Ring of Elysium Noesis script

> Reply from X3D ↑Mon Jan 10, 2022 5:23 pm at Mon Jan 10, 2022 5:23 pm
>
> 
Compiling these models is a challenge but I do like them.
02.jpg
Still searching for the glove texture getting over it
Can somebody please confirm if the mesh list in the above post are corrupt? Thanks

I can still watch. They are still normal.
## Post #16
- Username: nhatvpo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jul 12, 2015 5:41 pm
- Post datetime: 2023-06-15T05:32:56+00:00
- Post Title: Re: Ring of Elysium Noesis script

Can we get it's animations?
