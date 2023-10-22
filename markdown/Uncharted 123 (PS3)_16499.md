## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-05T15:26:03+00:00
- Post Title: Uncharted 1/2/3 (PS3)

Tools for Uncharted 1/2/3 (PS3). Also work with The Last of Us. Bones, weights, normals, textures, everything is working.

Usage: drop .PAK file onto the tool
or run from command line: Naughty_u <pak_file>

There are still some problems (I may fix them later):
- skeletons exported to separate file, you need to connect them manually
- levels export with some meshes placed at world center



[Naughty_u.rar](https://xentaxbackup.github.io/file/13096_Naughty_u.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-08T12:47:39+00:00
- Post Title: Uncharted 1/2/3 (PS3)

Testing showed some problems, these will be fixed soon, and tools will be published. Also it will support Uncharted 1.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-08T17:29:11+00:00
- Post Title: Uncharted 1/2/3 (PS3)

Tools posted

So finally all of the most wanted PS3 exclusives have tools. Well, maybe God of War left. But I plan to make tools for it soon.
## Post #4
- Username: raidergale
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 15, 2010 12:52 am
- Post datetime: 2017-07-09T21:22:49+00:00
- Post Title: Uncharted 1/2/3 (PS3)

Thank you very much for this, I tested it on some U2 models and it works flawlessly! 

I have a question though, do you know where the base Drake skeleton is located? All the costume-hero variations for the main characters are higher poly than the actual NPC versions, but of course they all use Drake's skeleton since it's just a skin for the main character.
Every NPC character I checked has its own skeleton in a [name]-base.pak file, but I can't seem to find an equivalent file for Drake (I was expecting something like hero-base.pak or something similar). It's possible I'm completely blind and I missed it though.

Thank you again for the tool, it's nice being able to check out U2 models after so long
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-10T08:27:33+00:00
- Post Title: Uncharted 1/2/3 (PS3)

I have no idea where drake's skeleton is. Actually I'm not sure who Drake is. Working on fixes, and level exporting:
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-07-10T11:01:13+00:00
- Post Title: Uncharted 1/2/3 (PS3)

> Reply from daemon1
>
> I have no idea where drake's skeleton is he's a main character. though there's no files named "drake" instead developers use "hero" for define the main protogonist.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-10T14:00:23+00:00
- Post Title: Uncharted 1/2/3 (PS3)

Uncharted 3 Pub:



While some furniture pieces are still standing outside. If I'll have time, I'll put them into their places.
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-07-11T02:01:12+00:00
- Post Title: Uncharted 1/2/3 (PS3)

The link at the top doesn't yet support level exporting, is this correct?
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-11T06:16:14+00:00
- Post Title: Uncharted 1/2/3 (PS3)

yes i'm working on it
## Post #10
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-07-11T06:36:39+00:00
- Post Title: Uncharted 1/2/3 (PS3)

> Reply from daemon1
>
> yes i'm working on it

Ah ok, I thoguht so, just wanted to make sure, as I was fishing out my Uncharted Collections.
## Post #11
- Username: Nyotengu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jul 29, 2014 11:05 am
- Post datetime: 2017-07-11T06:38:49+00:00
- Post Title: Uncharted 1/2/3 (PS3)

Edit: never mind, I just read what you said about the command line, I got the 2 .smd files but what can i use to see the .smd files?  

I just tried to extract the Chloe.pak and Hero.pak (nathan) from uncharted 2 and the tool stops responding with error: "Naughty_Reloc has stopped responding". Any idea why that's happening? I'm on windows 10 64 bit. Hoping to get a working uncharted 2 Chloe model.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-11T07:01:29+00:00
- Post Title: Uncharted 1/2/3 (PS3)

You can load SMD files into blender, maya or max using their SMD import plugins. Also can load in Noesis and convert to anything you want.

p.s. don't hurry, the new version will fix many issues
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-11T19:03:44+00:00
- Post Title: Uncharted 1/2/3 (PS3)

Tool updated.

- No need for parameters, all games detected automatically
- Fixed UVs, some mesh scales, normals
- Now all games have meshes exported with names
- Texture export
- Level export (experimental, i need more research to support them properly)

Important note. If you tried to export some very big levels with previous tool, it could corrupt the PAK file, so if it doesn't work anymore, you have to get original file again. Always backup your files before doing anything with Naughty files.
## Post #14
- Username: Hereisme
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 15, 2017 3:55 am
- Post datetime: 2017-07-15T14:55:45+00:00
- Post Title: Uncharted 1/2/3 (PS3)

> Reply from daemon1
>
> Tool updated.

- No need for parameters, all games detected automatically
- Fixed UVs, some mesh scales, normals
- Now all games have meshes exported with names
- Texture export
- Level export (experimental, i need more research to support them properly)

Important note. If you tried to export some very big levels with previous tool, it could corrupt the PAK file, so if it doesn't work anymore, you have to get original file again. Always backup your files before doing anything with Naughty files.

Are you planning to add import option aswell? so that you can import 3D maps/characters to game?
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-16T10:35:51+00:00
- Post Title: Uncharted 1/2/3 (PS3)

> Reply from Hereisme
>
> Are you planning to add import option aswell? so that you can import 3D maps/characters to game?
no
## Post #16
- Username: rubiksedits
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 29, 2017 2:04 pm
- Post datetime: 2017-07-29T06:45:39+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from daemon1
>
> Uncharted 3 Pub:



While some furniture pieces are still standing outside. If I'll have time, I'll put them into their places.

Where was the pkg for the pub located? And were the furniture pieces and stuff separate or did it all come together when you opened the SMD file?
## Post #17
- Username: outerstarz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 11, 2016 8:18 am
- Post datetime: 2017-08-13T20:55:23+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

can confirm it works beautifully, even TLOU exports fully

im used to 3ds max tho, how do i manually set the bones to the mesh in blender lmao
## Post #18
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-08-14T01:48:17+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from outerstarz
>
> can confirm it works beautifully, even TLOU exports fully

im used to 3ds max tho, how do i manually set the bones to the mesh in blender lmao

You don't need to use blender, you can use Max still, i use Maya.
## Post #19
- Username: madruguinha
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 16, 2017 5:48 am
- Post datetime: 2017-08-17T21:08:28+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Has anyone been able to properly rip the original Chloe model from Uncharted 2? I used the tool, and I got the chloe.smd and chloe-base_skel.smd. I was able to import the smd files to Blender, but everytime that I tried to connect the skeleton to the model, I feel like the weights are all messed up, the arm bone moves some part of the gear and doesn't move the arm completely, same thing with the legs bones.
This is my first time trying to rip a model from a game, since I haven't seen anyone trying to rip the Chloe model from Uncharted 2, I thought that I would try it myself, but so far I'm failing miserably
## Post #20
- Username: fires
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 14, 2017 12:07 am
- Post datetime: 2017-08-17T23:01:59+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Congratulations to this awesome tool!
Do you have any plans to release the source code?

Cheers,
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-08-19T09:27:40+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from fires
>
> Congratulations to this awesome tool!
Do you have any plans to release the source code?

No. There are certain people, who use free sources to make paid tools. I don't want my work being used in paid tools, so I'm not releasing sources. I'm only sharing information with people I trust, who make free tools.
## Post #22
- Username: fires
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 14, 2017 12:07 am
- Post datetime: 2017-08-20T21:22:31+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Ah, okay.

I am playing around with the environment files of uncharted 2 and have some problems.
At the moment, it looks like you export all models at their origin to one file, which is an issue for environments. 
Do you have any plans to look at the sphere tree of the environment as well? 
I am not sure, but probably the placement of the model instances is defined “somewhere” in this data structure …

Cheers,
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-08-21T17:29:09+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from fires
>
> it looks like you export all models at their origin
No. They all have offsets. Just for some of them offsets are zero. Its possible that there's some more information somewhere, but I don't have time to return to this in near future.
## Post #24
- Username: kuma
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 24, 2017 7:25 am
- Post datetime: 2017-09-27T11:40:29+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Does someone know if the Lazarevic's soldiers use the same skeleton as Lazarevic?
## Post #25
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-12-03T12:43:55+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Hello
I have a problem when extracting
hair uv map broken
there is an opportunity to fix it
tell me how, only manually?

Thanks for awesome tool!
## Post #26
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-12-04T09:45:46+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from Crazy31139
>
> Hello
I have a problem when extracting
hair uv map broken
there is an opportunity to fix it
tell me how, only manually?

Thanks for awesome tool!you should be more specific on you problem: what game, what file and what mesh of this file is broke? nobody will help or even read you with words like "I have a problem - please help me".
## Post #27
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-12-05T16:38:50+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

The Last of Us Maria Hair UV Map broken
[maria-hair-cloth.rar](https://xentaxbackup.github.io/file/13649_maria-hair-cloth.rar)
## Post #28
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-12-06T03:17:20+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from Crazy31139
>
> The Last of Us Maria Hair UV Map broken

It would be better to explain the issue with a screenshot, and telling us what caused it, and what file its from.

People are unlikely to download the file just to see what the issue is.
## Post #29
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-02-18T14:54:16+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Is there a way to unpack the PS4 Trilogy version including the better texture?
I got some files that is as .PAK but as i kinda could figure out the ps3 version unpacker don't work
And the Uncharted 4 Unpacker don't work either

Is it possible or is it a lost cause?
## Post #30
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-18T17:47:13+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from Faithfullfaun
>
> I got some files that is as .PAK but as i kinda could figure out the ps3 version unpacker don't work
Can you post some sample files?
## Post #31
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-02-22T17:55:12+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from akderebur
>
> Faithfullfaun wrote:I got some files that is as .PAK but as i kinda could figure out the ps3 version unpacker don't work
Can you post some sample files?

I don't have them anymore but you can download the dumped game files at psxhax
## Post #32
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-22T19:27:01+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from Faithfullfaun
>
> 
I don't have them anymore but you can download the dumped game files at psxhax

I just thought the Uncharted textures might be similar to TLOU, and that I can modify my texture tool to work with it maybe. I won't download the whole game to see a couple of texture files though 

Still thanks for letting me know.
## Post #33
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-22T20:53:16+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from akderebur
>
> Faithfullfaun wrote:
I don't have them anymore but you can download the dumped game files at psxhax

I just thought the Uncharted textures might be similar to TLOU, and that I can modify my texture tool to work with it maybe. I won't download the whole game to see a couple of texture files though 

Still thanks for letting me know.

here, I put a couple files from the PS4 rip, specifically from the Uncharted 2 part

[https://sta.sh/0f0p0ra1dpm](https://sta.sh/0f0p0ra1dpm)
## Post #34
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-02-22T20:54:53+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from akderebur
>
> Faithfullfaun wrote:
I don't have them anymore but you can download the dumped game files at psxhax

I just thought the Uncharted textures might be similar to TLOU, and that I can modify my texture tool to work with it maybe. I won't download the whole game to see a couple of texture files though 

Still thanks for letting me know.

It's not like TLOU
it's like the ones from PS3 when you unpack them then you get the model with textures (haven't come pass that yet)
There are no texture folder by itself
## Post #35
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-22T22:34:29+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from volfin
>
> 
https://sta.sh/0f0p0ra1dpm
Thank you for the files.

> Reply from Faithfullfaun
>
> 
It's not like TLOU
it's like the ones from PS3 when you unpack them then you get the model with textures (haven't come pass that yet)
There are no texture folder by itself
It is almost identical to TLOU. TLOU also has some pak files that contain both model and textures, but the textures are low quality. Higher quality textures are in separate pak files.

Anway I was able to get the textures to load but the resolution is too low : 


I guess that is normal, considering the files are < 3MB. The higher resolution textures should be in another pak.
## Post #36
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-02-22T22:46:08+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Perhaps i can try searching for it 
can i just open it with the TLOU texture tool?
## Post #37
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-22T22:59:22+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from Faithfullfaun
>
> Perhaps i can try searching for it 
can i just open it with the TLOU texture tool?
No, I had to make some changes. I added the new version in attachments. No preview for faster loading. Load the pak, and select Export -> DDS.

Also if you find the higher res pak files, pm me or post it here please. I can make something more proper.

Edit : Find the tool in my next post.
## Post #38
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-23T04:25:34+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from akderebur
>
> Faithfullfaun wrote:Perhaps i can try searching for it 
can i just open it with the TLOU texture tool?
No, I had to make some changes. I added the new version in attachments. No preview for faster loading. Load the pak, and select Export -> DDS.

Also if you find the higher res pak files, pm me or post it here please. I can make something more proper.


The actor files are in actor27\ps4\, and the dictionaries for textures are under texturedict1\ps4\.



The CSV file seems to map filenames to which chunk pak. Here's one of the chunk files, and the CSV. 

Where I think it's going to be odd is chunk-21 seems to be split into two files, and common across 3 files. Not sure how you would handle that, so the two parts of chunk-21 is the ones i included.

I tried your tool you posted above on one of the files, but it didn't seem to work.
## Post #39
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-23T13:24:04+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from volfin
>
> 
Where I think it's going to be odd is chunk-21 seems to be split into two files, and common across 3 files. Not sure how you would handle that, so the two parts of chunk-21 is the ones i included.
Even though they are named as chunks, they both have header info. So they seem to be no different than separate pak files.

I updated the tool to support texture paks too. Seems to be working fine with the files you included :



Only dds export, and also no list this time. Loading all data uses too much memory. So just do File -> Open, and click "Start Export". You can export with folder structure if you want to, might be more organized.
[TextureEditor_UC.rar](https://xentaxbackup.github.io/file/13950_TextureEditor_UC.rar)
## Post #40
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-23T20:36:00+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from akderebur
>
> Even though they are named as chunks, they both have header info. So they seem to be no different than separate pak files.

I updated the tool to support texture paks too. Seems to be working fine with the files you included :

Only dds export, and also no list this time. Loading all data uses too much memory. So just do File -> Open, and click "Start Export". You can export with folder structure if you want to, might be more organized.

Works good. Now only if we had the models the textures go to.   For 1 and 2 especially, this was the Remastered Edition with higher resolution models and textures not seen before.
## Post #41
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-02-24T01:00:23+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from volfin
>
> akderebur wrote:Even though they are named as chunks, they both have header info. So they seem to be no different than separate pak files.

I updated the tool to support texture paks too. Seems to be working fine with the files you included :

Only dds export, and also no list this time. Loading all data uses too much memory. So just do File -> Open, and click "Start Export". You can export with folder structure if you want to, might be more organized.

Works good. Now only if we had the models the textures go to.   For 1 and 2 especially, this was the Remastered Edition with higher resolution models and textures not seen before.

Wait did they Update the meshes too?   

And that would be cool beacuse on the old ones from Uncharted 1-2 most of the characters
Have broken weights
## Post #42
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-24T04:10:40+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from Faithfullfaun
>
> volfin wrote:akderebur wrote:Even though they are named as chunks, they both have header info. So they seem to be no different than separate pak files.

I updated the tool to support texture paks too. Seems to be working fine with the files you included :

Only dds export, and also no list this time. Loading all data uses too much memory. So just do File -> Open, and click "Start Export". You can export with folder structure if you want to, might be more organized.

Works good. Now only if we had the models the textures go to.   For 1 and 2 especially, this was the Remastered Edition with higher resolution models and textures not seen before.

Wait did they Update the meshes too?   

And that would be cool beacuse on the old ones from Uncharted 1-2 most of the characters
Have broken weights

yep, new models and textures. This video compares the versions:

[https://youtu.be/PO0GgWe92fY?t=120](https://youtu.be/PO0GgWe92fY?t=120)
## Post #43
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-24T11:27:13+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

I took a quick look at the pak files for mesh data. "chloe-winter.pak" works really similar to TLOU models, with chunk relative offsets and relocation table. "chloe.pak" also appears to be same, but for some reason all the offsets are absolute (from the beginning of the file). I haven't seen that with TLOU files, everything was relative.

I was able to load some of the meshes. Other ones have offsets that don't point to right data. There is probably an extra offset that I haven't figured out.

Still it looks kinda complete with these meshes. Maybe other ones are just LODs.
## Post #44
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-24T16:41:15+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from akderebur
>
> I took a quick look at the pak files for mesh data. "chloe-winter.pak" works really similar to TLOU models, with chunk relative offsets and relocation table. "chloe.pak" also appears to be same, but for some reason all the offsets are absolute (from the beginning of the file). I haven't seen that with TLOU files, everything was relative.

I was able to load some of the meshes. Other ones have offsets that don't point to right data. There is probably an extra offset that I haven't figured out.

Still it looks kinda complete with these meshes. Maybe other ones are just LODs.

Probably are LODs. Looking good so far
## Post #45
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-25T03:42:11+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

daemon1, should we continue discussing the ps4 version here? Even though it is Uncharted trilogy, it is a different game and not exactly related to your tool. If you want this thread to be about your tool, I can open a new topic.
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-26T15:29:16+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Do as you like
## Post #47
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-28T21:33:35+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

For those who are interested, akderebur finished a model tool for the PS4 version and posted it here:

[viewtopic.php?f=16&t=17762](http://forum.xentax.com/viewtopic.php?f=16&t=17762)
## Post #48
- Username: ebross67
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 04, 2016 1:42 am
- Post datetime: 2018-08-04T15:39:57+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

What model viewer do you use to convert .smd to .obj? Does 3D Studio Max or Blender support .smd?
## Post #49
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2018-08-04T15:41:04+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from ebross67
>
> What model viewer do you use to convert .smd to .obj? Does 3D Studio Max or Blender support .smd?

Noesis can convert them
## Post #50
- Username: BigGeyAl76
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 10, 2020 2:36 pm
- Post datetime: 2020-05-10T06:44:39+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

How do you even us it? it"s 60kilobytes, and just pulls up console for 2 seconds before crashing. thanks for the virus.
## Post #51
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-10T08:01:40+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from BigGeyAl76 ↑Sun May 10, 2020 2:44 pm at Sun May 10, 2020 2:44 pm
>
> 
How do you even us it? it"s 60kilobytes, and just pulls up console for 2 seconds before crashing. thanks for the virus.
If you never used console tools it doesnt mean its not working. Learn.
## Post #52
- Username: Neo241
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 08, 2020 3:06 pm
- Post datetime: 2020-12-18T09:01:14+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Can this be updated to map the textures/materials and/or get the correct positions on the maps?
## Post #53
- Username: modz2014
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 30, 2021 10:42 pm
- Post datetime: 2021-12-30T15:11:37+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Pm me i have something interested in the source code please
## Post #54
- Username: sameidandpw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 29, 2020 8:27 pm
- Post datetime: 2023-07-12T18:19:45+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

Git repo?
## Post #55
- Username: sameidandpw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 29, 2020 8:27 pm
- Post datetime: 2023-07-13T14:08:03+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

TextureEditor_UC gives only 64x64 textures?
## Post #56
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-13T15:10:06+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from sameidandpw ↑Thu Jul 13, 2023 10:08 pm at Thu Jul 13, 2023 10:08 pm
>
> 
TextureEditor_UC gives only 64x64 textures?
dont use TextureEditor_UC
## Post #57
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-10-20T15:52:45+00:00
- Post Title: Re: Uncharted 1/2/3 (PS3)

> Reply from akderebur ↑Fri Feb 23, 2018 9:24 pm at Fri Feb 23, 2018 9:24 pm
>
> 
Even though they are named as chunks, they both have header info. So they seem to be no different than separate pak files.

I updated the tool to support texture paks too. Seems to be working fine with the files you included :



Only dds export, and also no list this time. Loading all data uses too much memory. So just do File -> Open, and click "Start Export". You can export with folder structure if you want to, might be more organized.

Does this also work for the remastered editions too? Because I exported textures with it but some of the dds files simply are corrupt or don't open in Photoshop with the plugin I have, but most of the other ones work.
