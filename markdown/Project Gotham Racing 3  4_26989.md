## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-19T12:16:35+00:00
- Post Title: Project Gotham Racing 3 / 4

Tool for PGR3 & PGR4 cars

Drag .pak_hrd onto the tool or use command line.

Tool will export all textures to a subfolder in raw format, which then can be converted with included noesis plugin.
Tool will also make a text file with a list of all materials with all textures they use.

Tool for PGR4 areas

Tool will export all static models and all instanced models to .DMF format.
To load .DMF files use this blender plugin: [https://github.com/REDxEYE/decima-dmf](https://github.com/REDxEYE/decima-dmf)

Tool will export all textures to a subfolder in raw format, which then can be converted with included noesis plugin.
Tool will also make a text file with a list of all materials with all textures they use.

notes:
- to decompress .stream2 files tool needs xcompress64.dll from xbox sdk (not included)
- last UV pair (used for lightmaps) not exported.
- vertex colors not exported.








[gothamRacing.7z](https://xentaxbackup.github.io/file/24191_gothamRacing.7z)
## Post #2
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-20T02:45:47+00:00
- Post Title: Project Gotham Racing 3 / 4

nice. can't wait to use it.
## Post #3
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-20T04:46:26+00:00
- Post Title: Project Gotham Racing 3 / 4

> Reply from daemon1 ↑Wed Jul 19, 2023 8:16 pm at Wed Jul 19, 2023 8:16 pm
>
> 
Project Gotham Racing 3 & 4

Tool to get cars and maps will be posted here.
btw is DLC cars/maps supported? cuz these two games have some of them
## Post #4
- Username: WF4123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 10, 2023 1:04 am
- Post datetime: 2023-07-20T06:10:44+00:00
- Post Title: Project Gotham Racing 3 / 4

> Reply from UB833 ↑Thu Jul 20, 2023 12:46 pm at Thu Jul 20, 2023 12:46 pm
>
> 
daemon1 wrote: ↑Wed Jul 19, 2023 8:16 pm
Project Gotham Racing 3 & 4

Tool to get cars and maps will be posted here.









btw is DLC cars/maps supported? cuz these two games have some of them

Yes probably. For example this VW I saw on Sketchfab.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-20T07:07:28+00:00
- Post Title: Project Gotham Racing 3 / 4

Posted the test tool for CARS only.

Textures not extracted yet, and custom scale is not applied for PRG4 cars.
Also there's some leftover loose geometry, because of how data was organized in buffers.
But all of them must export with all UVs and vertex colors.
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-07-20T15:59:33+00:00
- Post Title: Project Gotham Racing 3 / 4

Appreciate for the tool, currently testing and have a question. Is it possible to detect meshes in damaged state and mark them somehow? For example, put _DAMAGE_ in front of the mesh name?


edit: also. All the cars in pgr3 and pgr4 after converting to ascii are mirrored by X axis.

edit2: it would be really nice if you could look into these files of 2 games:
blur, pc: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/104fi5XEctUbF-FhGhq0b6I2gcArWXqlp?usp=sharing)
blur 2, xbox360: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1cFQ_Xt2x7v9AbOWMfH8GWUF0S358B_G9?usp=sharing)
both game are done by the same developer and I assume the model storage technique might be similar. While the Blur has a lot of high detailed cars and problems with ripping, the Blur 2 was never released - I found its build on one of the archive sites for things like this.
## Post #7
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-20T16:25:17+00:00
- Post Title: Project Gotham Racing 3 / 4

how do I import converted .ascii file format used with your test tool to 3d program? and do I need 3ds max or blender to import it? I just wanted to test it that's all
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-07-20T16:37:14+00:00
- Post Title: Project Gotham Racing 3 / 4

Would it be also possible to convert characters with skeletons from pgr4?
There's a lot, for different countries and for different types of vehicles.

I've placed all of them here: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1chzYqEouO8qMP1TFhjfSPAEmvz_kmJUP?usp=sharing)
## Post #9
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-07-20T18:59:09+00:00
- Post Title: Project Gotham Racing 3 / 4

@UBE33 and @WF4123 please go back to your posts and edit them, you both quoted the whole think making a mess, try to keep things well organized.

> Reply from Tosyk ↑Thu Jul 20, 2023 11:59 pm at Thu Jul 20, 2023 11:59 pm
>
> ...edit: also. All the cars in pgr3 and pgr4 after converting to ascii are mirrored by X axis...
The devs that made these games are from UK the cars are driven from the right side, as far as i know they are not mirrored.
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-07-20T20:15:50+00:00
- Post Title: Project Gotham Racing 3 / 4

