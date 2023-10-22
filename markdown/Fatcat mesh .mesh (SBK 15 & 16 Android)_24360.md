## Post #1
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-15T12:17:42+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

Hi, i'm trying to open SBK 16 android's .mesh files, when i opened the file in hex editor it shows "fatcat mesh 1.0", im looking if someone could convert this to other format, or maybe even convert other format to this format

 ducati_lod0.rar
3d model sample (47.26 KiB) Downloaded 14 times
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-15T13:15:17+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

Well, ASCII plaintext format... Would be a pain to deal with.

Pure text editing though(largest mesh):



chassis.jpg (152.46 KiB) Viewed 100 times
## Post #3
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-15T13:43:34+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Bigchillghost ↑Sun Aug 15, 2021 9:15 pm at Sun Aug 15, 2021 9:15 pm
>
> 
Well, ASCII plaintext format... Would be a pain to deal with.

Pure text editing though(largest mesh):
chassis.jpg
Thanks for doing this, and also I know it's complicated but would you mind making a tool that can convert other 3d format to this format (only one other format to this one)? Or if you won't I also have one more 3d model from other game that I'm excited to know about
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-08-15T14:51:51+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Ya begitulah ↑Sun Aug 15, 2021 8:17 pm at Sun Aug 15, 2021 8:17 pm
>
> 
Hi, i'm trying to open SBK 16 android's .mesh files, when i opened the file in hex editor it shows "fatcat mesh 1.0", im looking if someone could convert this to other format, or maybe even convert other format to this formatducati_lod0.rar

I have download the
sbk15-official-mobile-game-1-5-2.apk
it.dtales.sbk16-1.4.2.apk

files, but I don't know which (archive) file contain the .mesh files.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-15T15:24:55+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Ya begitulah ↑Sun Aug 15, 2021 9:43 pm at Sun Aug 15, 2021 9:43 pm
>
> 
...and also I know it's complicated but would you mind making a tool that can convert other 3d format to this format (only one other format to this one)?
What for? I wouldn't say it's complicated since the layout is pretty straight forward except that you'll need to calculate the BBox for each submesh and the entire mesh, plus a little more research on the layout of the material file. But normally I'm not interested in converting anything back to the original format. Maybe someone else would like an attempt on that.
## Post #6
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-16T01:47:56+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Karpati ↑Sun Aug 15, 2021 10:51 pm at Sun Aug 15, 2021 10:51 pm
>
> 
Ya begitulah wrote: ↑Sun Aug 15, 2021 8:17 pm
Hi, i'm trying to open SBK 16 android's .mesh files, when i opened the file in hex editor it shows "fatcat mesh 1.0", im looking if someone could convert this to other format, or maybe even convert other format to this formatducati_lod0.rar


I have download the
sbk15-official-mobile-game-1-5-2.apk
it.dtales.sbk16-1.4.2.apk

files, but I don't know which (archive) file contain the .mesh files. it's in the obb
## Post #7
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-16T02:03:27+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Bigchillghost ↑Sun Aug 15, 2021 11:24 pm at Sun Aug 15, 2021 11:24 pm
>
> 
Ya begitulah wrote: ↑Sun Aug 15, 2021 9:43 pm
...and also I know it's complicated but would you mind making a tool that can convert other 3d format to this format (only one other format to this one)? 

What for? I wouldn't say it's complicated since the layout is pretty straight forward except that you'll need to calculate the BBox for each submesh and the entire mesh, plus a little more research on the layout of the material file. But normally I'm not interested in converting anything back to the original format. Maybe someone else would like an attempt on that. I'm making MotoGP 21 mod for this game, and looking if I can make it more realistic by changing the bike 3d model with the ones from the official game which can already converted to .obj and .dff, I'll also attach a material sample by the way


 display_background.rar
Material sample (415 Bytes) Downloaded 13 times
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-08-16T05:51:58+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Ya begitulah ↑Mon Aug 16, 2021 9:47 am at Mon Aug 16, 2021 9:47 am
>
> 
it's in the obb

Thank you for you information, but the .apk files I have downloaded have not .obb files.

Could you send me a download link to your .apk file(s)?
## Post #9
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-16T06:01:00+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Karpati ↑Mon Aug 16, 2021 1:51 pm at Mon Aug 16, 2021 1:51 pm
>
> 
Ya begitulah wrote: ↑Mon Aug 16, 2021 9:47 am
it's in the obb


Thank you for you information, but the .apk files I have downloaded have not .obb files.

Could you send me a download link to your .apk file(s)?
Did you download the game from Google play? If yes you've also downloaded the OBB, it's located in internal storage/Android/obb/it.dtales.sbk16, there you'll find a .OBB file, to open it you must rename it to .zip first
## Post #10
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-16T06:03:42+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Karpati ↑Mon Aug 16, 2021 1:51 pm at Mon Aug 16, 2021 1:51 pm
>
> 
Ya begitulah wrote: ↑Mon Aug 16, 2021 9:47 am
it's in the obb


