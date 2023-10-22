## Post #1
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2019-01-11T23:53:31+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

```
https://store.steampowered.com/app/961440/RESIDENT_EVIL_2__BIOHAZARD_RE2_1Shot_Demo/
```


The demo for RE2make is available. All its assets on contained in a single 8 gig PAK file. I've tried the RE7 and latest SFV PAK unpackers but they're incompatible.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-01-12T01:36:00+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

The same format as in RE7, just they added new flag for ZSTD compression. Currently the list of file names is actually empty.
[re2_pak_unpack_r1.rar](https://xentaxbackup.github.io/file/15447_re2_pak_unpack_r1.rar)
## Post #3
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2019-01-12T03:16:58+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

> Reply from Ekey
>
> The same format as in RE7, just they added new flag for ZSTD compression. Currently the list of file names is actually empty.
Any Chance of a Compatible Hook DLL being released so we can generate the file list?
## Post #4
- Username: ISKA
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 4:52 pm
- Post datetime: 2019-01-12T08:42:50+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

> Reply from Ekey
>
> The same format as in RE7, just they added new flag for ZSTD compression. Currently the list of file names is actually empty.
Thanks.
## Post #5
- Username: PRP1986
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Mar 26, 2018 1:18 am
- Post datetime: 2019-01-12T14:14:38+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

The unpacker works great - thanks.

I apologise if this is a stupid question, but how would I go about viewing the models/textures?
## Post #6
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2019-01-13T03:37:00+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

> Reply from PRP1986
>
> The unpacker works great - thanks.

I apologise if this is a stupid question, but how would I go about viewing the models/textures?

I don't know if steven gas machine tool can help you. it's the only tool that I know capable of extracting RE7 models and this demo uses the same engine.

[http://xnalara.org/viewtopic.php?f=17&t=1001&start=690](http://xnalara.org/viewtopic.php?f=17&t=1001&start=690)
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-13T09:43:40+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

You can make small changes to SGM to make it work with RE2. There are couple changes in file header, and buffers header. Vertex buffers are structured differently than RE7, so need to investigate what types there are.  At least the skeleton and mesh info are identical to RE7, so SGM does some of the heavy lifting already.

Here is Leon's body for example. I haven't got the time to really check the vertex buffer structure, so no weights atm.
## Post #8
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2019-01-13T10:35:27+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

> Reply from akderebur
>
> You can make small changes to SGM to make it work with RE2. There are couple changes in file header, and buffers header. Vertex buffers are structured differently than RE7, so need to investigate what types there are.  At least the skeleton and mesh info are identical to RE7, so SGM does some of the heavy lifting already.

Here is Leon's body for example. I haven't got the time to really check the vertex buffer structure, so no weights atm.
Nice work! This is great progress! Hopefully you share more soon
## Post #9
- Username: TTR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 28, 2011 4:14 am
- Post datetime: 2019-01-13T20:19:37+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

Ah, so right now we only have unskinned skeletal meshes but no environment static meshes?
## Post #10
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-13T21:29:56+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

> Reply from akderebur
>
> You can make small changes to SGM to make it work with RE2. There are couple changes in file header, and buffers header. Vertex buffers are structured differently than RE7, so need to investigate what types there are.  At least the skeleton and mesh info are identical to RE7, so SGM does some of the heavy lifting already.

Here is Leon's body for example. I haven't got the time to really check the vertex buffer structure, so no weights atm.

Thank you for having a look at this mate! 

I would be fine with just exporting/importing meshes and textures. I'm only curious about polycount, texture density, how they re-surfaced the sculpts and scan heads, etc. I know a lot of it comes from their engine (the polished good look of the game) but I still want to have a look at stuff like that.

You mention changing the file header and buffer header. May I ask what you changed in the SGM to open up the character? Because when I use the Re7 game and choose the pak location it just closes after the questions.
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-13T23:11:52+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

> Reply from completenoob
>
> 
May I ask what you changed in the SGM to open up the character?
It is an open source program, so I changed the RE7 module to work with RE2.

> Reply from TTR
>
> no environment static meshes?
I am not really interested in environment stuff, but couple ones I have seen were loading fine.

I got weights/uvs working quickly, but haven't tried lots of files as I just want main chars.
## Post #12
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-13T23:31:23+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

> Reply from akderebur
>
> completenoob wrote:
May I ask what you changed in the SGM to open up the character?
It is an open source program, so I changed the RE7 module to work with RE2.
TTR wrote:no environment static meshes?
I am not really interested in environment stuff, but couple ones I have seen were loading fine.

I got weights/uvs working quickly, but haven't tried lots of files as I just want main chars.

Pretty neat work! Main characters is actually my main interest as well.. Could I ask you if maybe you could share the changes you did to the SGM so that I could import/export the models from the demo to have a look at them?
## Post #13
- Username: Nemesisbg23
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 14, 2019 8:07 am
- Post datetime: 2019-01-14T01:15:26+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

> Reply from akderebur
>
> completenoob wrote:
May I ask what you changed in the SGM to open up the character?
It is an open source program, so I changed the RE7 module to work with RE2.
TTR wrote:no environment static meshes?
I am not really interested in environment stuff, but couple ones I have seen were loading fine.

I got weights/uvs working quickly, but haven't tried lots of files as I just want main chars.

https://i.imgur.com/2jysuCy.png
WOOOOW nice job mate love it can we also get that so we can look around the files id love to find more stuff :3
## Post #14
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-14T02:12:10+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

I just patched it quickly to load Leon properly. It still uses some hardcoded stuff and not suitable for general use. Also not all vertex types are supported. I have no plans to polish it and release it, since it is not my tool anyway.

Wait for semory to release a proper RE2 support. I don't think it will take too long.
## Post #15
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2019-01-14T10:09:39+00:00
- Post Title: Resident Evil 2 Remake - demo PAK file

No Claire/Ada models are stored in demo files?
## Post #16
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-14T10:36:44+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from akderebur
>
> I just patched it quickly to load Leon properly. It still uses some hardcoded stuff and not suitable for general use. Also not all vertex types are supported. I have no plans to polish it and release it, since it is not my tool anyway.

Wait for semory to release a proper RE2 support. I don't think it will take too long.

Thank you.
## Post #17
- Username: ReginA
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 12, 2019 3:14 am
- Post datetime: 2019-01-14T11:04:51+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I extracted audio files. It's riff wave format in the code and I couldn't convert it with all vgm stuff i know. Any suggestions? Music wav files in the .pak files after extraction of main demo .pak file.
## Post #18
- Username: Anthony7888
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 15, 2019 6:51 pm
- Post datetime: 2019-01-15T10:57:40+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hello you can give me a link to download the tool for Resident Evil 2 Remake
## Post #19
- Username: benishandler
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jun 25, 2018 5:41 am
- Post datetime: 2019-01-16T03:00:29+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from ReginA
>
> I extracted audio files. It's riff wave format in the code and I couldn't convert it with all vgm stuff i know. Any suggestions? Music wav files in the .pak files after extraction of main demo .pak file.

How did you get those .pak files to extract? It just fails for me with both the RE7 and RE2 Remake bms scripts.
## Post #20
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-16T05:34:43+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from benishandler
>
> ReginA wrote:I extracted audio files. It's riff wave format in the code and I couldn't convert it with all vgm stuff i know. Any suggestions? Music wav files in the .pak files after extraction of main demo .pak file.

How did you get those .pak files to extract? It just fails for me with both the RE7 and RE2 Remake bms scripts.
RE7 script is useless, you have to use  to use the Ekey  re2_pak_unpack_r1 posted in previous page 
Did you used the last "quickbms_4gb_files.exe"?
## Post #21
- Username: GlemyToto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 24, 2017 10:06 pm
- Post datetime: 2019-01-16T08:19:56+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> It just fails for me with both the RE7 and RE2 Remake bms scripts.
If it fails with the RE2 script, update your quickbms version.
## Post #22
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-16T10:05:07+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Don't bother extracting the files. Unless you've figured out a way to view the data like the gentleman above who doesn't give two cents about explaining how he patched (or sharing his patched) SGM, then there's no point in extracting because you won't be able to view the files.
## Post #23
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2019-01-16T10:07:26+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from akderebur
>
> I just patched it quickly to load Leon properly. It still uses some hardcoded stuff and not suitable for general use. Also not all vertex types are supported. I have no plans to polish it and release it, since it is not my tool anyway.

Wait for semory to release a proper RE2 support. I don't think it will take too long.

You can do whatever you want with the program my good man, I don't mind at all. You can even change the name on it if you want LMAO. I just can't look at games now or in the near future as my mind is lost elsewhere.
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-16T10:37:34+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from howfie
>
> 
You can do whatever you want with the program my good man, I don't mind at all. You can even change the name on it if you want LMAO. I just can't look at games now or in the near future as my mind is lost elsewhere.
I have seen your xnalara post. Sorry to hear that you are having a hard time. I hope everything gets sorted out soon.

In that case I will do some tests on different models, and release the modified program.
## Post #25
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-01-16T12:05:05+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Here's "alpha" maxscript and Noesis plugin for RE2 R, if anyone want to test it out. Skinned meshes should work, static partially xD Don't have a lot of samples. It's for those of you who prefer using 3ds max instead of something else  
[RE2_R.7z](https://xentaxbackup.github.io/file/15490_RE2_R.7z)
## Post #26
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2019-01-16T12:10:40+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Nice zaramot, you still extracting models? You're a robot!
## Post #27
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-01-16T12:14:02+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from howfie
>
> Nice zaramot, you still extracting models? You're a robot!

I'm an idiot aha ha ha! Nice to see you Steven
## Post #28
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2019-01-16T14:52:56+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Does someone know where the models are stored??, I have checked the streaming folders but there's only textures there.

Edit: 

Nevermind, I already found the models.
## Post #29
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-16T15:21:07+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot
>
> Here's "alpha" maxscript and Noesis plugin for RE2 R, if anyone want to test it out. Skinned meshes should work, static partially xD Don't have a lot of samples. It's for those of you who prefer using 3ds max instead of something else

Thank you for script mate, really nice!

> Reply from Darko
>
> Does someone know where the models are stored??, I have checked the streaming folders but there's only textures there.

I used the Quickbms script to unpack the Pak file and then use the script from zaramot to import the mes files the script extracted.

[https://imgur.com/a/VcdIW29](https://imgur.com/a/VcdIW29)

I've selected all of them and put them on a separate folder just for convenience sake. I am yet to find the characters because there's a lot here. Police station main hall is 00000000000021e8.mes

[https://imgur.com/a/Lc5mXbT](https://imgur.com/a/Lc5mXbT)

Dam that's some really nice optimization and low poly. They did a tremendous great job on textures and PBR fine tuning. Can't wait to find the characters. Texture wise, I can't get it to read them in noesis.
## Post #30
- Username: Nyotengu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jul 29, 2014 11:05 am
- Post datetime: 2019-01-16T15:29:43+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I've unpacked everything with the quickbms script but I don't see any .10 files for the noesis plugin to read? Is there a trick to this? lol
## Post #31
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-01-16T15:34:40+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I think, it all depends on the extractor you used lol maybe you will have different extension. In that case you will have to rename it, or tell me the extensions you have, so I could just edit few lines and you are good to go xD There's a tool on zenhax, which have names, at least part of them. I think, person which provided me samples used this one ? I may ask if you want. 
[https://zenhax.com/viewtopic.php?f=9&t=9253](https://zenhax.com/viewtopic.php?f=9&t=9253)
## Post #32
- Username: Nyotengu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jul 29, 2014 11:05 am
- Post datetime: 2019-01-16T15:40:39+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot
>
> I think, it all depends on the extractor you used lol maybe you will have different extension. In that case you will have to rename it, or tell me the extensions you have, so I could just edit few lines and you are good to go xD There's a tool on zenhax, which have names, at least part of them. I think, person which provided me samples used this one ? I may ask if you want. 
https://zenhax.com/viewtopic.php?f=9&t=9253

oh ok i just used the bms script in this thread first page. lol ill check the zenhax one.  thanks
## Post #33
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-16T15:56:10+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Here is the modıfıed SGM and smc import script : [https://www.mediafire.com/file/t0vbm9f1 ... 2.rar/file](https://www.mediafire.com/file/t0vbm9f1u7bgub3/SGM_RE2.rar/file)

It only has RE2 in the game list, also I have disabled obj export since it takes lot of time. It exports smc, which you can import into Blender with the provided script. Only tested on Blender 2.49. All of the LODs will be exported. Ones starting with "s_00" are the best quality ones, delete the rest if you want. Textures are exported too, as dds.

The program worked fine with couple of files I have tested, let me know if you see any problems. Just nothing related to Blender import/export.
## Post #34
- Username: Nyotengu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jul 29, 2014 11:05 am
- Post datetime: 2019-01-16T16:16:36+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from akderebur
>
> Here is the modıfıed SGM and smc import script : https://www.mediafire.com/file/t0vbm9f1 ... 2.rar/file

It only has RE2 in the game list, also I have disabled obj export since it takes lot of time. It exports smc, which you can import into Blender with the provided script. Only tested on Blender 2.49. All of the LODs will be exported. Ones starting with "s_00" are the best quality ones, delete the rest if you want. Textures are exported too, as dds.

The program worked fine with couple of files I have tested, let me know if you see any problems. Just nothing related to Blender import/export.

I tried it and the application just closed after selecting yes to the options?
## Post #35
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-16T16:19:25+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Nyotengu
>
> 
I tried it and the application just closed after selecting yes to the options?
What files do you have in the selected folder? Make sure your extensions matches what the program is looking for.
## Post #36
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-16T16:25:46+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Same here. Opens and closes straight away after the questions. Inside the folder is the re_chunk_000.pak file. It creates a folder after it closes with the same name and a single file inside with 0 file size.
[https://imgur.com/a/DEv6W7Q](https://imgur.com/a/DEv6W7Q)
## Post #37
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-16T16:31:14+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from completenoob
>
> Inside the folder is the re_chunk_000.pak file.
Oh don't use it for unpacking the archive. Just unpack it using the bms script and also get the filelist from the thread zaramot linked. Extracted files will have proper file names that way.

After that you would point it to "natives/x64/sectionroot/character/player/pl0000/pl0000" for example and it would extract all meshes/textures for Leon's body. I should have removed .pak option to avoid confusion but anyway.
## Post #38
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-16T16:37:35+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Thank you! Testing now.
## Post #39
- Username: benishandler
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jun 25, 2018 5:41 am
- Post datetime: 2019-01-16T17:05:40+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from fil1969
>
> benishandler wrote:ReginA wrote:I extracted audio files. It's riff wave format in the code and I couldn't convert it with all vgm stuff i know. Any suggestions? Music wav files in the .pak files after extraction of main demo .pak file.

How did you get those .pak files to extract? It just fails for me with both the RE7 and RE2 Remake bms scripts.
RE7 script is useless, you have to use  to use the Ekey  re2_pak_unpack_r1 posted in previous page 
Did you used the last "quickbms_4gb_files.exe"?

I meant the .pak files which are inside the big, "outer" .pak file, but those are something completely different, as it turns out. They are Wwise .pck files. I managed to extract them and convert the sounds to .ogg using this: [https://github.com/Vextil/Wwise-Unpacker](https://github.com/Vextil/Wwise-Unpacker)
## Post #40
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-16T17:40:37+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from akderebur
>
> completenoob wrote:Inside the folder is the re_chunk_000.pak file.
Oh don't use it for unpacking the archive. Just unpack it using the bms script and also get the filelist from the thread zaramot linked. Extracted files will have proper file names that way.

After that you would point it to "natives/x64/sectionroot/character/player/pl0000/pl0000" for example and it would extract all meshes/textures for Leon's body. I should have removed .pak option to avoid confusion but anyway.

I used the bms script and the filelist (I'm assuming it's the re2_pak_names_demo.list - [https://zenhax.com/download/file.php?id=6098](https://zenhax.com/download/file.php?id=6098) - although I couldn't relate both - just placed them both on the same folder) from zaramot (link he provided) but when I extract the files I don't get any natives/x64/sectionroot/character/player. I do have that folder but, inside, I have only a vfx folder and systems folder inside the natives/x64 folder.

[https://imgur.com/a/hpNGxVY](https://imgur.com/a/hpNGxVY)

It did extract a bunch of wma, vap, tex and smc files however but all under the root folder like this:
[https://imgur.com/a/wEPbGfW](https://imgur.com/a/wEPbGfW)

Also, for some reason blender 2.79 doesn't load the script. Do I have to use version 2.49?
## Post #41
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-16T17:53:37+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from completenoob
>
> I don't get any natives/x64/sectionroot/character/player.
I am pretty sure this list from Ekey has the player folder : [https://zenhax.com/viewtopic.php?p=42319#p42319](https://zenhax.com/viewtopic.php?p=42319#p42319)

> Reply from completenoob
>
> 
Do I have to use version 2.49?
I guess so. I haven't really changed the smc import. It probably uses some methods only supported on 2.49. So better use that version.
## Post #42
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-16T18:21:21+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from akderebur
>
> completenoob wrote:I don't get any natives/x64/sectionroot/character/player.
I am pretty sure this list from Ekey has the player folder : https://zenhax.com/viewtopic.php?p=42319#p42319
completenoob wrote:
Do I have to use version 2.49?
I guess so. I haven't really changed the smc import. It probably uses some methods only supported on 2.49. So better use that version.

I will try to unpack them again using that version. I might have extracted with an older version of the file list. Script seems to be working fine on version 2.49, thank you.

Edit: Unpacked everything again and I can confirm that it unpacked everything really nicely into named folders. Meshes and textures. 
Script in Blender is importing every Lod, does not load textures (not hard to load by hand anyways).

Edit2: Is it me or the engine is doing a far greater job than it looks? Models with normal maps of 256x256?? That's for the fat cop, Leon's textures are 1024x1024. I mean...It looks ok from afar but...

[https://imgur.com/a/sdSx82x](https://imgur.com/a/sdSx82x)
## Post #43
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2019-01-17T02:19:53+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I have bunch of different version of Blender installed but none of them pick up python script.

is there something else required?
## Post #44
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-17T02:38:29+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Google and install version 2.49b. Run it and open the text editor. Open the py script through the text editor and press alt+p to run it. Browse the smc file and import.
## Post #45
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2019-01-17T02:53:15+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Oh I see, looks like it cant find "inc_noesis" module and that module wants javabridge with Oracle JRE installed. The latter is a hard pass here.
## Post #46
- Username: MJones
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 03, 2019 2:03 am
- Post datetime: 2019-01-17T05:59:07+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Well I tried with quickbms and I got a tons of files from all types: Tex, Dat, Pfb, Sbd, _Sv etc. I don't really know how to open the files with all these different files. I just want to use some stuff for enviromental purposes, not really into characters models.
## Post #47
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-17T08:24:30+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Those files should be correct (judging by the names you've mentioned). There should also be .mes/mesh files these. These are the game models (both characters and props/environments). 

If it's a bit confusing to you, I would advise using the max script zaramot provided (this thread - page 2). Even after all the work to get models to load in blender and unpacking with SGM I ended up using max. For characters at least it's painless. Load script, load mes file, done. Loads only the Lod0 with bones and skin weights too. Static meshes as well. I was able to load the police station main hall for example.
## Post #48
- Username: MJones
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 03, 2019 2:03 am
- Post datetime: 2019-01-17T08:44:32+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from completenoob
>
> Those files should be correct (judging by the names you've mentioned). There should also be .mes/mesh files these. These are the game models (both characters and props/environments). 

If it's a bit confusing to you, I would advise using the max script zaramot provided (this thread - page 2). Even after all the work to get models to load in blender and unpacking with SGM I ended up using max. For characters at least it's painless. Load script, load mes file, done. Loads only the Lod0 with bones and skin weights too. Static meshes as well. I was able to load the police station main hall for example.
So the .mes files (which im pretty sure I saw a few) are the models im looking for. If I use the max zaramot script do I have to unpack the pak file all over again? I would be very grateful if you could explain me how these things work or send a link for a guide, I never tried to see the models from something as complex as the RE engine can be so it's pretty confusing. At least I know the .mes files are the models im looking for.
## Post #49
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-17T09:25:48+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

If you have unpacked everything using the Quickbms and the file list and you don't want textures, just the meshes then you're fine using just the max script. Open max, run the script and point to the .mes/mesh files. For characters it even imports bones and skin weights. 

If you need the textures (really low resolution by the way) or want to use blender to open the files then you will need the SGM provided on this thread. Basically I used it for the textures because I prefer using max as the script loads only the Lod0. It was cool to see how far they go into optimization with the Lods (in blender) but other than that I prefer max. For a guide/tutorial on how to use SGM and blender download the latest version here and unrar it (images are inside). Hope it helps: [http://xnalara.org/viewtopic.php?f=17&t ... 6707f3057e](http://xnalara.org/viewtopic.php?f=17&t=1001&sid=52eb8730d4cd0946d8ef5f6707f3057e)
## Post #50
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2019-01-17T10:06:18+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

```
        elif dxtType == 72:
            ddsFmt = noesis.NOESISTEX_DXT1
        #Cubemaps
        elif dxtType == 95:
            ddsData = rapi.imageDecodeDXT(ddsData, ddsWidth, ddsHeight, noesis.FOURCC_BC6S)
            ddsFmt = noesis.NOESISTEX_RGBA32
        #Colorcubes
        elif dxtType == 29:
            ddsFmt = noesis.NOESISTEX_RGBA32

```

Here is some things I've found for the Noesis Python script "fmt_RE2_REMAKE_tex.py"
I'm not 100% sure.
## Post #51
- Username: Scobalula
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 24, 2017 7:13 pm
- Post datetime: 2019-01-17T12:11:19+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from completenoob
>
> If you have unpacked everything using the Quickbms and the file list and you don't want textures, just the meshes then you're fine using just the max script. Open max, run the script and point to the .mes/mesh files. For characters it even imports bones and skin weights. 

If you need the textures (really low resolution by the way) or want to use blender to open the files then you will need the SGM provided on this thread. Basically I used it for the textures because I prefer using max as the script loads only the Lod0. It was cool to see how far they go into optimization with the Lods (in blender) but other than that I prefer max. For a guide/tutorial on how to use SGM and blender download the latest version here and unrar it (images are inside). Hope it helps: http://xnalara.org/viewtopic.php?f=17&t ... 6707f3057e

With regards to the textures, you are probably running into the same issue I ran into when I started working on my own RE7 tools, there is a separate folder for the textures called "streaming" which contains the high resolution streamed textures (sticking "streaming" folder between the path and natives/x64 should give the correct texture).

On the textures again, the type/format directly correlates with DirectX's DXGI_FORMAT enumerator for anyone concerned (from SDK): 

[https://pastebin.com/tkCT58bQ](https://pastebin.com/tkCT58bQ)
## Post #52
- Username: Anthony7888
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 15, 2019 6:51 pm
- Post datetime: 2019-01-17T17:18:00+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I can have the max script provided by zaramot

for Resident Evil 2 Reamke and how do you do with texture

of all types: Tex, Dat, Pfb, Sbd, _Sv etc.
## Post #53
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-17T17:34:32+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Scobalula
>
> completenoob wrote:If you have unpacked everything using the Quickbms and the file list and you don't want textures, just the meshes then you're fine using just the max script. Open max, run the script and point to the .mes/mesh files. For characters it even imports bones and skin weights. 

If you need the textures (really low resolution by the way) or want to use blender to open the files then you will need the SGM provided on this thread. Basically I used it for the textures because I prefer using max as the script loads only the Lod0. It was cool to see how far they go into optimization with the Lods (in blender) but other than that I prefer max. For a guide/tutorial on how to use SGM and blender download the latest version here and unrar it (images are inside). Hope it helps: http://xnalara.org/viewtopic.php?f=17&t ... 6707f3057e

With regards to the textures, you are probably running into the same issue I ran into when I started working on my own RE7 tools, there is a separate folder for the textures called "streaming" which contains the high resolution streamed textures (sticking "streaming" folder between the path and natives/x64 should give the correct texture).

On the textures again, the type/format directly correlates with DirectX's DXGI_FORMAT enumerator for anyone concerned (from SDK): 

https://pastebin.com/tkCT58bQ

Oh that explains it! I knew they had to have different sized textures. I will have test it now  thank you!

> Reply from Anthony7888
>
> I can have the max script provided by zaramot

for Resident Evil 2 Reamke and how do you do with texture

of all types: Tex, Dat, Pfb, Sbd, _Sv etc.

Have a lool at the previois posts dor a detailed explanation and tutorial. You can use SGM to extract just the textures.
## Post #54
- Username: Anthony7888
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 15, 2019 6:51 pm
- Post datetime: 2019-01-17T17:54:09+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

thanks i can just have the script for the mes.mesh because i do not find it a link to download it thanks
## Post #55
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2019-01-17T18:15:10+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Anthony7888
>
> thanks i can just have the script for the mes.mesh because i do not find it a link to download it thanks

It's on the 2nd page of this thread from the user zaramot.
## Post #56
- Username: Anthony7888
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 15, 2019 6:51 pm
- Post datetime: 2019-01-17T18:27:16+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

thank you
## Post #57
- Username: Anthony7888
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 15, 2019 6:51 pm
- Post datetime: 2019-01-17T18:34:14+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

how to have and open the texture
## Post #58
- Username: MJones
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 03, 2019 2:03 am
- Post datetime: 2019-01-17T21:00:59+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from completenoob
>
> If you have unpacked everything using the Quickbms and the file list and you don't want textures, just the meshes then you're fine using just the max script. Open max, run the script and point to the .mes/mesh files. For characters it even imports bones and skin weights. 

If you need the textures (really low resolution by the way) or want to use blender to open the files then you will need the SGM provided on this thread. Basically I used it for the textures because I prefer using max as the script loads only the Lod0. It was cool to see how far they go into optimization with the Lods (in blender) but other than that I prefer max. For a guide/tutorial on how to use SGM and blender download the latest version here and unrar it (images are inside). Hope it helps: http://xnalara.org/viewtopic.php?f=17&t ... 6707f3057e
Well I kinda want the textures too, a model without texture wouldn't be that useful xD. Is there any way I can find the model with his texture in the files? Also there isn't a script or something that extracts the files with the names? It would be very difficult find something when there is only a series of numbers as a name.
## Post #59
- Username: TTR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 28, 2011 4:14 am
- Post datetime: 2019-01-17T23:57:55+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot
>
> Here's "alpha" maxscript and Noesis plugin for RE2 R, if anyone want to test it out. Skinned meshes should work, static partially xD Don't have a lot of samples. It's for those of you who prefer using 3ds max instead of something else

Hey, is there anything I can do to help get static meshes working? I'm really looking to get static meshes out of it. It seems like the vertices are connecting in a really weird order and it's making the meshes come out really distorted and jumbled up, with the wrong vertices making weird faces.
## Post #60
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-01-18T01:25:16+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Sure, send me some problematic models I'll see what I can do! But also note, that there's an alternative tool (and you can use Blender), just saying maybe you don't know
## Post #61
- Username: GlemyToto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 24, 2017 10:06 pm
- Post datetime: 2019-01-18T13:28:07+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I've ported the SMC import script to Blender 2.8
Note that the port is not complete, I've only tested it with Leon's body, so all the format features that weren't used in this particular SMC file have not been updated. Please send me a file if you encounter some problems and need an update.

> Reply from akderebur
>
> Here is the modıfıed SGM and smc import script : https://www.mediafire.com/file/t0vbm9f1 ... 2.rar/file

It only has RE2 in the game list, also I have disabled obj export since it takes lot of time. It exports smc, which you can import into Blender with the provided script. Only tested on Blender 2.49. All of the LODs will be exported. Ones starting with "s_00" are the best quality ones, delete the rest if you want. Textures are exported too, as dds.

The program worked fine with couple of files I have tested, let me know if you see any problems. Just nothing related to Blender import/export.

Do you know who wrote this import script so I can put his name as author of the script ?
[smc_import.zip](https://xentaxbackup.github.io/file/15508_smc_import.zip)
## Post #62
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-19T17:17:00+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot
>
> Here's "alpha" maxscript and Noesis plugin for RE2 R, if anyone want to test it out. Skinned meshes should work, static partially xD Don't have a lot of samples. It's for those of you who prefer using 3ds max instead of something else

Hi, thank you very much for your Max script, works perfectly but i want ask a thing if is possible, i noticed, along the .mesh file, there is a Mat file, where are stored all the textures informations with their correct path, any chance editing your script in a way that can read this file to get the model imported with the textures? It will save a lot of works for sceneries. Thank you in advance.
Fil
## Post #63
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-01-19T22:49:28+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hey! I think it's possible, can't tell for sure, like 100%. First I need to take a look at those .mtl files. But should be possible
## Post #64
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-20T06:30:35+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot
>
> Hey! I think it's possible, can't tell for sure, like 100%. First I need to take a look at those .mtl files. But should be possible
 oh, wow! Would be great! If you need some files to check, i have all extracted, so i can give you what you need, for example here there is the .mat file regarding the Police Hall:

```
https://www.mediafire.com/file/m4w5e2pioc6dzkk/st4_101_0_terrain_00ms_mat.mdf2.10/file
```
## Post #65
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2019-01-20T11:34:17+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

hello, you planing add support props in your max script
props - [https://1drv.ms/f/s!Amg1SaLumVp40xMoAFsnQMyiTs6Q](https://1drv.ms/f/s!Amg1SaLumVp40xMoAFsnQMyiTs6Q)
## Post #66
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2019-01-21T13:14:59+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hey guys, i was wondering if anyone of you know more about the material/shading system they use? I managed to locate albedo, normals and occlusion textures, but haven't seen anything that resembles the metallic or roughness yet.
## Post #67
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-21T13:32:05+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Highflex
>
> Hey guys, i was wondering if anyone of you know more about the material/shading system they use? I managed to locate albedo, normals and occlusion textures, but haven't seen anything that resembles the metallic or roughness yet.
 hi, with .mes.mesh comes a .mat or .mdf file, open it with notepad + or an hex editor, you will see all the materials used for that model.
These are a few lines i copied from a file i mentioned: hope this helps

```
G u n _ M a t   M a s t e r M a t e r i a l / M a s t e r / W e a p o n _ D e f a u l t . m m t r   p l 0 0 0 0 _ B o d y _ M a t   M a s t e r M a t e r i a l / M a s t e r / R e c o r d _ P l a y e r . m m t r   p l 0 0 0 0 _ C l o t h _ M a t   M a s t e r M a t e r i a l / M a s t e r / R e c o r d _ P l a y e r . m m t r   p l 0 0 0 0 _ I t e m _ M a t   M a s t e r M a t e r i a l / M a s t e r / R e c o r d _ P l a y e r . m m t r   p l 0 0 0 0 _ S l e e v e _ M a t   M a s t e r M a t e r i a l / M a s t e r / R e c o r d _ P l a y e r . m m t r   p l 0 0 0 0 _ S l i n g _ M a t   M a s t e r M a t e r i a l / M a s t e r / R e c o r d _ P l a y e r . m m t r   p l 0 0 0 0 _ p a n e l _ M a t   M a s t e r M a t e r i a l / M a s t e r / E n v _ E m i s s i v e . m m t r   B a s e M e t a l M a p   S e c t i o n R o o t / C h a r a c t e r / W e a p o n / w p 0 0 0 0 / w p 0 0 0 0 _ v p 7 0 _ A L B M . t e x   N o r m a l R o u g h n e s s M a p   S e c t i o n R o o t / C h a r a c t e r / W e a p o n / w p 0 0 0 0 / w p 0 0 0 0 _ v p 7 0 _ N R M R . t e x   A l p h a T r a n s l u c e n t O c c l u s i o n S S S M a p   s y s t e m s / r e n d e r i n g / N u l l A T O S . t e x   H e a t _ M a s k   s y s t e m s / r e n d e r i n g / N u l l W h i t e . t e x   B l o o d T e x t u r e   s y s t e m s / r e n d e r i n g / N u l l N o r m a l R o u g h n e s s . t e x   D e t a i l M a p   M a s t e r M a t e r i a l / T e x t u r e s / N u l l D e t a i l . t e x   D e t a i l M a s k M a p   s y s t e m s / r e n d e r i n g / N u l l W h i t e . t e x   B a s e M e t a l M a p   S e c t i o n R o o t / C h a r a c t e r / P l a y e r / p l 0 0 0 0 / p l 0 0 0 0 / p l 0 0 0 0 _ b o d y _ A L B M . t e x   N o r m a l R o u g h n e s s M a p   S e c t i o n R o o t / C h a r a c t e r / P l a y e r / p l 0 0 0 0 / p l 0 0 0 0 / p l 0 0 0 0 _ b o d y _ N R M R . t e x   A l p h a T r a n s l u c e n t O c c l u s i o n S S S M a p   S e c t i o n R o o t / C h a r a c t e r / P l a y e r / p l 0 0 0 0 / p l 0 0 0 0 / p l 0 0 0 0 _ b o d y _ A T O S . t e x   R e c _ R T T   V F X / R e c o r d S y s t e m / R e c o r d T e x t u r e / p l 0 0 0 0 / p l 0 0 0 0 _ b o d y . r t e x   R e c _ F I X   V F X / R e c o r d S y s t e m / R e c o r d T e x t u r e / B a s e T e x t u r e s / n u l l _ b l a c k _ M S K 4 . t e x   R e c _ P r o t e c t   V F X / R e c o r d S y s t e m / R e c o r d T e x t u r e / B a s e T e x t u r e s / n u l l _ b l a c k _ M S K 4 . t e x   R e c _ R a i n _ W a t e r R i p l e   R E _ E N G I N E _ L I B R A R Y / V F X _ L i b r a r y / T e x t u r e / T E X _ V e c t o r / t e x _ c a p c o m _ v e c t o r _ w a t e r _ 0 0 1 1 _ A r r a y _ N R M R . t e x   R e c _ R a i n _ W e t M a s k   V F X / T e x t u r e / T E X _ C h a r a c t e r / T E X _ p l 0 0 0 0 / t e x _ 0 0 0 2 _ p l 0 0 0 0 _ w e t m a s k _ 0 0 0 0 _ M S K 1 . t e x   R e c _ I n j u r y _ B a s e M a p   V F X / R e c
```
## Post #68
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2019-01-21T14:31:06+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Highflex
>
> Hey guys, i was wondering if anyone of you know more about the material/shading system they use? I managed to locate albedo, normals and occlusion textures, but haven't seen anything that resembles the metallic or roughness yet.
You can also check textures names like:

> _alb (ALBedo) | _atos ( ... Occlusion + Specular?) | _nrmr (NoRMal + Roughness)
## Post #69
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2019-01-21T17:20:00+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Thanks, just found some of that and seeing how it compares to the traditional PBR Pipeline.

The atos file seems to contain Ambient Occlusion from the file i checked ( leon body ) but for hair it contains the Opacity Mask.
## Post #70
- Username: Scobalula
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 24, 2017 7:13 pm
- Post datetime: 2019-01-22T11:26:11+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Material file logic in C# (should be enough info to make scripts for other uses):

[https://pastebin.com/7aSmdaYB](https://pastebin.com/7aSmdaYB)

Example from parsing the Leon's body:

```
DetailMaskMap : NullWhite
BaseMetalMap : pl0000_body_ALBM
NormalRoughnessMap : pl0000_body_NRMR
AlphaTranslucentOcclusionSSSMap : pl0000_body_ATOS
Rec_RTT : pl0000_body
Rec_FIX : null_black_MSK4
Rec_Protect : null_black_MSK4
Rec_Rain_WaterRiple : tex_capcom_vector_water_0011_Array_NRMR
Rec_Rain_WetMask : tex_0002_pl0000_wetmask_0000_MSK1
Rec_Injury_BaseMap : Record_Injury_Map_ALBA
Rec_Injury_NormalMap : Record_InjuryMap_NRM
Rec_Mud_Map : Record_Mad_Map_MSK4
Rec_Dent_Map : NullBlack
BloodMask : null_black_MSK4

```


(Note I removed full path in this particular dump, those texture names have paths in the material file)

BaseMetalMap has the albedo/diffuse with an alpha channel that contains the specular/metal mask, ATOS indeed contains an opacity mask (since the albedo's alpha is used for the spec), along with Occlusion (as hinted from its name) and I believe SSS = Sub Surface Scattering.
## Post #71
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2019-01-23T00:26:28+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

To anyone interested in Modding RE2, I made a big discovery that will help with a lot of stuff.
[http://residentevilmodding.boards.net/t ... orial-shot](http://residentevilmodding.boards.net/thread/9934/simple-modding-swapping-tutorial-shot)
## Post #72
- Username: Anthony7888
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 15, 2019 6:51 pm
- Post datetime: 2019-01-26T09:40:22+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

hello i can have the tools to extract the full game thanks
## Post #73
- Username: Anthony7888
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 15, 2019 6:51 pm
- Post datetime: 2019-01-26T12:08:59+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hello, can I have all the tools and the complete list for extract Resident Evil 2 Remake The complete game
## Post #74
- Username: friendzonebill
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 31, 2018 5:55 am
- Post datetime: 2019-01-26T19:03:01+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Anthony is known scammer and art thief, beware.
## Post #75
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-27T06:18:53+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from friendzonebill
>
> Anthony is known scammer and art thief, beware.

XD
## Post #76
- Username: GlemyToto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 24, 2017 10:06 pm
- Post datetime: 2019-01-27T10:41:32+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

@Anthony7888
You can really easily extract the models with the tools already available 
[claire.jpg](https://xentaxbackup.github.io/file/15593_claire.jpg)
## Post #77
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2019-01-27T15:24:43+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I noticed the maxscript is not applying the vertex normals, any chance to see a upgrade for this? Its mostly noticeable in Faces.
## Post #78
- Username: Pixelbuster1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 28, 2019 12:21 am
- Post datetime: 2019-01-27T16:43:43+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I'm looking into doing some audio mods if possible, wanna mod in some DMX music to replace Mr. X
## Post #79
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-01-27T20:22:09+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Highflex
>
> I noticed the maxscript is not applying the vertex normals, any chance to see a upgrade for this? Its mostly noticeable in Faces.

Yup, but I guess most of ppl using Blender tool, right? I still haven't had much reports on skinned meshes from friend of mine, except one, I fixed maxscript for rigged "burger" mesh lol (I could upload updated one). I don't have the game, so I don't have files
## Post #80
- Username: iammhk128
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 28, 2019 3:54 am
- Post datetime: 2019-01-27T21:00:51+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Dear sirs:
We are an engineering team(group),active on various fields such as(like) gaming.
We'll be gratful if you help us with seprating game's texts(subtitle) from the game and changing ut with our own language
## Post #81
- Username: Sundownsyndrome
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 12, 2015 11:15 am
- Post datetime: 2019-01-27T21:10:06+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot
>
> Highflex wrote:I noticed the maxscript is not applying the vertex normals, any chance to see a upgrade for this? Its mostly noticeable in Faces.

Yup, but I guess most of ppl using Blender tool, right? I still haven't had much reports on skinned meshes from friend of mine, except one, I fixed maxscript for rigged "burger" mesh lol (I could upload updated one). I don't have the game, so I don't have files

i don't usually like using the blender tool. unwieldy to me. for the most part, skinned meshes work alright. but weapons need to be adjusted i think, their rigging isn't quite right. i dunno how many samples you want but i can provide a few prob.
## Post #82
- Username: Manulis
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 26, 2019 6:13 pm
- Post datetime: 2019-01-27T22:54:10+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hello everyone, first off great work on extracting and decrypting stuff from this game so quickly!
Unfortunately I'm not nearly as skilled as you folks here and had some questions.

I've used quickbms before for some gamecube model extracting. I was wondering how to rip stuff from the main .pak file for the game.
It says its too large and I as wondering how to get around that.

Was wondering what to do after extracting with quickbms as well. It outputs a large assortment of junk obviously, no clue how to view any of it.

Secondly I was wondering if someone could explain the function of the Hooks you've been posting? This is completely new to me haha.

I'm most familiar using Blender for modelling. (I'm also trying to extract from the full game)

Sorry for all the questions but its hard to follow the thread a bit when it gets so strung out with info over multiple pages. Thanks for any help you send my way.
## Post #83
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2019-01-28T00:21:38+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot
>
> Highflex wrote:I noticed the maxscript is not applying the vertex normals, any chance to see a upgrade for this? Its mostly noticeable in Faces.

Yup, but I guess most of ppl using Blender tool, right? I still haven't had much reports on skinned meshes from friend of mine, except one, I fixed maxscript for rigged "burger" mesh lol (I could upload updated one). I don't have the game, so I don't have files

Hmm depends, i personally use Maya for all of my developments and played around with getting one of the faces hooked up so you can animate it. Just noticed when i started applying the textures with some base shading as demonstrated here:

[https://imgur.com/a/zyoTQb1](https://imgur.com/a/zyoTQb1)

I don't see any other issues so far, this was the only thing that i noticed by processing all components of Leon to be workable with.

If you need any files or more info on this please let me know, i have experience with applying normals through max-script just needs to be parsed i guess.
## Post #84
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2019-01-28T16:58:29+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Highflex
>
> zaramot wrote:Highflex wrote:I noticed the maxscript is not applying the vertex normals, any chance to see a upgrade for this? Its mostly noticeable in Faces.

Yup, but I guess most of ppl using Blender tool, right? I still haven't had much reports on skinned meshes from friend of mine, except one, I fixed maxscript for rigged "burger" mesh lol (I could upload updated one). I don't have the game, so I don't have files  

Hmm depends, i personally use Maya for all of my developments and played around with getting one of the faces hooked up so you can animate it. Just noticed when i started applying the textures with some base shading as demonstrated here:

https://imgur.com/a/zyoTQb1

I don't see any other issues so far, this was the only thing that i noticed by processing all components of Leon to be workable with.

If you need any files or more info on this please let me know, i have experience with applying normals through max-script just needs to be parsed i guess.

Weld your normals or vertices...
## Post #85
- Username: troconisgerman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 29, 2019 4:19 am
- Post datetime: 2019-01-28T20:31:41+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

How do I find the environment file?, when I use SGM when it goes to convert environment files to smc it closes and doesn;t convertmesh.18xxxxxxxxx files to smc
## Post #86
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-29T11:21:00+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from troconisgerman
>
> How do I find the environment file?, when I use SGM when it goes to convert environment files to smc it closes and doesn;t convertmesh.18xxxxxxxxx files to smc

The sceneries are in: \natives\x64\sectionroot\environment\location\
The sceneries props are in:  \natives\x64\objectroot\setmodel\
Put the xentax.exe file in the \environment\location\ folder, open it as admin, in the  "select path"  click on "exe path" 
click on ok, answer: process pak, NO process textures? YES process mesh? YES
That is. It will convert all the textures and .mesh files in the "location" folders
## Post #87
- Username: CzlowiekDrzewo
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 17, 2014 5:46 pm
- Post datetime: 2019-01-29T17:19:08+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I'm really confused so I hope someone here can help me out. How do you get all those different folders? All I get is .dat and .pfb files.
## Post #88
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-30T06:01:17+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from CzlowiekDrzewo
>
> I'm really confused so I hope someone here can help me out. How do you get all those different folders? All I get is .dat and .pfb files.
before using quickbms you have to put in the game folder the namefilelist, this will allow quickbms to create the correct folders
[https://zenhax.com/viewtopic.php?f=9&t=9253&start=60](https://zenhax.com/viewtopic.php?f=9&t=9253&start=60)
## Post #89
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-30T16:18:17+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot
>
> Hey! I think it's possible, can't tell for sure, like 100%. First I need to take a look at those .mtl files. But should be possible

hi! any update?
## Post #90
- Username: iammhk128
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 28, 2019 3:54 am
- Post datetime: 2019-01-30T16:35:33+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

[http://dl2.dlfox.com/PS4/DELETED/bandic ... 51-367.mp4](http://dl2.dlfox.com/PS4/DELETED/bandicam%202019-01-30%2019-58-51-367.mp4) 

NOT WORK xentax

PLZ HELP
## Post #91
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2019-01-30T19:51:11+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from iammhk128
>
> http://dl2.dlfox.com/PS4/DELETED/bandic ... 51-367.mp4 

NOT WORK xentax

PLZ HELP

Use the max script.
## Post #92
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-01-30T20:28:31+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from iammhk128
>
> http://dl2.dlfox.com/PS4/DELETED/bandic ... 51-367.mp4 

NOT WORK xentax

PLZ HELP
you don't have to process pak files with xentax, only textures and mesh, to process pak files use quickbms with re2unpack
## Post #93
- Username: CzlowiekDrzewo
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 17, 2014 5:46 pm
- Post datetime: 2019-02-01T20:11:28+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Appreciate all the help in this thread. I ran into another problem though. I'm at the stage of importing the .smc into Blender but I can't enable the script. I get and error:

```
  File "D:\XXXXX\Blender Foundation\Blender\2.79\scripts\modules\addon_utils.py", line 331, in enable
    mod = __import__(module_name)
  File "C:\Users\XXXXXX\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\smc_import.py", line 561
    filter_glob: StringProperty(
               ^
SyntaxError: invalid syntax


```


I tried few older versions and I get pretty much the same thing on every one of them.

EDIT: Nevermind, it's an addon for 2.80. I'm a dumbass.
## Post #94
- Username: abstrait
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Dec 05, 2016 12:33 am
- Post datetime: 2019-02-02T05:49:38+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Is there any way to import the animation files in 3ds max ?
## Post #95
- Username: tnt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 03, 2017 6:02 am
- Post datetime: 2019-02-07T16:05:59+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I modified the script to work with Blender 2.78 , using GlemyToto's version as a template


 smc_import_2_78.zip
(11.14 KiB) Downloaded 184 times
## Post #96
- Username: cashgrany
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 16, 2018 1:26 am
- Post datetime: 2019-02-08T00:13:33+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hello ;
How do we extract the .tex files; textures?
## Post #97
- Username: ushimata
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-02-08T14:59:33+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

[Leon](https://cdn.discordapp.com/attachments/493152982293282816/543115191022256151/Leon.png)
[Ada](https://cdn.discordapp.com/attachments/493152982293282816/543147890801901611/Ada.png)

Noesis importer almost finished
## Post #98
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2019-02-08T15:32:43+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from cashgrany
>
> Hello ;
How do we extract the .tex files; textures?

Read the thread.
## Post #99
- Username: cashgrany
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 16, 2018 1:26 am
- Post datetime: 2019-02-08T15:52:49+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

thank you so much Darko ; I had misread; is it normal that some texture is blank?
## Post #100
- Username: alexsimm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 09, 2019 12:45 am
- Post datetime: 2019-02-08T17:07:31+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I extracted files from re_chunk_000.pak by quickbms. I got files with .dat and .pfb  adn other extensions. What should I do next ?
## Post #101
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-02-09T14:22:30+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Gh0stBlade
>
> Leon
Ada

Noesis importer almost finished

Awesome! Will supports sceneries and autotexture aswell?
## Post #102
- Username: beelzebub2063
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-02-09T20:37:48+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Resident Evil 2 Remake - [RE2] - [PC]/b]


fmt_RE2_mesh_1_5.py - Version 1.5 - 09/02/19
I recommend using the .gltf file format for exporting 
Supported:
1. Meshes, UVs, Normals, Skin Weights, Skin Indices, Skeleton (*.1808312334)
2. Auto texturing and material parameter parsing.
3. Textures (*.10)

Have fun.
[fmt_RE2_mesh_1_5.zip](https://xentaxbackup.github.io/file/15688_fmt_RE2_mesh_1_5.zip)
## Post #103
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-02-10T05:36:57+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Gh0stBlade
>
> Resident Evil 2 Remake - [RE2] - [PC]/b]


fmt_RE2_mesh_1_5.py - Version 1.5 - 09/02/19
I recommend using the .gltf file format for exporting 
Supported:
1. Meshes, UVs, Normals, Skin Weights, Skin Indices, Skeleton (*.1808312334)
2. Auto texturing and material parameter parsing.
3. Textures (*.10)

Have fun.

Autotextures doesn't work for me
EDIT:
The noesis console said: Failed to open material file "mesh.mdf2.10" of course!! Is a "mat.mdf2.10" i renamed it and it loads textures. Could you edit the script, please?
## Post #104
- Username: rugalytto
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-02-10T16:53:48+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from fil1969
>
> 
Autotextures doesn't work for me
EDIT:
The noesis console said: Failed to open material file "mesh.mdf2.10" of course!! Is a "mat.mdf2.10" i renamed it and it loads textures. Could you edit the script, please?

It's not a bug in the code. Problem is some mdf files weren't named the same as the mesh file so you have to rename them manually. I could create some code that scans for certain suffixes but it's just a hack (and i don't like hacks in code).
## Post #105
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-02-10T17:12:35+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Gh0stBlade
>
> fil1969 wrote:
Autotextures doesn't work for me
EDIT:
The noesis console said: Failed to open material file "mesh.mdf2.10" of course!! Is a "mat.mdf2.10" i renamed it and it loads textures. Could you edit the script, please?

It's not a bug in the code. Problem is some mdf files weren't named the same as the mesh file so you have to rename them manually. I could create some code that scans for certain suffixes but it's just a hack (and i don't like hacks in code).

Some? Almost all!  anyway ok, just to be sure what i have to do.
btw thanks, even with this "problem",your script save a lot of work
## Post #106
- Username: Nemesisbg23
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 14, 2019 8:07 am
- Post datetime: 2019-02-11T01:33:56+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Gh0stBlade
>
> Resident Evil 2 Remake - [RE2] - [PC]/b]


fmt_RE2_mesh_1_5.py - Version 1.5 - 09/02/19
I recommend using the .gltf file format for exporting 
Supported:
1. Meshes, UVs, Normals, Skin Weights, Skin Indices, Skeleton (*.1808312334)
2. Auto texturing and material parameter parsing.
3. Textures (*.10)

Have fun.
well i tried it and i get this error all the time on every model xD 

 

Halp my friends also get this error xD
## Post #107
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-02-11T03:19:56+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Nemesisbg23
>
> Gh0stBlade wrote:Resident Evil 2 Remake - [RE2] - [PC]/b]


fmt_RE2_mesh_1_5.py - Version 1.5 - 09/02/19
I recommend using the .gltf file format for exporting 
Supported:
1. Meshes, UVs, Normals, Skin Weights, Skin Indices, Skeleton (*.1808312334)
2. Auto texturing and material parameter parsing.
3. Textures (*.10)

Have fun.
well i tried it and i get this error all the time on every model xD 

 

Halp my friends also get this error xD
Download the latest version of Noesis.
## Post #108
- Username: Nemesisbg23
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 14, 2019 8:07 am
- Post datetime: 2019-02-11T03:36:27+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Gh0stBlade
>
> Nemesisbg23 wrote:Gh0stBlade wrote:Resident Evil 2 Remake - [RE2] - [PC]/b]


fmt_RE2_mesh_1_5.py - Version 1.5 - 09/02/19
I recommend using the .gltf file format for exporting 
Supported:
1. Meshes, UVs, Normals, Skin Weights, Skin Indices, Skeleton (*.1808312334)
2. Auto texturing and material parameter parsing.
3. Textures (*.10)

Have fun.
well i tried it and i get this error all the time on every model xD 



Halp my friends also get this error xD
Download the latest version of Noesis.
AH i got it working but where are the textures xD
## Post #109
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-02-11T03:56:07+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Nemesisbg23
>
> 
AH i got it working but where are the textures xD
As explained on the previous page, each mesh file has it's own corresponding .mdf.10 file that holds material information. It must be renamed exactly the same as the mesh file minus the file extension. Check the debug log window for more details.
## Post #110
- Username: spazman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 10, 2019 9:31 am
- Post datetime: 2019-02-11T11:31:28+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I can not seem to see the mesh/models in Noesis to choose from. I can see the textures tex.10 and tex.dds only with Gh0stBlade script. What am I doing wrong?
## Post #111
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-02-11T13:16:19+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from spazman
>
> I can not seem to see the mesh/models in Noesis to choose from. I can see the textures tex.10 and tex.dds only with Gh0stBlade script. What am I doing wrong?
did you select in "files type" "all know formats"?
## Post #112
- Username: DarkRaven
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 20, 2015 5:30 pm
- Post datetime: 2019-02-11T13:52:41+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Is there a way to merge mesh files on Noesis on import, like body then add head/hair mesh into the preview window.
## Post #113
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2019-02-11T16:47:59+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

yes: tools, model merger
## Post #114
- Username: spazman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 10, 2019 9:31 am
- Post datetime: 2019-02-11T20:09:23+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from fil1969
>
> spazman wrote:I can not seem to see the mesh/models in Noesis to choose from. I can see the textures tex.10 and tex.dds only with Gh0stBlade script. What am I doing wrong?
did you select in "files type" "all know formats"?
yes, I do not see anything else but texture files. The mesh are in the folder but Noesis and Gh0stBlade's script does not seem to see it.
## Post #115
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-02-12T05:52:27+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from spazman
>
> fil1969 wrote:spazman wrote:I can not seem to see the mesh/models in Noesis to choose from. I can see the textures tex.10 and tex.dds only with Gh0stBlade script. What am I doing wrong?
did you select in "files type" "all know formats"?
yes, I do not see anything else but texture files. The mesh are in the folder but Noesis and Gh0stBlade's script does not seem to see it.

First: download and unpack this in your Noesis-plugins-python folder
[download/file.php?id=15688](http://forum.xentax.com/download/file.php?id=15688)
Second: be sure to update your Noesis to the last version.
If you want the model with textures, you have to rename the mat file exactly like the mesh file. Keeping the extension.
## Post #116
- Username: spazman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 10, 2019 9:31 am
- Post datetime: 2019-02-12T10:12:33+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from fil1969
>
> First: download and unpack this in your Noesis-plugins-python folder
download/file.php?id=15688
Second: be sure to update your Noesis to the last version.
If you want the model with textures, you have to rename the mat file exactly like the mesh file. Keeping the extension.
Sorry but I tried that. The python script only gives me texture files and not the mesh. I also check the "check for updates" and it says I am already using the latest version of Noesis. I see the mesh are in the folder but Noesis can not detect them.
I did use an expanded list on quickbms. Is that the problem? What list did you guys use for quickbms?
## Post #117
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-02-12T20:12:07+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from spazman
>
> fil1969 wrote:First: download and unpack this in your Noesis-plugins-python folder
download/file.php?id=15688
Second: be sure to update your Noesis to the last version.
If you want the model with textures, you have to rename the mat file exactly like the mesh file. Keeping the extension.
Sorry but I tried that. The python script only gives me texture files and not the mesh. I also check the "check for updates" and it says I am already using the latest version of Noesis. I see the mesh are in the folder but Noesis can not detect them.
I did use an expanded list on quickbms. Is that the problem? What list did you guys use for quickbms?
Meshes probably have the wrong file extension. The script expects .1808312334 for the mesh's file extension. If you unpacked the game properly using the bms script with filenames it should work.
## Post #118
- Username: spazman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 10, 2019 9:31 am
- Post datetime: 2019-02-13T02:58:23+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Gh0stBlade
>
> spazman wrote:fil1969 wrote:First: download and unpack this in your Noesis-plugins-python folder
download/file.php?id=15688
Second: be sure to update your Noesis to the last version.
If you want the model with textures, you have to rename the mat file exactly like the mesh file. Keeping the extension.
Sorry but I tried that. The python script only gives me texture files and not the mesh. I also check the "check for updates" and it says I am already using the latest version of Noesis. I see the mesh are in the folder but Noesis can not detect them.
I did use an expanded list on quickbms. Is that the problem? What list did you guys use for quickbms?
Meshes probably have the wrong file extension. The script expects .1808312334 for the mesh's file extension. If you unpacked the game properly using the bms script with filenames it should work.
I do see the mesh.1808312334 in the folder but the script does not detect it for some reason. What bms script with filenames did you guys use? I used an updated one but it may be the wrong one.
## Post #119
- Username: themimegogo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 06, 2018 8:07 pm
- Post datetime: 2019-02-13T16:41:56+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hi everyone,

found my way here from the Resident Evil Modding Boards. (Much thanks to Luigi too for showing the the links to get to this thread).

I'm a hobbyist animator, and a rigger by profession. I only have a decent rudimentary amount of knowledge in maxscript, python and mel, and I am by no means a scripter / coder. I am here because I find the concept of being able to import our own custom models back into the game very enticing. 

Much of what I've seen of the successful (Character swap)mods so far are done by replacing and renaming certain .pfb files and placing them in the appropriate directories. You guys probably already know that.

My question is - is there already a tool around that allows importing standard DCC formats (such as .fbx) back into the game? I mean I understand, that if we want a rigged character with the proper skinning, on the rigging side I will need to prepare a skeletal structure that conforms to whatever is being used in the game. But before I proceed to do that, I'd im curious to know if it's already possible at this point in time. 

I've seen a few early posts in this thread talking about meshes working properly with the correct weights and whatnot ~ but I'm assuming that those were referring to character models that were successfully exported out and not into the game. 

Thank you for taking the time to read this. I promise I wont be a bother.
## Post #120
- Username: themimegogo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 06, 2018 8:07 pm
- Post datetime: 2019-02-16T02:59:30+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hi again...

after some reading back and forth on the first 3 pages of this this thread, I managed to successfully test importing some skinned meshes into max.

there are quite a number of .mes files located just outside the natives folder after doing the unpacking with quickbms. Ive been importing .mes files randomly and so far ive found a dog ([https://imgur.com/a/47NOmbw](https://imgur.com/a/47NOmbw))that i dont believe ive seen in the game, a zombie head and what looks like a long chain of sewer poo poo.

2 questions:

1 Which .mes file should i look at if im interested in the characters?
2 how do i look at these meshes with their tectures?

Edit:
nvm - found the characters in their respective sectionroot folders in the natives db. (Hunk - [https://imgur.com/a/Zhn1RzZ](https://imgur.com/a/Zhn1RzZ))
as for the textures, i guess we have to manually re-assign them to new shaders on our own yes?
## Post #121
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2019-02-16T16:57:59+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Question - is it possible to make noesis script auto-apply textures not from default folder, but from streaming/ path, which are HD textures?
Example Leon's body textures 
natives\x64\sectionroot\character\player\pl0000\pl0000 - default quality
natives\x64\streaming\sectionroot\character\player\pl0000\pl0000 - high quality

P.S. natives\x64\sectionroot\environment\location\st7_factory\st7_2_orphanasylum\st7_202_0\st7_202_0_terrain_00ms.mesh-not all textures are applied, don't know the reason....
## Post #122
- Username: themimegogo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 06, 2018 8:07 pm
- Post datetime: 2019-02-16T19:00:42+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot
>
> Here's "alpha" maxscript and Noesis plugin for RE2 R, if anyone want to test it out. Skinned meshes should work, static partially xD Don't have a lot of samples. It's for those of you who prefer using 3ds max instead of something else

In that case I will do some tests on different models, and release the modified program.[/quote]

zaramot, thanks for this. works like a charm
quick question - is there a script or a tool available that does the exact reverse of this script that you provided?

say I modified the mesh a bit, then would wand to export it out again as a working .mesh file (or as a pfb.16) that could be brought back into the game?
## Post #123
- Username: georgesears
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-02-16T22:35:16+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from georgesears ↑Sun Feb 17, 2019 12:57 am at Sun Feb 17, 2019 12:57 am
>
> 
Question - is it possible to make noesis script auto-apply textures not from default folder, but from streaming/ path, which are HD textures?
Example Leon's body textures 
natives\x64\sectionroot\character\player\pl0000\pl0000 - default quality
natives\x64\streaming\sectionroot\character\player\pl0000\pl0000 - high quality

P.S. natives\x64\sectionroot\environment\location\st7_factory\st7_2_orphanasylum\st7_202_0\st7_202_0_terrain_00ms.mesh-not all textures are applied, don't know the reason....

[img/]https://cdn.discordapp.com/attachments/ ... nknown.png[/img]

That's a beta/unfinished level with missing textures actually. The finished stage is in another folder.

Using higher quality textures is an easy fix, shame nobody told me about this before the script released but here it is.
[fmt_RE2_mesh_1_7.zip](https://xentaxbackup.github.io/file/15737_fmt_RE2_mesh_1_7.zip)
## Post #124
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2019-02-16T22:43:42+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Gh0stBlade ↑Sun Feb 17, 2019 6:35 am at Sun Feb 17, 2019 6:35 am
>
> 


That's a beta/unfinished level with missing textures actually. The finished stage is in another folder.

Using higher quality textures is an easy fix, shame nobody told me about this before the script released but here it is.

Thanks for quick fix, i'll keep both versions tho)
But what about prop placement? Is that possible to be parsed and exported with placement? There are files like _occ.mesh maybe coordinates and links to models are there?
## Post #125
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-02-17T00:41:34+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from georgesears ↑Sun Feb 17, 2019 6:43 am at Sun Feb 17, 2019 6:43 am
>
> 
Gh0stBlade wrote: ↑Sun Feb 17, 2019 6:35 am


That's a beta/unfinished level with missing textures actually. The finished stage is in another folder.

Using higher quality textures is an easy fix, shame nobody told me about this before the script released but here it is.


Thanks for quick fix, i'll keep both versions tho)
But what about prop placement? Is that possible to be parsed and exported with placement? There are files like _occ.mesh maybe coordinates and links to models are there?

Prop placement is probably managed by an completely different script file (xml based i'd assume) the _occ.mesh does not contain prop placement. I don't know if modders found out which files control it but even if they did their xml based formats are complex and I currently don't have time to look at them.
## Post #126
- Username: abstrait
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Dec 05, 2016 12:33 am
- Post datetime: 2019-02-19T12:23:06+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

@Gh0stBlade

Hello Ghost,
Is there any way to import the animations into 3dsmax by any chance ?
Thank you.
## Post #127
- Username: zaselim
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 20, 2019 4:11 am
- Post datetime: 2019-02-19T20:30:41+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from zaramot ↑Wed Jan 16, 2019 8:05 pm at Wed Jan 16, 2019 8:05 pm
>
> 
Here's "alpha" maxscript and Noesis plugin for RE2 R, if anyone want to test it out. Skinned meshes should work, static partially xD Don't have a lot of samples. It's for those of you who prefer using 3ds max instead of something else
Hello how r you?
So how do i export the mesh file after editing it? I used your script and import the claire mesh file and then edited it a bit. Now how do i export the mesh file? or do i need to export it in other format like obj or fbx then convert it to mesh file?
## Post #128
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-02-20T18:00:06+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from abstrait ↑Tue Feb 19, 2019 8:23 pm at Tue Feb 19, 2019 8:23 pm
>
> 
@Gh0stBlade

Hello Ghost,
Is there any way to import the animations into 3dsmax by any chance ?
Thank you.

Nope, my script only handles the 3D models.
## Post #129
- Username: nemesis1919
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 23, 2019 11:08 pm
- Post datetime: 2019-02-23T15:50:10+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Nemesisbg23 ↑Mon Feb 11, 2019 11:36 am at Mon Feb 11, 2019 11:36 am
>
> 
Gh0stBlade wrote:Nemesisbg23 wrote:
well i tried it and i get this error all the time on every model xD 



Halp my friends also get this error xD
Download the latest version of Noesis.
AH i got it working but where are the textures xD


Hi get this error too, how did you get it to work? I'm using Noesis version 4.39. is that the latest version? if not then where can I get the latest version?
## Post #130
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-02-23T17:16:49+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

[/quote]



Hi get this error too, how did you get it to work? I'm using Noesis version 4.39. is that the latest version? if not then where can I get the latest version?
[/quote]

the last is 4.395. you can update your version directly in noesis, clicking on Tools---> check for update
## Post #131
- Username: nemesis1919
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 23, 2019 11:08 pm
- Post datetime: 2019-02-23T22:18:09+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Great, that worked... thanks.
## Post #132
- Username: unblockedsmashflash2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 27, 2019 1:15 am
- Post datetime: 2019-02-26T17:35:55+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Oh! thanks bro It really helpful...
## Post #133
- Username: roachdaripper
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 10, 2019 8:14 pm
- Post datetime: 2019-06-16T03:00:36+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

was trying to export a modded mr x model
## Post #134
- Username: Skemooo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 23, 2019 3:26 pm
- Post datetime: 2019-07-27T09:15:11+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

I was able to render some ingame models in blender thanks to all you ppl here..

[https://imgur.com/TEy1GT4](https://imgur.com/TEy1GT4)

now as second i thought i would make a small edit to the models but i just realized the tools i have here are only for unpack and import.. not export and repack.. am i correct i did spend some time looking for anything available for blender.. so far al most all videos i watched used 3DS max 2014 version and tool provided by the malewae .. i have 0 exp in 3DS max but ill give it a try.. unless someone can point to any export adn repacking tools/scripts that work with blender?
## Post #135
- Username: DioBrando
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 06, 2010 11:59 am
- Post datetime: 2019-09-27T12:17:15+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Does anyone know how to extract the mcol.3017 files? I assume they are colliders for the environments.
## Post #136
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-12-29T22:18:07+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hook is updated for latest game version. Now only unique names will be recorded. [here](https://www4.zippyshare.com/v/eSAd16LO/file.html)
## Post #137
- Username: TTR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 28, 2011 4:14 am
- Post datetime: 2019-12-30T06:16:24+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

shoutout to Gh0stBlade, your neosis plugin fixed the UV errors i was getting with the other tools. GOD.
## Post #138
- Username: Maron19
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Nov 05, 2017 10:22 pm
- Post datetime: 2020-03-23T14:50:57+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Ekey ↑Mon Dec 30, 2019 6:18 am at Mon Dec 30, 2019 6:18 am
>
> 
Hook is updated for latest game version. Now only unique names will be recorded. here

Is this a joke? It doesn't work at all, even the game doesn't start, totally pointless.
## Post #139
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-03-25T17:33:32+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

> Reply from Maron19 ↑Mon Mar 23, 2020 10:50 pm at Mon Mar 23, 2020 10:50 pm
>
> 
Is this a joke? It doesn't work at all, even the game doesn't start, totally pointless.

Yes, I'm a clown and decided to make a joke on everyone.
## Post #140
- Username: Maron19
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Nov 05, 2017 10:22 pm
- Post datetime: 2020-03-27T20:31:40+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

That's what I thought, you do these different unpacker, but everything unfinished, barely working ...
## Post #141
- Username: 3drussiangrabber
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 27, 2020 12:12 am
- Post datetime: 2020-04-03T15:38:30+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hello man!
You want need more here
[https://www.tombraiderforums.com/showpo ... count=9534](https://www.tombraiderforums.com/showpost.php?p=5268383&postcount=9534)
## Post #142
- Username: MadHotHatter
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 11, 2022 10:55 pm
- Post datetime: 2022-06-11T16:06:07+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Is anyone know any way to get animations? Thanks for reply
## Post #143
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2022-07-23T18:41:54+00:00
- Post Title: Re: Resident Evil 2 Remake - demo PAK file

Hi, can you please checkout the new filenames for RE2 PC release? Latest update completely renamed all essential files. We are interested especially in .msg files. Normally small change in last number is present (.msg.14 to some other number at the end) and we can do some guessing (algorithmically), but this time it is not the case (we tested numbers from 0 to 1000000).  It will be probably the same extension for all msg files so we can use previous list. Thanks in advance.