> Reply from mono24 ↑Fri Jul 21, 2023 2:59 am at Fri Jul 21, 2023 2:59 am
>
> 
Tosyk wrote: ↑Thu Jul 20, 2023 11:59 pm...edit: also. All the cars in pgr3 and pgr4 after converting to ascii are mirrored by X axis...
The devs that made these games are from UK the cars are driven from the right side, as far as i know they are not mirrored.
They are mirrored. I know this for sure.
## Post #11
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-07-20T21:19:07+00:00
- Post Title: Project Gotham Racing 3 / 4

> Reply from Tosyk ↑Fri Jul 21, 2023 4:15 am at Fri Jul 21, 2023 4:15 am
>
> They are mirrored. I know this for sure.
That was my very first initial thought after testing the tool, i personally never played them at the time, but if you did play them and can confirm they are mirrored then that's that.
## Post #12
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-21T02:56:24+00:00
- Post Title: Project Gotham Racing 3 / 4

I ask again, how do I import this .ascii file onto any 3d viewer? is there any dedicated plugin I have to use or is needed to convert to readable obj file?
[sd.png](https://xentaxbackup.github.io/file/24088_sd.png)
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-21T05:31:43+00:00
- Post Title: Project Gotham Racing 3 / 4

> Reply from UB833 ↑Fri Jul 21, 2023 10:56 am at Fri Jul 21, 2023 10:56 am
>
> 
I ask again, how do I import this .ascii file onto any 3d viewer?
There are several plugins for blender (example: xps tools by johnzero), and also a noesis plugin from where you can convert to many other formats.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-21T05:33:00+00:00
- Post Title: Project Gotham Racing 3 / 4

> Reply from Tosyk ↑Thu Jul 20, 2023 11:59 pm at Thu Jul 20, 2023 11:59 pm
>
> 
edit2: it would be really nice if you could look into these files of 2 games:
blur, 
blur 2, 
both game are done by the same developer and I assume the model storage technique might be similar.
I checked the files, and unfortunately, they have nothing in common with PGR games.
## Post #15
- Username: sam mods
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 07, 2021 2:05 pm
- Post datetime: 2023-07-21T07:35:31+00:00
- Post Title: Project Gotham Racing 3 / 4

Bye any chance will you try Driveclub?
## Post #16
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-21T07:37:25+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

> Reply from daemon1 ↑Fri Jul 21, 2023 1:31 pm at Fri Jul 21, 2023 1:31 pm
>
> 
UB833 wrote: ↑Fri Jul 21, 2023 10:56 am
I ask again, how do I import this .ascii file onto any 3d viewer?

There are several plugins for blender (example: xps tools by johnzero), and also a noesis plugin from where you can convert to many other formats.

thnk you so much for that. I'm using Blender 3.6.0 and this plugin worked like a charm.

> Reply from mono24 ↑Fri Jul 21, 2023 5:19 am at Fri Jul 21, 2023 5:19 am
>
> 
Tosyk wrote: ↑Fri Jul 21, 2023 4:15 amThey are mirrored. I know this for sure.

That was my very first initial thought after testing the tool, i personally never played them at the time, but if you did play them and can confirm they are mirrored then that's that.

Tosyk is right btw, the model itself is indeed mirrored. it's not intended to be like that irl and in-game.
[Screenshot 2023-07-21 133034.jpg](https://xentaxbackup.github.io/file/24089_Screenshot 2023-07-21 133034.jpg)
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-21T08:24:32+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

> Reply from sam mods ↑Fri Jul 21, 2023 3:35 pm at Fri Jul 21, 2023 3:35 pm
>
> 
Bye any chance will you try Driveclub?
Maybe later, some day.
## Post #18
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-21T09:11:59+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

By any chance to scale like this size in default zoom view? I just imported a dummy model. ignore the rotation btw.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-22T07:01:10+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

All map objects are done. A bit of a mess, because all track versions present at the same time.
Now proceeding with textures.
## Post #20
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-24T07:11:25+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

> Reply from daemon1 ↑Thu Jul 20, 2023 3:07 pm at Thu Jul 20, 2023 3:07 pm
>
> 
Also there's some leftover loose geometry, because of how data was organized in buffers.
But all of them must export with all UVs and vertex colors.

I guess some of the leftover mesh geometry are used in the game, especially for the headlight/brakelight emission shading when in night time racing.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-24T15:39:53+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

Textures exported, materials assigned to scene.
So far, its possible to manually apply textures after that.



Next i maybe try auto-assigning them.
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-07-24T15:54:49+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

> Reply from daemon1 ↑Mon Jul 24, 2023 11:39 pm at Mon Jul 24, 2023 11:39 pm
>
> 
Textures exported, materials assigned to scene.
So far, its possible to manually apply textures after that.

img

Next i maybe try auto-assigning them.have you updated the tool yet to test it?
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-25T12:23:40+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

Tool for PGR4 areas for testing.

Tool will export all static models and all instanced models to .DMF format.
To load .DMF files use this blender plugin: [https://github.com/REDxEYE/decima-dmf](https://github.com/REDxEYE/decima-dmf)

Tool will export all textures to a subfolder in raw format, which then can be converted with included noesis plugin.
Tool will also make a text file with a list of all materials with all textures they use.

notes:
- to decompress .stream2 files tool needs xcompress64.dll from xbox sdk (not included)
- UV2/UV3 not exported. Usually used for lightmaps.
- vertex colors not exported.

edit: tool moved to 1st post
## Post #24
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-27T04:26:38+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

any update on your tool about Car textures?
## Post #25
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-31T10:08:18+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

is it just me or that xna plugin messes up the material of every car after I saved the blender scene or exported to obj? uv itself is okay btw but material, how is that?
## Post #26
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-31T10:15:01+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

also for noesis xna plugin, it gives me an error:
## Post #27
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-07-31T10:49:28+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

> Reply from UB833 ↑Mon Jul 31, 2023 6:08 pm at Mon Jul 31, 2023 6:08 pm
>
> 
is it just me or that xna plugin messes up the material of every car after I saved the blender scene or exported to obj? uv itself is okay btw but material, how is that?

img
where did you get the textures? I would love to check it myself. But as I understand, there is no way to get textures, right?
## Post #28
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-31T11:09:21+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

> Reply from Tosyk ↑Mon Jul 31, 2023 6:49 pm at Mon Jul 31, 2023 6:49 pm
>
> 
UB833 wrote: ↑Mon Jul 31, 2023 6:08 pm
is it just me or that xna plugin messes up the material of every car after I saved the blender scene or exported to obj? uv itself is okay btw but material, how is that?

img

where did you get the textures? I would love to check it myself. But as I understand, there is no way to get textures, right?
well I got the textures from sketchfab website: [https://sketchfab.com/3d-models/ruf-r50 ... cae68b5b31](https://sketchfab.com/3d-models/ruf-r50-fa09a71eef1a40388e7423cae68b5b31)

EDIT: yea, that's the only way I got the textures from since daemon haven't gotten us any update.
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-08-02T13:35:51+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

> Reply from UB833 ↑Thu Jul 27, 2023 12:26 pm at Thu Jul 27, 2023 12:26 pm
>
> 
any update on your tool about Car textures?
I dont have time for it right now.
## Post #30
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-08-02T14:33:02+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

> Reply from daemon1 ↑Wed Aug 02, 2023 9:35 pm at Wed Aug 02, 2023 9:35 pm
>
> 
UB833 wrote: ↑Thu Jul 27, 2023 12:26 pm
any update on your tool about Car textures?

I dont have time for it right now.

ok, take your time dw
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-08-06T11:47:14+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

Both tools updated. Check 1st post.

Cars tool:
- texture export
- material list
- scale fixed

Maps tool:
- workaround fix for textures with reversed mipmaps 
(they are now exported in full size, but you need to manually cut the biggest mip)
- more UV pairs added
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-08-06T17:01:33+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

Another small fix.

Only cars tool. Now cars must have proper size. Both PGR3 & 4.
## Post #33
- Username: DarkMrag
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 24, 2023 11:46 pm
- Post datetime: 2023-08-24T15:58:45+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

Оh! Someone got to "sawing" PGR in comfortable mode without emulator: thank you very much! There was a question: is Project Gotham Racing 2 supported along with its younger brethren (or maybe it will be supported in the future)? 
For years I have been trying to extract models of one of the locations in the second game (from video memory), but failed miserably.
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-08-25T16:24:26+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

> Reply from DarkMrag ↑Thu Aug 24, 2023 11:58 pm at Thu Aug 24, 2023 11:58 pm
>
> 
is Project Gotham Racing 2 supported along with its younger brethren (or maybe it will be supported in the future)?
no, i dont have plans for this
## Post #35
- Username: apartverendos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 17, 2023 8:20 pm
- Post datetime: 2023-10-17T12:23:00+00:00
- Post Title: Re: Project Gotham Racing 3 / 4

These tools and instructions are intended for modders, researchers and enthusiasts who wish to modify or analyze objects from PGR3 and PGR4. Keep in mind that the use of such modding tools is not always officially supported and may violate the terms of service of the respective games or platforms. Have you already opted for a driver's license with [scannable fake id](https://fairyid.com/) and how fast did it work out for you? I need a driver's license immediately too. Always use caution and make sure you have the necessary rights to use such tools to handle game assets.
