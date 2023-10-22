## Post #1
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-26T21:29:18+00:00
- Post Title: Dune: Spice Wars (.pak)

Here is script for unpacking pak file from Dune: Spice Wars. It's not valid for re-import because there are checksums for every file (adler32).
Update: Though checksums are not validated against files, so it's possible to modify package without adjusting them ([proof](https://i.imgur.com/ttvYTmB.jpg)).

Also, files are using extensions of their sources instead of actual ones: png are dds of various types, fbx are hmd, and so on.



 dune_spice_wars_extract_v2.zip
(553 Bytes) Downloaded 28 times
## Post #2
- Username: ghostx2015
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 11, 2015 12:32 am
- Post datetime: 2022-04-27T06:34:46+00:00
- Post Title: Dune: Spice Wars (.pak)

What game engine model format is .hmd?
Is there a tool that can read the .hmd model?
## Post #3
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-27T11:10:01+00:00
- Post Title: Dune: Spice Wars (.pak)

@ghostx2015: The game is using Heaps engine, like for their previous games, Northgard and Wartales. Apparently native IDE for it ([hide](https://github.com/HeapsIO/hide)) works fine with renamed/converted sources, including animations. You need to convert textures though and some complex assets are not supported.




leto.jpg (145.87 KiB) Viewed 469 times
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-28T20:01:30+00:00
- Post Title: Dune: Spice Wars (.pak)

Here is script for repacking. You need to place modified file, script and archive in the same folder and run script on modified file - it will be appended to selected archive (can be specified in the script), if original file was there. Make sure to backup original archive and extracted files, as modified archive can't be extracted anymore (you can still add other modified files to it though). 
It may be updated in the future, since current script is built with workarounds due to quickbms limitations.

Alternatively you can use native build tool from the engine as explained [here](https://heaps.io/documentation/resource-management.html).

Update: Script is updated to handle all files, though currently modified data.cdb should smaller or equal to original file.



 dune_spice_wars_repack_v2.zip
(1.24 KiB) Downloaded 55 times
## Post #5
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2022-04-30T19:19:32+00:00
- Post Title: Dune: Spice Wars (.pak)

Try this - quick extractor with repack build to support Czech localization. I hope it will work fine 
[http://raptor-cestiny.cz/download/files ... tor100.zip](http://raptor-cestiny.cz/download/files/utils/DuneSpiceWarsExtractor100.zip)
## Post #6
- Username: Multicor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 28, 2022 9:18 am
- Post datetime: 2022-05-09T18:48:07+00:00
- Post Title: Dune: Spice Wars (.pak)

> Reply from XRaptor ↑Sun May 01, 2022 3:19 am at Sun May 01, 2022 3:19 am
>
> 
Try this - quick extractor with repack build to support Czech localization. I hope it will work fine 
http://raptor-cestiny.cz/download/files ... tor100.zip

Hi!

Thanks for the tool! 
This tool does not support importing the file "data.cdb". The game will not start after import. The "texts.xml" will work, but it only contains the user interface texts. Can you update the program or help me? 

Also, is there any way to not have to split the 2.8GB file after translation? 

Thank you.
## Post #7
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2022-05-12T19:36:16+00:00
- Post Title: Dune: Spice Wars (.pak)

> Reply from Multicor ↑Tue May 10, 2022 2:48 am at Tue May 10, 2022 2:48 am
>
> 
This tool does not support importing the file "data.cdb". The game will not start after import. The "texts.xml" will work, but it only contains the user interface texts. Can you update the program or help me? 

Also, is there any way to not have to split the 2.8GB file after translation?

Tool has nothing to do with game crash after editing files. It is just repacker. Maybe you just somehow damaged this file in editor.

Split file after translation? What do you mean? Repacker just creates a new file, because it is streaming original unedited files from original pak to new one.
## Post #8
- Username: dvxm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 02, 2022 3:46 pm
- Post datetime: 2022-09-02T07:56:38+00:00
- Post Title: Dune: Spice Wars (.pak)

Spiritovod, thanks for making this BMS file, I've just used it to unpack Dune's res.compressed.pak file
## Post #9
- Username: Pheen!x
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 10, 2022 10:00 pm
- Post datetime: 2022-10-10T15:25:52+00:00
- Post Title: Dune: Spice Wars (.pak)

> Reply from Spiritovod ↑Wed Apr 27, 2022 7:10 pm at Wed Apr 27, 2022 7:10 pm
>
> 
@ghostx2015: The game is using Heaps engine, like for their previous games, Northgard and Wartales. Apparently native IDE for it (hide) works fine with renamed/converted sources, including animations. You need to convert textures though and some complex assets are not supported.

Hello, 

just jumping in here, I am stuck at the stage when opening the files. 
I renamed all fbx-files into hmd-files, at least it looks like that is what you did. 

But then you are talking abouting "converted sources, including animations". 
Could you or anybody give me any pointers where I can look up conversion to open the Dune files?

Thanks.
## Post #10
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-10-10T23:01:29+00:00
- Post Title: Dune: Spice Wars (.pak)

@Pheen!x: You only need to convert extracted dds textures to actual png, then Hide can use them. It can be done with any tool supporting DXT/BC formats, like PVRTexTool (except for BC7). Though Hide can only preview models/animations, not export them or save in other formats.
## Post #11
- Username: Pheen!x
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 10, 2022 10:00 pm
- Post datetime: 2022-10-11T07:21:10+00:00
- Post Title: Dune: Spice Wars (.pak)

Great thank you. Bummer that they cannot be exported, I was hoping to be able to 3D print some of the models.
## Post #12
- Username: mihailgaravsyuk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 24, 2022 12:49 am
- Post datetime: 2022-10-24T08:33:17+00:00
- Post Title: Dune: Spice Wars (.pak)

> Reply from Spiritovod ↑Fri Apr 29, 2022 4:01 am at Fri Apr 29, 2022 4:01 am
>
> 
Here is script for repacking. You need to place modified file, script and archive in the same folder and run script on modified file - it will be appended to selected archive (can be specified in the script), if original file was there. Make sure to backup original archive and extracted files, as modified archive can't be extracted anymore (you can still add other modified files to it though). 
It may be updated in the future, since current script is built with workarounds due to quickbms limitations.

Alternatively you can use native build tool from the engine as explained here.

Update: Script is updated to handle all files, though currently modified data.cdb should smaller or equal to original file.


dune_spice_wars_repack_v2.zip

i have a problem.  I use quickbms_4gb_files.exe, because size res.compressed.pak file a 3.2Gb. But repacking not run:
[https://drive.google.com/file/d/1Vz--8Y ... sp=sharing](https://drive.google.com/file/d/1Vz--8Yr33Lwa48Fy82SXn5A0nyxgpPvJ/view?usp=sharing)

When i use quickbms.exe, in cmd writes that:
[https://drive.google.com/file/d/1K96go5 ... sp=sharing](https://drive.google.com/file/d/1K96go5pITdlOQuu7o1j1gDYpMJMEvT3k/view?usp=sharing)

how do i repackage the file?
## Post #13
- Username: Throneddarcy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 11, 2019 1:46 am
- Post datetime: 2023-07-03T14:15:57+00:00
- Post Title: Dune: Spice Wars (.pak)

Hello I'm new to extracting and that I've extracted the files but when I try to open/import the fbx I've had no luck was wondering if anyone could help me with this issue?
## Post #14
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-07-04T12:54:29+00:00
- Post Title: Dune: Spice Wars (.pak)

@Throneddarcy: Despite the extensions, those extracted files are actually hmd (proprietary models format for the engine) and common dds textures, not fbx and png. It was mentioned above. You can try to find some tools for converting this models format, though I couldn't back then.
## Post #15
- Username: sameidandpw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 29, 2020 8:27 pm
- Post datetime: 2023-09-22T12:09:36+00:00
- Post Title: Dune: Spice Wars (.pak)

Any chance you will update the extract script to work with the retail version? There seems to be a problem with the content of some of the extracted files. For example no text in the *.css files and json files starting in the middle of a tag.
## Post #16
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-09-24T01:35:56+00:00
- Post Title: Re: Dune: Spice Wars (.pak)

@sameidandpw: I couldn't reproduce any of the mentioned issues with latest steam version. Try to use 4gb_files version of quickbms, if you didn't yet, and make sure that package was not already modified. Aside from that there shouldn't be any problems, since package format is still the same.
## Post #17
- Username: sameidandpw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 29, 2020 8:27 pm
- Post datetime: 2023-09-25T21:53:02+00:00
- Post Title: Re: Dune: Spice Wars (.pak)

I used the dune_spice_wars_extract.bms file form the first post zip file with quickbms_4gb_files.exe (v0.12) on the res.compressed.pak (v1.0.2.28081) file of the game.

EDIT:
Comparing the difference between the extracted files from v1.0.2.28081 and v1.0.3.28195 the problem appears with or around the Environment\Texture\Ground\Rock\Ground_Ice_01_height.png file. You can use the UI\style.css, UI\style_cjk.css or any of the Vehicle\*\*\*.props files for examples of unsuccessfully extracted files.

The game files ware not modified before the attempt to extract them, if you have the v1.0.3.28195 files - can you share the res.compressed.pak file MD5/SHA1 checksum value?
## Post #18
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-09-26T00:45:24+00:00
- Post Title: Re: Dune: Spice Wars (.pak)

@sameidandpw: I just noticed that script in the first post was an old one with workaround - it would work with some previous quickbms versions, but not current one. The point is that some things were fixed in 0.12, so workaround is not required (and moreover, it got broken) - I probably updated it at zenhax when quickbms received required fix, but not here. Script in the first post is now updated, it should work like expected with latest 4gb_files quickbms.
## Post #19
- Username: Acid
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 26, 2011 7:31 pm
- Post datetime: 2023-10-07T19:08:29+00:00
- Post Title: Re: Dune: Spice Wars (.pak)

Can anyone confirm that the repack script does work?

Im not able to reimport/repack. The game has been patched a few times since these scripts were made. Im assuming they would need to be updated to the current version. If thats the case, im not requesting anything be updated.  As many times as the game gets patched, it would just be a pain.

@XRator
Your extractor program does seem to work to extract but when repacking, its creating the repacked file a little smaller than the original the files were extracted from. If you can, any help would be appreciated.

Extracted vanila file from version 1.0.3.28390: 4.55 GB (4,890,402,816 bytes)
Repacked unmodified file: 4.53 GB (4,872,052,736 bytes)
## Post #20
- Username: DarkEmblem
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 07, 2021 10:35 pm
- Post datetime: 2023-10-14T17:49:48+00:00
- Post Title: Re: Dune: Spice Wars (.pak)

Has anyone been able to properly export the 3D models?