Thank you for you information, but the .apk files I have downloaded have not .obb files.

Could you send me a download link to your .apk file(s)?
The .apk and .OBB are separate, here's a link to download the OBB file: [https://s3.rexdl.com/android/game/SBK16 ... dl.com.zip](https://s3.rexdl.com/android/game/SBK16-Official-Mobile-Game-1.4.2-Adreno-www.ReXdl.com.zip)
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-16T14:05:57+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Ya begitulah ↑Mon Aug 16, 2021 10:03 am at Mon Aug 16, 2021 10:03 am
>
> 
I'm making MotoGP 21 mod for this game, and looking if I can make it more realistic by changing the bike 3d model with the ones from the official game which can already converted to .obj and .dff, I'll also attach a material sample by the way
Well, guess you'll have to edit the material file manually as there're shader related stuffs. Here's a simple Noesis exporter for this format:


 fmt_FatCatMeshExporter_mesh.zip
(1.23 KiB) Downloaded 16 times



You'll also need to edit the material file path for each submesh after export.
## Post #12
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-16T14:16:15+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Bigchillghost ↑Mon Aug 16, 2021 10:05 pm at Mon Aug 16, 2021 10:05 pm
>
> 
Ya begitulah wrote: ↑Mon Aug 16, 2021 10:03 am
I'm making MotoGP 21 mod for this game, and looking if I can make it more realistic by changing the bike 3d model with the ones from the official game which can already converted to .obj and .dff, I'll also attach a material sample by the way

Well, guess you'll have to edit the material file manually as there're shader related stuffs. Here's a simple Noesis exporter for this format:
fmt_FatCatMeshExporter_mesh.zip

You'll also need to edit the material file path for each submesh after export. wow, didn't expect this, thank you so much
## Post #13
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-16T14:21:56+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Bigchillghost ↑Mon Aug 16, 2021 10:05 pm at Mon Aug 16, 2021 10:05 pm
>
> 
Ya begitulah wrote: ↑Mon Aug 16, 2021 10:03 am
I'm making MotoGP 21 mod for this game, and looking if I can make it more realistic by changing the bike 3d model with the ones from the official game which can already converted to .obj and .dff, I'll also attach a material sample by the way

Well, guess you'll have to edit the material file manually as there're shader related stuffs. Here's a simple Noesis exporter for this format:
fmt_FatCatMeshExporter_mesh.zip

You'll also need to edit the material file path for each submesh after export. when I'm trying to export it says "the file type could not be determined" any fix for that?
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-16T14:36:47+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

You need to learn to edit your post to avoid double posting and embed quotes.

> Reply from Ya begitulah ↑Mon Aug 16, 2021 10:21 pm at Mon Aug 16, 2021 10:21 pm
>
> when I'm trying to export it says "the file type could not be determined" any fix for that?
You mean "import" I suppose?
## Post #15
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-16T14:51:15+00:00
- Post Title: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Bigchillghost ↑Mon Aug 16, 2021 10:36 pm at Mon Aug 16, 2021 10:36 pm
>
> 
You need to learn to edit your post to avoid double posting and embed quotes.
Ya begitulah wrote: ↑Mon Aug 16, 2021 10:21 pmwhen I'm trying to export it says "the file type could not be determined" any fix for that?

You mean "import" I suppose? sorry, when I try to import other error pops up, something about the file cannot be previewed, and when I click on export the could not be determined one pops up
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-16T15:00:54+00:00
- Post Title: Re: Fatcat mesh .mesh (SBK 15 & 16 Android)

What format did you try to import/export from? The script is mean to export from something supported by Noesis already.

Anyway here's the updated script with support for importing from the mesh format. The exported mesh would be identical to the imported one.


 fmt_FatCatMesh_mesh.zip
(1.87 KiB) Downloaded 20 times
## Post #17
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-17T00:34:42+00:00
- Post Title: Re: Fatcat mesh .mesh (SBK 15 & 16 Android)

> Reply from Bigchillghost ↑Mon Aug 16, 2021 11:00 pm at Mon Aug 16, 2021 11:00 pm
>
> 
What format did you try to import/export from? The script is mean to export from something supported by Noesis already.

Anyway here's the updated script with support for importing from the mesh format. The exported mesh would be identical to the imported one.
fmt_FatCatMesh_mesh.zip Thanks, I'll try it
Update: It works, but only for bike and cockpit meshes, this really help me making the bike textures, massive thanks   


Screenshot (190).png (181.48 KiB) Viewed 32 times
