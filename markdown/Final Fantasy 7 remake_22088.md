## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-04-30T09:29:26+00:00
- Post Title: Final Fantasy 7 remake

Final Fantasy 7 remake tool.

Supports static & skeletal models, maps, textures. Usage instructions below.







Textures will be auto-assigned if you extract them before loading the map:

[ff7r.rar](https://xentaxbackup.github.io/file/18060_ff7r.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-04-30T09:30:57+00:00
- Post Title: Final Fantasy 7 remake

You can use the tool to convert individual assets, or all assets in a folder.

1. To convert one asset, drop asset file onto the tool, or run the tool from command line with asset filename as parameter.

If asset file contains a texture, in will be exported to "textures" subfolder in Directx10 DDS format. After that you can convert them to the format you like.

If asset file contains static or skeletal mesh, in will be exported to ASCII. Raw data will also be saved in "staticmesh.raw" & "skeletalmesh.raw" folders for later use in map extraction.

If asset file contains a material, it will export material info in a text file, and create "material.db" file with information for later use in map extraction. If "material.db" file already exists next to the tool, it will be updated with newly found materials.

If asset file contains a blueprint, it will create "blueprint.db" file with information for later use in map extraction. If "blueprint.db" file already exists next to the tool, it will be updated with newly found blueprints.

2. To convert all assets in a folder, place the tool in that folder and run it. Tool will search that folder and all subfolders for .uasset files and try converting them all. When prompted "are you sure?" you can press "enter" to confirm or Ctrl-C to cancel.

3. To convert maps, drop .umap file onto the tool, or run the tool from command line with umap filename as parameter. Current version will extract static meshes, skeletal meshes, blueprint-generated meshes, lights and landscapes from a map.

For map extraction to work, "staticmesh.raw" and "skeletalmesh.raw" folders with previously extracted data must be in the same folder with the tool. If some models will be missing, tool will give messages.

If "blueprint.db" file will be next to the tool, it will try and place all models mentioned in blueprints on the map. There's no proper blueprint support, so some models may be placed incorrectly.

If "material.db" file will be next to the tool, material information from that file will be used to place texture names in the output ASCII file, so when loaded, all textures will be applied automatically. By default, ASCII file will have texture names with ".PNG" format. If you converted textures to another format (for example .JPG), you need to replace ".png" to ".jpg" in ASCII file with any text editor before loading it.

If there will be no "material.db" file, or some materials will be missing in that file, tool will give messages and material names will be used for textures. In that case you can search and apply them manually. Some models do not use any textures (for example, solid color materials or lights). For such models ascii file will also have material name as texture name, so if you want, you can open that material in umodel and see whats the color and other properties.

note: blueprints are not properly supported, because i'm not going to read their code at all. This would be just too complicated. Since most blueprints just have 1 mesh inside and some logic, i'm assuming they are simply placing that mesh. In reality, the mesh position may be edited or calculated accoridng to game logic, or removed at all - this is all NOT supported.
## Post #3
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-04-30T18:53:05+00:00
- Post Title: Final Fantasy 7 remake

Big thanx for your tool, as always, it is very useful and understandable to use.
## Post #4
- Username: Soniccol13
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 01, 2020 4:53 am
- Post datetime: 2020-04-30T22:12:39+00:00
- Post Title: Final Fantasy 7 remake

Does anyone know where i can get the files?
## Post #5
- Username: Judojiop
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 01, 2020 11:36 am
- Post datetime: 2020-05-01T03:40:28+00:00
- Post Title: Final Fantasy 7 remake

Thank you very much for your hard work and also for providing the tool plus the detailed instructions. Much appreciated
## Post #6
- Username: kenshin20080
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 20, 2020 11:47 pm
- Post datetime: 2020-05-01T06:18:35+00:00
- Post Title: Final Fantasy 7 remake

OMG! Thank you so much!
## Post #7
- Username: jusete
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 19, 2014 8:00 pm
- Post datetime: 2020-05-01T06:49:28+00:00
- Post Title: Final Fantasy 7 remake

I've got the game installed, how can I extract the files so I can export them with your tool? Thanks for your work!
## Post #8
- Username: seiken
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 01, 2018 3:08 am
- Post datetime: 2020-05-01T07:10:32+00:00
- Post Title: Final Fantasy 7 remake

Many thanks !
## Post #9
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2020-05-01T11:34:50+00:00
- Post Title: Final Fantasy 7 remake

No game file download
## Post #10
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-05-01T16:06:44+00:00
- Post Title: Final Fantasy 7 remake

You have made a lot of improvements in this regard. Really amazing.
I used to have to examine all the data to find the Textures before. Now, the tool states in an extra form for textures.
## Post #11
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2020-05-01T23:32:34+00:00
- Post Title: Final Fantasy 7 remake

Can anybody rip some locations for me with textures? Tifa bar and/or Mako reactor? blender/max/maya - whichever you can send

I've scoured the internet top to bottom but was unable to find the gamefiles. I'm not really interested in character models, just the locations. I would like to try to assemble them in UE4 just for fun of it.
## Post #12
- Username: lethal01
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 01, 2020 4:07 pm
- Post datetime: 2020-05-02T03:39:03+00:00
- Post Title: Final Fantasy 7 remake

Seems like this will be perfect once I find a way to actually get my hands on the files.
Any chance of you putting the locations you already ripped up somewhere?
## Post #13
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-05-02T07:09:18+00:00
- Post Title: Final Fantasy 7 remake

Anyone willing to share the info (PM is fine too) with the decryption key to PKG?
I'd appreciate it.
## Post #14
- Username: lethal01
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 01, 2020 4:07 pm
- Post datetime: 2020-05-02T09:13:53+00:00
- Post Title: Final Fantasy 7 remake

One question do you know or can anyone guess what the  Hair_NB textures are for and which uv set they are meant to be used with.? Maybe a tangent map?
## Post #15
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2020-05-02T13:49:31+00:00
- Post Title: Final Fantasy 7 remake

Any kind soul willing to link me the PKG and decryption key? Want to look into model replacements to hopefully replace Tifa's model with the Dissidia NT by rigging it among some other stuff.
## Post #16
- Username: Hatredboy
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 21, 2017 7:48 am
- Post datetime: 2020-05-03T07:59:58+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from daemon1 ↑Thu Apr 30, 2020 5:29 pm at Thu Apr 30, 2020 5:29 pm
>
> 
Final Fantasy 7 remake tool.

Supports static & skeletal models, maps, textures. Usage instructions below.

That's...amazing!!!
## Post #17
- Username: ProGamer
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Sep 05, 2019 4:44 pm
- Post datetime: 2020-05-04T12:01:47+00:00
- Post Title: Re: Final Fantasy 7 remake

Thank you for the work you do I already have all the files Is it possible to add to the tool to extract the animations The animations really interest me
## Post #18
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-05-04T12:12:59+00:00
- Post Title: Re: Final Fantasy 7 remake

You were told to buzz off on zenhax and now you came here to pet your ego?
## Post #19
- Username: ProGamer
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Sep 05, 2019 4:44 pm
- Post datetime: 2020-05-04T12:17:09+00:00
- Post Title: Re: Final Fantasy 7 remake

> You were told to buzz off on zenhax and now you came here to pet your ego?

I have the right to be where I want thank you
Mind your own business   

I reported you

This is my last answer for people like you
## Post #20
- Username: jaxx21
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 11, 2020 12:00 am
- Post datetime: 2020-05-04T14:14:53+00:00
- Post Title: Re: Final Fantasy 7 remake

Do not take care of these jealous, you do a good job and you share everything. I'm fine with it. Each his sources. Thanks again for everything. Please continue without taking care of them.
## Post #21
- Username: ProGamer
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Sep 05, 2019 4:44 pm
- Post datetime: 2020-05-04T17:43:34+00:00
- Post Title: Re: Final Fantasy 7 remake

> Do not take care of these jealous, you do a good job and you share everything. I'm fine with it. Each his sources. Thanks again for everything. Please continue without taking care of them.

Thank you very much, I do not pay attention to these jealous.
## Post #22
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-05-04T20:30:58+00:00
- Post Title: Re: Final Fantasy 7 remake

Thanks Daemon for you hard work on the tools.
## Post #23
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2020-05-05T00:11:58+00:00
- Post Title: Re: Final Fantasy 7 remake

First of all thanks for the tool !
And now the problem i have with it..   
I've followed what was said to extract map putting all needed together but after dropping the umap file on the exe i end with just 3 text files import export and names so i suppose i'm doing something wrong there.
If someone who made it work and know how to do it properly can explain in more details or give some lights on what i do wrong it would be really nice.
To give more details of what ive done so far :
converted all assets.
Got the "staticmesh.raw" & "skeletalmesh.raw" & "textures" folders.
Got "blueprint.db" & "material.db" files.
Exe tool in same folder.
Drag and drop of umap.
Got Import , export , names txt files only.
## Post #24
- Username: blaen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 12, 2010 3:45 am
- Post datetime: 2020-05-05T06:09:33+00:00
- Post Title: Re: Final Fantasy 7 remake

Looks awesome.

I'd love to try this but like many others I don't have the pkg key. Is anyone able to PM me anything?
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-05T08:26:08+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Hevon ↑Tue May 05, 2020 8:11 am at Tue May 05, 2020 8:11 am
>
> 
Drag and drop of umap.
Got Import , export , names txt files only.
That umap file probably contains no objects.
## Post #26
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2020-05-05T09:35:34+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from daemon1 ↑Tue May 05, 2020 4:26 pm at Tue May 05, 2020 4:26 pm
>
> 
Hevon wrote: ↑Tue May 05, 2020 8:11 am
Drag and drop of umap.
Got Import , export , names txt files only.

That umap file probably contains no objects.
 Tried different kind of umap files and all of them give me text files its weird.
I think i know why it doesnt work and its because i try using this tool with the files of the demo.
## Post #27
- Username: jusete
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 19, 2014 8:00 pm
- Post datetime: 2020-05-05T11:35:58+00:00
- Post Title: Re: Final Fantasy 7 remake

where are located the .umap files needed for the environments?
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-05T11:41:35+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Hevon ↑Tue May 05, 2020 5:35 pm at Tue May 05, 2020 5:35 pm
>
> 
I think i know why it doesnt work and its because i try using this tool with the files of the demo.
no, it works with the demo.
Level files are in "level" folder, then inside each map - "layout" subfolder
## Post #29
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2020-05-05T11:53:39+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from daemon1 ↑Tue May 05, 2020 7:41 pm at Tue May 05, 2020 7:41 pm
>
> 
Hevon wrote: ↑Tue May 05, 2020 5:35 pm
I think i know why it doesnt work and its because i try using this tool with the files of the demo.

no, it works with the demo.
Level files are in "level" folder, then inside each map - "layout" subfolder

Well then i guess no luck for me , i do something wrong for sure but what ? i dunno i really think i followed correctly what was said to use the tool hmm.
I think if you could do a step by step of what to do would help to see what i did wrong if you have time for it of course. And thanks for helping already.
## Post #30
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-05-05T17:25:26+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Hevon ↑Tue May 05, 2020 7:53 pm at Tue May 05, 2020 7:53 pm
>
> i do something wrong for sure but what ?
Once you have all required files, make sure to have them in same folder where the UMAP your trying to convert is, then you'll get what you need.
## Post #31
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2020-05-05T21:09:24+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from mono24 ↑Wed May 06, 2020 1:25 am at Wed May 06, 2020 1:25 am
>
> 
Hevon wrote: ↑Tue May 05, 2020 7:53 pmi do something wrong for sure but what ?
Once you have all required files, make sure to have them in same folder where the UMAP your trying to convert is, then you'll get what you need.

Nice finally working ! got the 3D models just need to add textures one by one cause it didnt found it directly in the folder. Any idea how to get missing textures ? some seems not being converted or something.
Thanks a lot more making things clear  and thanks to  daemon1 too !
## Post #32
- Username: doguy258
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 06, 2020 7:58 am
- Post datetime: 2020-05-06T00:02:27+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Hevon ↑Wed May 06, 2020 5:09 am at Wed May 06, 2020 5:09 am
>
> 
mono24 wrote: ↑Wed May 06, 2020 1:25 am
Hevon wrote: ↑Tue May 05, 2020 7:53 pmi do something wrong for sure but what ?
Once you have all required files, make sure to have them in same folder where the UMAP your trying to convert is, then you'll get what you need.


Nice finally working ! got the 3D models just need to add textures one by one cause it didnt found it directly in the folder. Any idea how to get missing textures ? some seems not being converted or something.
Thanks a lot more making things clear  and thanks to  daemon1 too !

Hey Hevon,

I am stuck the same way you were. I keep getting text files when I try dropping the .umap over the tool. How do I know what files need to be in the same folder as the .umap?  Mind sharing what you did?
## Post #33
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-05-06T00:15:00+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Hevon ↑Wed May 06, 2020 5:09 am at Wed May 06, 2020 5:09 am
>
> Any idea how to get missing textures ?
For ALL textures to be loaded, automatically, you need to make sure on next step, converted UMAPs must be moved to textures folder, otherwise it wont work.
## Post #34
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2020-05-06T00:23:55+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from doguy258 ↑Wed May 06, 2020 8:02 am at Wed May 06, 2020 8:02 am
>
> 

I am stuck the same way you were. I keep getting text files when I try dropping the .umap over the tool. How do I know what files need to be in the same folder as the .umap?  Mind sharing what you did?

After converting all assets with the tool i take :
tool exe file
blueprint.db
material.db
textures folder
staticmesh.raw folder
skeletalmesh.raw folder

And for exemple if i want the maps when you start the game i go to this path  \Level\Game\Field\010-MAKO1\Layout_Merge and put all the folders and files i listed before into this directory.
You should find umaps files.
Then i drag and drop 010-MAKO1_Layout_010-Station.umap on the exe tool and it should make ASCII file.

> Reply from mono24 ↑Wed May 06, 2020 8:15 am at Wed May 06, 2020 8:15 am
>
> 
Hevon wrote: ↑Wed May 06, 2020 5:09 amAny idea how to get missing textures ?
For ALL textures to be loaded, automatically, you need to make sure on next step, converted UMAPs must be moved to textures folder, otherwise it wont work.
Thanks it fixed my problem  

ps:Forgot to say i converted all the DDS texture into png to make it work because the ASCII file when loaded is looking for png files.
## Post #35
- Username: doguy258
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 06, 2020 7:58 am
- Post datetime: 2020-05-06T00:38:49+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Hevon ↑Wed May 06, 2020 8:23 am at Wed May 06, 2020 8:23 am
>
> 

After converting all assets with the tool i take :
tool exe file
blueprint.db
material.db
textures folder
staticmesh.raw folder
skeletalmesh.raw folder

And for exemple if i want the maps when you start the game i go to this path  \Level\Game\Field\010-MAKO1\Layout_Merge and put all the folders and files i listed before into this directory.
You should find umaps files.
Then i drag and drop 010-MAKO1_Layout_010-Station.umap on the exe tool and it should make ASCII file.

When you say "after converting all assets" do I literally mean ALL or just the models, materials, and textures? For instance, I am trying to recreate the seventh heaven bar. I have the models and textures converted. Is there more that needs to be converted before taking the steps that you mentioned?

Thanks for the quick reply BTW!
## Post #36
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-05-06T06:05:58+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Hevon ↑Wed May 06, 2020 8:23 am at Wed May 06, 2020 8:23 am
>
> ps:Forgot to say i converted all the DDS texture into png to make it work because the ASCII file when loaded is looking for png files.
Convert the Layout, not Layout_merge.
As for ASCIIs, change the PNG to DDS using Notepad++, its faster than windows notepad.
## Post #37
- Username: jusete
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 19, 2014 8:00 pm
- Post datetime: 2020-05-06T08:31:04+00:00
- Post Title: Re: Final Fantasy 7 remake

Are the files to extract in the folder called "Environments"? For the .umap you said, Mako1, the models to extract are from 1st Avenue? Thansk!
## Post #38
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2020-05-06T14:04:17+00:00
- Post Title: Re: Final Fantasy 7 remake

anyone pm me file. plz  

edit: Done, im Happy
## Post #39
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2020-05-06T16:10:16+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from doguy258 ↑Wed May 06, 2020 8:38 am at Wed May 06, 2020 8:38 am
>
> 

When you say "after converting all assets" do I literally mean ALL or just the models, materials, and textures? For instance, I am trying to recreate the seventh heaven bar. I have the models and textures converted. Is there more that needs to be converted before taking the steps that you mentioned?

Thanks for the quick reply BTW!

Just models materials and textures yes 

> Reply from mono24 ↑Wed May 06, 2020 2:05 pm at Wed May 06, 2020 2:05 pm
>
> 
Hevon wrote: ↑Wed May 06, 2020 8:23 amps:Forgot to say i converted all the DDS texture into png to make it work because the ASCII file when loaded is looking for png files.
Convert the Layout, not Layout_merge.
As for ASCIIs, change the PNG to DDS using Notepad++, its faster than windows notepad.
 Oh ok i was converting wrong one even if it was working and i tried using notpad to change png to dds but the ASCII file when loaded in blender its empty.
## Post #40
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-05-06T18:04:08+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Hevon ↑Thu May 07, 2020 12:10 am at Thu May 07, 2020 12:10 am
>
> ...and i tried using notpad to change png to dds but the ASCII file when loaded in blender its empty.
I think Blender does NOT support all DDS types, might as well stick to PNG then.
## Post #41
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2020-05-07T10:07:25+00:00
- Post Title: Re: Final Fantasy 7 remake

Do I need a Blu-ray drive to extract? 
I want a environment asset
## Post #42
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-05-08T01:13:19+00:00
- Post Title: Re: Final Fantasy 7 remake

Skyview Hall is one of my favorites honestly. The music and the scenery
## Post #43
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2020-05-08T05:04:16+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Takato Matsukj ↑Fri May 08, 2020 9:13 am at Fri May 08, 2020 9:13 am
>
> 

Skyview Hall is one of my favorites honestly. The music and the scenery

Damn really great view and style.

Wanted to ask you if you had any idea of where could be the files of the backgrounds ?
I got all the maps of the demo but no background where we can see the clocktower for example.
Oh and did you add yourself all the lights and stuff ? if its the case well done
## Post #44
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2020-05-08T05:20:01+00:00
- Post Title: Re: Final Fantasy 7 remake

Interesting seeing people post but no sources for decrypted files....

Anyway, if someone could answer this I'd very much appreciate it. As we all know, at times the textures in this game look..... well.... bad. Hopefully it's a loading issue which will be patched whenever things return to semi-normal in Japan. However I have to wonder, if you can see the texture files, can you confirm if it's a loading bug or are the textures really just low resoultion?

Like this Chocobo poster for example. Horribly pixelated in the game.... is the actual file really this bad?
## Post #45
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2020-05-08T05:42:47+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Cloud452 ↑Fri May 08, 2020 1:20 pm at Fri May 08, 2020 1:20 pm
>
> 
Interesting seeing people post but no sources for decrypted files....

Anyway, if someone could answer this I'd very much appreciate it. As we all know, at times the textures in this game look..... well.... bad. Hopefully it's a loading issue which will be patched whenever things return to semi-normal in Japan. However I have to wonder, if you can see the texture files, can you confirm if it's a loading bug or are the textures really just low resoultion?

Like this Chocobo poster for example. Horribly pixelated in the game.... is the actual file really this bad?

It a bug for sure its stuck using lowres texture its well know with games using unreal engine so i'm not surprise to see that.
## Post #46
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-05-09T00:23:45+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Hevon ↑Fri May 08, 2020 1:04 pm at Fri May 08, 2020 1:04 pm
>
> 
Takato Matsukj wrote: ↑Fri May 08, 2020 9:13 am

Skyview Hall is one of my favorites honestly. The music and the scenery


Damn really great view and style.

Wanted to ask you if you had any idea of where could be the files of the backgrounds ?
I got all the maps of the demo but no background where we can see the clocktower for example.
Oh and did you add yourself all the lights and stuff ? if its the case well done

The background files you're looking for are called BackCloth. Just search your whole pak folder for that specific name.

And thank you. Yea I placed the lights myself. I couldn't find the proper floor/side lights so I just made cubes with emissions.(This was ported into Unity)
## Post #47
- Username: lethal01
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 01, 2020 4:07 pm
- Post datetime: 2020-05-09T00:28:33+00:00
- Post Title: Re: Final Fantasy 7 remake

I'm looking for the umap file for the scene where zack fights against the soldiers (doubting it was actually modeled)
Also the one for the flashback to nibleheim (assuming it exists once again)

Anyone seen umap files for these scene, what it's titled are and what files are required? 
Or are the character models the only things actually in game from these scenes?

Edit: Alright I found a wagon from the Nibleheim scene 
 so it seems it's realtime and there but I think my rip is missing assets.

I'll keep looking and ripping in the meantime but if anyone could rip these locations I'd be thankful.
## Post #48
- Username: HITHECHUN
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 10, 2020 2:32 am
- Post datetime: 2020-05-09T18:36:55+00:00
- Post Title: Re: Final Fantasy 7 remake

Thanks for sharing
## Post #49
- Username: kasake
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 16, 2012 3:03 pm
- Post datetime: 2020-05-09T19:33:15+00:00
- Post Title: Re: Final Fantasy 7 remake

Could someone tell me (perhaps via PM) how they're able to get their hands on the data files? Would be much appreciated!
## Post #50
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2020-05-09T19:51:56+00:00
- Post Title: Re: Final Fantasy 7 remake

If anyone has information on how to extract all the files from the .pkg or has other information    send me a private message, i have fiber optics so i have no bandwidth problems.
## Post #51
- Username: DPyro
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jul 12, 2010 3:06 am
- Post datetime: 2020-05-09T23:23:48+00:00
- Post Title: Re: Final Fantasy 7 remake

Looking for the same. PKG title key would be appreciated.
## Post #52
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-05-10T03:10:38+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lethal01 ↑Sat May 09, 2020 8:28 am at Sat May 09, 2020 8:28 am
>
> 
I'm looking for the umap file for the scene where zack fights against the soldiers (doubting it was actually modeled)
Also the one for the flashback to nibleheim (assuming it exists once again)

Anyone seen umap files for these scene, what it's titled are and what files are required? 
Or are the character models the only things actually in game from these scenes?

Edit: Alright I found a wagon from the Nibleheim scene 
 so it seems it's realtime and there but I think my rip is missing assets.

I'll keep looking and ripping in the meantime but if anyone could rip these locations I'd be thankful.

The nibelheim scene (along with 100% of the games flashbacks) are pre-rendered video files, if you go through the games video files you can see them.
For all of those, there is no map file.
There are however a few random assets. however those assets are not *from* the nibelheim scene itself, they're from the little area immediately after the first bombing mission, where Cloud walks through burning streets, the left side is nibelheim and the right is midgar, so those models are used for that scene, and are on fire. If you look at the scene where he fights the soldiers, its reusing the cliffs from the sector where Aerith lives.

Just so there isn't any missunderstanding, when I say pre-rendered, I also mean just videos of the game itself, because flashbacks happen so instantly that there wouldn't be time to load a whole new map and all the new models/animations in such a short time, so a video of those things happens instead.

That said, *some* of those assets still individually exist, such as young Aerith, Young Cloud, Young Tifa, eventhough you only ever see them in in-game graphic quality video files. I assume they intended to have it all realtime, but changed in the end.
## Post #53
- Username: Fraxul
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 08, 2014 10:00 am
- Post datetime: 2020-05-10T06:06:09+00:00
- Post Title: Re: Final Fantasy 7 remake

I would also love to know where to find the PKG key for this game. If anyone feels like sharing, please drop me a PM!
## Post #54
- Username: lethal01
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 01, 2020 4:07 pm
- Post datetime: 2020-05-10T10:08:30+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Sun May 10, 2020 11:10 am at Sun May 10, 2020 11:10 am
>
> 

The nibelheim scene (along with 100% of the games flashbacks) are pre-rendered video files, if you go through the games video files you can see them.
For all of those, there is no map file.
There are however a few random assets. however those assets are not *from* the nibelheim scene itself, they're from the little area immediately after the first bombing mission, where Cloud walks through burning streets, the left side is nibelheim and the right is midgar, so those models are used for that scene, and are on fire. If you look at the scene where he fights the soldiers, its reusing the cliffs from the sector where Aerith lives.

Thanks this was my assumption but I didn't wanna risk not asking. That wagon gave me a lot of hope but I realized the came from the Sephiroth flashback. Now I'm just porting the opening scene to blender.




I thought it could be useful is the 1/1000th scale from floor 60 on the shinra building. I'm seeing it listed as F60Midgulbase_01_0shinbuilding but can't find any other parts if anyone comes across the rest please share it's location or just the files
## Post #55
- Username: weirdalsuperfan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 23, 2019 5:54 pm
- Post datetime: 2020-05-10T19:01:35+00:00
- Post Title: Re: Final Fantasy 7 remake

Can someone tell me how to extract/decrypt the game pkg so it's in a usable format for this tool? Want to try and dump all the Japanese strings in the game.
## Post #56
- Username: lethal01
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 01, 2020 4:07 pm
- Post datetime: 2020-05-10T21:07:36+00:00
- Post Title: Re: Final Fantasy 7 remake

Has anyone been able to extract the backcloth(skybox) files that are larger than 80mb?
I just keep getting that memory error.
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-11T07:00:25+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lethal01 ↑Mon May 11, 2020 5:07 am at Mon May 11, 2020 5:07 am
>
> 
Has anyone been able to extract the backcloth(skybox) files that are larger than 80mb?
I just keep getting that memory error.
use my tool (ff7r.exe) to extract them from uasset in original DDS format.
They are floating point images, to keep wide range brightness values of the sky.
If you need, then you can convert them to some other format. But note that usual 8-bit image formats are not suitable for that.
## Post #58
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2020-05-12T09:19:58+00:00
- Post Title: Re: Final Fantasy 7 remake

Any plans of support animations? or it's too much to ask?
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-12T15:00:11+00:00
- Post Title: Re: Final Fantasy 7 remake

its already supported by someone else
## Post #60
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2020-05-12T16:51:37+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from daemon1 ↑Tue May 12, 2020 11:00 pm at Tue May 12, 2020 11:00 pm
>
> 
its already supported by someone else

Via PM maybe?
## Post #61
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2020-05-12T18:08:09+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from daemon1 ↑Thu Apr 30, 2020 5:30 pm at Thu Apr 30, 2020 5:30 pm
>
> 
If asset file contains static or skeletal mesh, in will be exported to ASCII. Raw data will also be saved in "staticmesh.raw" & "skeletalmesh.raw" folders for later use in map extraction.

What plugin do i use for importing those ASCII and raw models into blender? smd is for skeleton, i get that much. But everything else is a mistery for me.

I tried renaming ascii to obj because both look very simmillar, but no luck.
## Post #62
- Username: lethal01
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 01, 2020 4:07 pm
- Post datetime: 2020-05-12T22:52:53+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from daemon1 ↑Mon May 11, 2020 3:00 pm at Mon May 11, 2020 3:00 pm
>
> 
use my tool (ff7r.exe) to extract them from uasset in original DDS format.
They are floating point images, to keep wide range brightness values of the sky.
If you need, then you can convert them to some other format. But note that usual 8-bit image formats are not suitable for that.

Thanks,
 I should have figured it out but Im' bouncing between playing around with this and other stuff.
## Post #63
- Username: escrl141
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 16, 2018 11:26 pm
- Post datetime: 2020-05-13T12:55:39+00:00
- Post Title: Re: Final Fantasy 7 remake

I've done everything and successfully extracted an environment map, but can anyone share the best way to open the ascii file in blender 2.82?
edit:solved (xps/ascii plugin for blender)

thanks for the tool!
## Post #64
- Username: WeissKalt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 14, 2020 4:43 am
- Post datetime: 2020-05-13T20:56:58+00:00
- Post Title: Re: Final Fantasy 7 remake

Would anyone be kind as to send me a PM with the asset files for this please and thank you?
## Post #65
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-05-14T06:25:36+00:00
- Post Title: Re: Final Fantasy 7 remake

Hi, daemon1 tool is amazing  but i still not understand how perfectly maps extraction works, or well, I managed to get some sceneries, but are incomplete, I always have a missed models error, and I missed blueprint.db
What i did:
1 with umodel I extracted from paks, ALL the content of environments and sceneries folders (uassets, uexp and ubulk)
2 placed all these extracted files in one folder (around 100.000 files)
3 launched ff7rem.exe tool (it extracted all good, created folders and the material.db file)
I open a .layout umap file with the tool, but nothing.
Can you please write detailled steps to make this works?

Thank you in advance

**Nevermind. I did it!!!
## Post #66
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-05-14T12:49:45+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from fil1969 ↑Thu May 14, 2020 2:25 pm at Thu May 14, 2020 2:25 pm
>
> 
Hi, daemon1 tool is amazing  but i still not understand how perfectly maps extraction works, or well, I managed to get some sceneries, but are incomplete, I always have a missed models error, and I missed blueprint.db
What i did:
1 with umodel I extracted from paks, ALL the content of environments and sceneries folders (uassets, uexp and ubulk)
2 placed all these extracted files in one folder (around 100.000 files)
3 launched ff7rem.exe tool (it extracted all good, created folders and the material.db file)
I open a .layout umap file with the tool, but nothing.
Can you please write detailled steps to make this works?

Thank you in advance

**Nevermind. I did it!!!

Hi fil. Could you explain how you solve it ? If other user have the same problem  they can know how to solve it.

Thanks,
Drawing
## Post #67
- Username: Aentropy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 15, 2020 3:14 am
- Post datetime: 2020-05-14T21:15:31+00:00
- Post Title: Re: Final Fantasy 7 remake

Sorry, I am new to this. Where do you get the game data from to use the tool with? Do you need to get the data from the Bluray disc to your computer?
## Post #68
- Username: JunHimekawa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 06, 2020 1:16 pm
- Post datetime: 2020-05-14T23:03:43+00:00
- Post Title: Re: Final Fantasy 7 remake

Thank you for the tool! It's my first time trying to extract models. I'm trying to extract the Church, but I'm not getting the .umap or blueprint files. Am I doing something wrong?
## Post #69
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-05-15T05:02:24+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Drawing ↑Thu May 14, 2020 8:49 pm at Thu May 14, 2020 8:49 pm
>
> 
fil1969 wrote: ↑Thu May 14, 2020 2:25 pm
Hi, daemon1 tool is amazing  but i still not understand how perfectly maps extraction works, or well, I managed to get some sceneries, but are incomplete, I always have a missed models error, and I missed blueprint.db
What i did:
1 with umodel I extracted from paks, ALL the content of environments and sceneries folders (uassets, uexp and ubulk)
2 placed all these extracted files in one folder (around 100.000 files)
3 launched ff7rem.exe tool (it extracted all good, created folders and the material.db file)
I open a .layout umap file with the tool, but nothing.
Can you please write detailled steps to make this works?

Thank you in advance

**Nevermind. I did it!!! 


Hi fil. Could you explain how you solve it ? If other user have the same problem  they can know how to solve it.

Thanks,
Drawing
I make it work in this way:
1 with umodel I saved NOT extracted from paks, ALL the content of environments and sceneries and blueprint folders (uassets, uexp and ubulk)
2 placed all these extracted files in one folder (around 100.000 files)
3 launched ff7rem.exe tool (it extracted all good, created folders and the material.db and blueprint.db files)
4 with umodel I saved the umap i want ( located in: level--> game-->field-->*subfoldernameyouchoose*-->LAYOUT not LAYOUTMERGE)
5 dropped the umap into the tool, all was converted good (only some errors regarding materials but that is normal since the game use shaders only on some models, like lights etc.
6 I put the generetad mesh.ascii in the textures folder
NOTE: I previously converted ALL the FF7rem tool generated DDS textures in PNG format.
7 Imported the mesh ascii in blender using this script: [https://www.deviantart.com/johnzero7/jo ... -834572824](https://www.deviantart.com/johnzero7/journal/XPS-tools-2-0-2-for-Blender-2-80-834572824)

[](https://ibb.co/Dkrkz8v)

[](https://ibb.co/2F6yqyv)

this is the result, i
Hope this will be usefull.
## Post #70
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-05-15T11:23:30+00:00
- Post Title: Re: Final Fantasy 7 remake

Thanks man
## Post #71
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-15T14:58:12+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from fil1969 ↑Fri May 15, 2020 1:02 pm at Fri May 15, 2020 1:02 pm
>
> 
2 placed all these extracted files in one folder (around 100.000 files)
You dont have to do that. Tool will properly use all of the files in its directory and all subfolders (as its said in description)
## Post #72
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-05-15T16:29:25+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from daemon1 ↑Fri May 15, 2020 10:58 pm at Fri May 15, 2020 10:58 pm
>
> 
fil1969 wrote: ↑Fri May 15, 2020 1:02 pm
2 placed all these extracted files in one folder (around 100.000 files)

You dont have to do that. Tool will properly use all of the files in its directory and all subfolders (as its said in description)

oh, thanks, and the others steps i did, are correct?
## Post #73
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-05-15T18:41:37+00:00
- Post Title: Re: Final Fantasy 7 remake

Aerith's home is legit one of my fav in the game
So glad I did it.

Somethings are missing like lamps and stuff but eh it's not noticeable for a daytime map.
## Post #74
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-05-15T20:19:15+00:00
- Post Title: Re: Final Fantasy 7 remake

Lighting is too plain and direct for the render.
## Post #75
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-05-15T23:36:33+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Kein ↑Sat May 16, 2020 4:19 am at Sat May 16, 2020 4:19 am
>
> 
Lighting is too plain and direct for the render.

Its not a render bud. Just a screenshot of my scene in unity.Its a work-in-progress Sorry you don't like it but its whatever lol
## Post #76
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-05-16T08:57:07+00:00
- Post Title: Re: Final Fantasy 7 remake

> Its not a render bud.

> Just a screenshot of my scene in unity.
And? Unity does not render or something? It has dedicated rendering system and pipiline and you should stop reacting this extreme to a simple non-demanding criticism.
## Post #77
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-05-16T09:28:50+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Kein ↑Sat May 16, 2020 4:57 pm at Sat May 16, 2020 4:57 pm
>
> 
Its not a render bud.
Just a screenshot of my scene in unity.
And? Unity does not render or something? It has dedicated rendering system and pipiline and you should stop reacting this extreme to a simple non-demanding criticism.
why instead of criticize, you don't do it yourself??
## Post #78
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-05-16T10:11:31+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from fil1969 ↑Sat May 16, 2020 12:29 am at Sat May 16, 2020 12:29 am
>
> 
oh, thanks, and the others steps i did, are correct?
i'm not entirely sure in your description, but probably yes
## Post #79
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-05-16T13:42:48+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Kein ↑Sat May 16, 2020 4:57 pm at Sat May 16, 2020 4:57 pm
>
> 
Its not a render bud.
Just a screenshot of my scene in unity.
And? Unity does not render or something? It has dedicated rendering system and pipiline and you should stop reacting this extreme to a simple non-demanding criticism.

Relax, your comment is unnecessary. Literally I said, its a work-in-progress and you expect the picture to be with the upmost expectations of being a perfect Render when its not even intended to be one. I don't get why you had to say "you should stop reacting this extreme to a simple non-demanding criticism." Sounds like your full of yourself. Totally unnecessary... the way I reacted was not extreme.

Simple enough, do it yourself
## Post #80
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-05-16T13:54:22+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from fil1969 ↑Sat May 16, 2020 5:28 pm at Sat May 16, 2020 5:28 pm
>
> 
Kein wrote: ↑Sat May 16, 2020 4:57 pm
Its not a render bud.
Just a screenshot of my scene in unity.
And? Unity does not render or something? It has dedicated rendering system and pipiline and you should stop reacting this extreme to a simple non-demanding criticism.

why instead of criticize, you don't do it yourself??

He has nothing better to do.
## Post #81
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-05-16T14:22:11+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Takato Matsukj ↑Sat May 16, 2020 9:42 pm at Sat May 16, 2020 9:42 pm
>
> 
Relax, your comment is unnecessary.
I will be the judge to that.
## Post #82
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-05-16T14:29:55+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Kein ↑Sat May 16, 2020 10:22 pm at Sat May 16, 2020 10:22 pm
>
> 
Takato Matsukj wrote: ↑Sat May 16, 2020 9:42 pm
Relax, your comment is unnecessary.
I will be the judge to that.

I like your attitude.
## Post #83
- Username: ils
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 25, 2010 12:36 pm
- Post datetime: 2020-05-24T11:59:59+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from fil1969 ↑Fri May 15, 2020 1:02 pm at Fri May 15, 2020 1:02 pm
>
> 
Drawing wrote: ↑Thu May 14, 2020 8:49 pm
fil1969 wrote: ↑Thu May 14, 2020 2:25 pm
Hi, daemon1 tool is amazing  but i still not understand how perfectly maps extraction works, or well, I managed to get some sceneries, but are incomplete, I always have a missed models error, and I missed blueprint.db
What i did:
1 with umodel I extracted from paks, ALL the content of environments and sceneries folders (uassets, uexp and ubulk)
2 placed all these extracted files in one folder (around 100.000 files)
3 launched ff7rem.exe tool (it extracted all good, created folders and the material.db file)
I open a .layout umap file with the tool, but nothing.
Can you please write detailled steps to make this works?

Thank you in advance

**Nevermind. I did it!!! 


Hi fil. Could you explain how you solve it ? If other user have the same problem  they can know how to solve it.

Thanks,
Drawing

I make it work in this way:
1 with umodel I saved NOT extracted from paks, ALL the content of environments and sceneries and blueprint folders (uassets, uexp and ubulk)
2 placed all these extracted files in one folder (around 100.000 files)
3 launched ff7rem.exe tool (it extracted all good, created folders and the material.db and blueprint.db files)
4 with umodel I saved the umap i want ( located in: level--> game-->field-->*subfoldernameyouchoose*-->LAYOUT not LAYOUTMERGE)
5 dropped the umap into the tool, all was converted good (only some errors regarding materials but that is normal since the game use shaders only on some models, like lights etc.
6 I put the generetad mesh.ascii in the textures folder
NOTE: I previously converted ALL the FF7rem tool generated DDS textures in PNG format.
7 Imported the mesh ascii in blender using this script: https://www.deviantart.com/johnzero7/jo ... -834572824





this is the result, i
Hope this will be usefull.

hi,
i follow your guide, but it seems the texture didn't load in Blender
i wonder if the steps is the same for characters file.

the ASCII load fine in blender, but no texture information in the ASCII files

here's my steps :
1. extract the "specific" PAK files using Noesis, QuickBMS or save using Umodel (all create the same file "\Character\Player\PC000x")
2. all those folders each contains "Material", "Model" and "Texture"
3. then i follow your guide (no. 2), place it in 1 folder "PC000x", and then run the ff7r.exe (this will create "materials", "skeletalmesh", "skeletalmesh.raw" and "texture" folder
4. i didn't find the ".umap" files from your guide (no. 4), is there any umap files for characters?
5. since i can't find umap files, i assume the "generated mesh.ascii" is the one on "skeletalmesh" folders? i copied it to texture folder
6. convert DDS to PNG (is this necessary?)
7. load in blender using the XPS tools, but the models are grey/no texture

also, in the ASCII files, there are no PNG/DDS references. i wonder how blender can correctly lookup the texture.

sorry i really noob in 3D modelling here
please advise

THANK YOU!
## Post #84
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-05-24T13:21:44+00:00
- Post Title: Re: Final Fantasy 7 remake

Anyone who know how to export animation?
## Post #85
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-05-24T14:03:18+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from linsaberlove ↑Sun May 24, 2020 9:21 pm at Sun May 24, 2020 9:21 pm
>
> 
Anyone who know how to export animation?
[https://www.gildor.org/smf/index.php/to ... l#msg36249](https://www.gildor.org/smf/index.php/topic,6925.msg36249.html#msg36249)
## Post #86
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-05-25T03:52:04+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Kein ↑Sun May 24, 2020 10:03 pm at Sun May 24, 2020 10:03 pm
>
> 
linsaberlove wrote: ↑Sun May 24, 2020 9:21 pm
Anyone who know how to export animation? 

https://www.gildor.org/smf/index.php/to ... l#msg36249
Thanks,I did it! But I still get some physical issues,when the character walk,her leg can be outside of the dress....Any idea how to fix that?
## Post #87
- Username: DioBrando
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 06, 2010 11:59 am
- Post datetime: 2020-05-26T00:56:24+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from linsaberlove ↑Mon May 25, 2020 11:52 am at Mon May 25, 2020 11:52 am
>
> 
Kein wrote: ↑Sun May 24, 2020 10:03 pm
linsaberlove wrote: ↑Sun May 24, 2020 9:21 pm
Anyone who know how to export animation? 

https://www.gildor.org/smf/index.php/to ... l#msg36249

Thanks,I did it! But I still get some physical issues,when the character walk,her leg can be outside of the dress....Any idea how to fix that?

Probably the dress is simulated. You'll need to run some kind of cloth sim.

There is a lot nicer way to view animations to:
Set “Tools->Data Viewer->Other->Default preview commands” to:
-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath "F:\FF7_Remake\End2\Content\GameContents"

"F:\FF7_Remake\End2\Content\GameContents" will be your GameContents with all the extracted packages obviously. This will load all the textures in the preview window too.

Load the model and just drag-and-drop the anim you want to apply to it over the preview window from windows explorer, or use the “apply to preview” script in optionalplugins.
## Post #88
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-05-26T03:26:07+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from DioBrando ↑Tue May 26, 2020 8:56 am at Tue May 26, 2020 8:56 am
>
> 
linsaberlove wrote: ↑Mon May 25, 2020 11:52 am
Kein wrote: ↑Sun May 24, 2020 10:03 pm


https://www.gildor.org/smf/index.php/to ... l#msg36249

Thanks,I did it! But I still get some physical issues,when the character walk,her leg can be outside of the dress....Any idea how to fix that? 


Probably the dress is simulated. You'll need to run some kind of cloth sim.

There is a lot nicer way to view animations to:
Set “Tools->Data Viewer->Other->Default preview commands” to:
-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath "F:\FF7_Remake\End2\Content\GameContents"

"F:\FF7_Remake\End2\Content\GameContents" will be your GameContents with all the extracted packages obviously. This will load all the textures in the preview window too.

Load the model and just drag-and-drop the anim you want to apply to it over the preview window from windows explorer, or use the “apply to preview” script in optionalplugins.

But cloth simulation is not the same for different 3d software, is there a way to get the game's cloth  simulation data
## Post #89
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-05-26T03:34:42+00:00
- Post Title: Re: Final Fantasy 7 remake

Yes, by importing into Unreal Engine and using their tookit.
## Post #90
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-05-26T04:06:46+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Sun May 10, 2020 11:10 am at Sun May 10, 2020 11:10 am
>
> 
lethal01 wrote: ↑Sat May 09, 2020 8:28 am
I'm looking for the umap file for the scene where zack fights against the soldiers (doubting it was actually modeled)
Also the one for the flashback to nibleheim (assuming it exists once again)

Anyone seen umap files for these scene, what it's titled are and what files are required? 
Or are the character models the only things actually in game from these scenes?

Edit: Alright I found a wagon from the Nibleheim scene 
 so it seems it's realtime and there but I think my rip is missing assets.

I'll keep looking and ripping in the meantime but if anyone could rip these locations I'd be thankful.


The nibelheim scene (along with 100% of the games flashbacks) are pre-rendered video files, if you go through the games video files you can see them.
For all of those, there is no map file.
There are however a few random assets. however those assets are not *from* the nibelheim scene itself, they're from the little area immediately after the first bombing mission, where Cloud walks through burning streets, the left side is nibelheim and the right is midgar, so those models are used for that scene, and are on fire. If you look at the scene where he fights the soldiers, its reusing the cliffs from the sector where Aerith lives.

Just so there isn't any missunderstanding, when I say pre-rendered, I also mean just videos of the game itself, because flashbacks happen so instantly that there wouldn't be time to load a whole new map and all the new models/animations in such a short time, so a video of those things happens instead.

That said, *some* of those assets still individually exist, such as young Aerith, Young Cloud, Young Tifa, eventhough you only ever see them in in-game graphic quality video files. I assume they intended to have it all realtime, but changed in the end.
Where are these video files? Can't find them,folder location plz
## Post #91
- Username: gamenpc
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 02, 2020 10:35 am
- Post datetime: 2020-05-26T04:14:01+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from DioBrando ↑Tue May 26, 2020 8:56 am at Tue May 26, 2020 8:56 am
>
> 
linsaberlove wrote: ↑Mon May 25, 2020 11:52 am
Kein wrote: ↑Sun May 24, 2020 10:03 pm


https://www.gildor.org/smf/index.php/to ... l#msg36249

Thanks,I did it! But I still get some physical issues,when the character walk,her leg can be outside of the dress....Any idea how to fix that? 


Probably the dress is simulated. You'll need to run some kind of cloth sim.

There is a lot nicer way to view animations to:
Set “Tools->Data Viewer->Other->Default preview commands” to:
-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath "F:\FF7_Remake\End2\Content\GameContents"

"F:\FF7_Remake\End2\Content\GameContents" will be your GameContents with all the extracted packages obviously. This will load all the textures in the preview window too.

Load the model and just drag-and-drop the anim you want to apply to it over the preview window from windows explorer, or use the “apply to preview” script in optionalplugins.

Thanks, I did it. Buy……  
[](https://www.overpic.net/viewer.php?file=xp9hh4mfeb8hyi7hhxi4e.jpg)

I want to import unity. 
Sorry, my English is terrible.
## Post #92
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-05-26T04:24:42+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from gamenpc ↑Tue May 26, 2020 12:14 pm at Tue May 26, 2020 12:14 pm
>
> 
DioBrando wrote: ↑Tue May 26, 2020 8:56 am
linsaberlove wrote: ↑Mon May 25, 2020 11:52 am

Thanks,I did it! But I still get some physical issues,when the character walk,her leg can be outside of the dress....Any idea how to fix that? 


Probably the dress is simulated. You'll need to run some kind of cloth sim.

There is a lot nicer way to view animations to:
Set “Tools->Data Viewer->Other->Default preview commands” to:
-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath "F:\FF7_Remake\End2\Content\GameContents"

"F:\FF7_Remake\End2\Content\GameContents" will be your GameContents with all the extracted packages obviously. This will load all the textures in the preview window too.

Load the model and just drag-and-drop the anim you want to apply to it over the preview window from windows explorer, or use the “apply to preview” script in optionalplugins.


Thanks, I did it. Buy……  


I want to import unity. 
Sorry, my English is terrible.
Just export to fbx with animation should be fine,I guess- -
## Post #93
- Username: gamenpc
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 02, 2020 10:35 am
- Post datetime: 2020-05-26T04:31:36+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from linsaberlove ↑Tue May 26, 2020 12:24 pm at Tue May 26, 2020 12:24 pm
>
> 
gamenpc wrote: ↑Tue May 26, 2020 12:14 pm
DioBrando wrote: ↑Tue May 26, 2020 8:56 am


Probably the dress is simulated. You'll need to run some kind of cloth sim.

There is a lot nicer way to view animations to:
Set “Tools->Data Viewer->Other->Default preview commands” to:
-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath "F:\FF7_Remake\End2\Content\GameContents"

"F:\FF7_Remake\End2\Content\GameContents" will be your GameContents with all the extracted packages obviously. This will load all the textures in the preview window too.

Load the model and just drag-and-drop the anim you want to apply to it over the preview window from windows explorer, or use the “apply to preview” script in optionalplugins.


Thanks, I did it. Buy……  


I want to import unity. 
Sorry, my English is terrible.

Just export to fbx with animation should be fine,I guess- -

Importing unity with human animation is still the same orz.
## Post #94
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-05-26T04:43:27+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from gamenpc ↑Tue May 26, 2020 12:31 pm at Tue May 26, 2020 12:31 pm
>
> 
linsaberlove wrote: ↑Tue May 26, 2020 12:24 pm
gamenpc wrote: ↑Tue May 26, 2020 12:14 pm



Thanks, I did it. Buy……  


I want to import unity. 
Sorry, my English is terrible.

Just export to fbx with animation should be fine,I guess- -


Importing unity with human animation is still the same orz.
But importing PSK/PSA animation to 3dmax works fine,maybe a second export?
## Post #95
- Username: DioBrando
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 06, 2010 11:59 am
- Post datetime: 2020-05-26T04:48:22+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from gamenpc ↑Tue May 26, 2020 12:14 pm at Tue May 26, 2020 12:14 pm
>
> 
DioBrando wrote: ↑Tue May 26, 2020 8:56 am
linsaberlove wrote: ↑Mon May 25, 2020 11:52 am

Thanks,I did it! But I still get some physical issues,when the character walk,her leg can be outside of the dress....Any idea how to fix that? 


Probably the dress is simulated. You'll need to run some kind of cloth sim.

There is a lot nicer way to view animations to:
Set “Tools->Data Viewer->Other->Default preview commands” to:
-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath "F:\FF7_Remake\End2\Content\GameContents"

"F:\FF7_Remake\End2\Content\GameContents" will be your GameContents with all the extracted packages obviously. This will load all the textures in the preview window too.

Load the model and just drag-and-drop the anim you want to apply to it over the preview window from windows explorer, or use the “apply to preview” script in optionalplugins.


Thanks, I did it. Buy……  


I want to import unity. 
Sorry, my English is terrible.

You can work directly with the uassets in Noesis, nothing else is required. You can then go to "file->export from preview" to export an fbx model with the animation attached. It will load to Unity. In the Noesis tools menu you can create a Batch Process to export all animation in the game to fbx using those same export commands "-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath"



474846.jpg (237.44 KiB) Viewed 689 times
## Post #96
- Username: gamenpc
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 02, 2020 10:35 am
- Post datetime: 2020-05-26T07:54:34+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from DioBrando ↑Tue May 26, 2020 12:48 pm at Tue May 26, 2020 12:48 pm
>
> 
gamenpc wrote: ↑Tue May 26, 2020 12:14 pm
DioBrando wrote: ↑Tue May 26, 2020 8:56 am


Probably the dress is simulated. You'll need to run some kind of cloth sim.

There is a lot nicer way to view animations to:
Set “Tools->Data Viewer->Other->Default preview commands” to:
-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath "F:\FF7_Remake\End2\Content\GameContents"

"F:\FF7_Remake\End2\Content\GameContents" will be your GameContents with all the extracted packages obviously. This will load all the textures in the preview window too.

Load the model and just drag-and-drop the anim you want to apply to it over the preview window from windows explorer, or use the “apply to preview” script in optionalplugins.


Thanks, I did it. Buy……  


I want to import unity. 
Sorry, my English is terrible.


You can work directly with the uassets in Noesis, nothing else is required. You can then go to "file->export from preview" to export an fbx model with the animation attached. It will load to Unity. In the Noesis tools menu you can create a Batch Process to export all animation in the game to fbx using those same export commands "-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath"
474846.jpg

thanks DioBrando. 
Finally everything is working, the model looks mirrored, how to fix it？
## Post #97
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-05-26T08:36:22+00:00
- Post Title: Re: Final Fantasy 7 remake

Confused about how the animations are organized in these folders,I want to find the animation and scene of aerith meeting cloud for the first time.When I search PC0003(stand for aerith model)in umodel,then animations are located in two places,cut\game and motion\(action enemy player)
in motion folder,I guess enemy and player files should represent repectable animations.In motion\action I find some really long animation,but in cut\game only a few animation works(the others don't show figure at all). - -
    Anyone tell me what these folders stand for and how to find that scene 
   - -  and where are pre-rendered video files located ?  
  Help Plz~
## Post #98
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-05-26T13:10:01+00:00
- Post Title: Re: Final Fantasy 7 remake

In some animations(Most cut\game animations),the character is very far from view which is beyond Noesis's maximal scale range- - 
How to change view to the character????
I can fix this by resetting the coordinates in 3dmax ,but loading animation in 3dmax is quite slow- -
So the question is how to change all coordinates to 0 in Noesis
## Post #99
- Username: gamenpc
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 02, 2020 10:35 am
- Post datetime: 2020-05-27T14:44:08+00:00
- Post Title: Re: Final Fantasy 7 remake

Noesis export from preview(can loaded anime and texture) fbx file.
[https://www.overpic.net/viewer.php?file ... czyuzy.jpg](https://www.overpic.net/viewer.php?file=x2267tp6jlvkesczyuzy.jpg)
[https://www.overpic.net/viewer.php?file ... znqy64.jpg](https://www.overpic.net/viewer.php?file=x77ejj7nzx5efx7znqy64.jpg)
but in blender and unity this fbx file no texture. is "advanced options" need some commands?
## Post #100
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-03T22:31:16+00:00
- Post Title: Re: Final Fantasy 7 remake

For those who want to export umaps and recreate maps 
here is how 

- First having dled all paks open umodel and save packages for blueprints, environments(and the environments folder thats inside the characters folder, you can just extract the whole characters folder which will give you all the character models or just the environment folder this contains all the moving parts for maps like doors and such), levels, effects and lighting(all of these contain models related to scenery, many maps share models between them so you need to extract all)

- place the ff7 tool into UmodelSaved\End\Content\GameContents(this file path would have been created by umodel)

- run ff7 tool(double click the tool) it will extract all blueprints, environments, levels, effects and lighting assets

- You will end up with folders for materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw and textures and blueprint.db and material.db files and some loose .ascii models

- move materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw, textures a blueprint.db and material.db files and some loose .ascii models to the map folder you want to extract for example UmodelSaved\End\Content\GameContents\Level\Game\Field\020-TOWN8\Layout(must be 'layout' not 'layout merged')

- Drag a .umap onto the ff7 tool for example 020-TOWN8_Layout_010-OuterWall.umap(there will be many umaps with extra bits on there name like 020-TOWN8_Layout_010-OuterWall_Animation.umap and 020-TOWN8_Layout_010-OuterWall_animation.umap extract all the ones listed here;
Animation.umap(many doors and moving elements are in here)
collision.umap(only if you want to put this in a game engine where you will want collision as this is a simplified collision mesh for the level) 
envplan.umap(contains the breakable crates that are ingame but good as props)
lighting.umap (these are the models for the lighting as well as the models for lit windows ect)
all of these contain models so extract them for there .ascii the rest you can ignore they dont seem extract anything there are also uexp files ignore these too)

- you will get 3 text log files like this 020-TOWN8_Layout_010-OuterWall.names.txt, 020-TOWN8_Layout_010-OuterWall.export.txt, 020-TOWN8_Layout_010-OuterWall.import.txt and .ascii files(you will get one or several of these .ascii they are generated with what seems to be a 100mb cap as there being generated if it hits this cap it splits off into another .ascii file)

- I then move the generated .ascii files into the textures folder that we got from the ff7 tool

- i also converted all dds textures in this texture folder to png as the .ascii expects png not dds(you can convert these many ways using verios tools umodel and do this too or you can use notepad++ to edit the .ascii and replace all .png references with .dds)

- Lastly use the blender addon that was linked with the game files to import the ascii, they will import sideways as there using y axis as up where as blender is z axis up by default

All maps import super huge blender has a max view clipping so you wont see the meshes at first
In blender press n to bring up the right side panel click on the view tab
at the top you will have
focal length
clip start
end

change end to something like 1000000 its 1000 by default
and change clip start to 10(this will stop meshes doing a weird zfighting thing)
blender has a minimum and maximum mesh clipping view distance built in to help with performance but you can change that with these values 
you can also use number pad . it will jump the camera to a selected object(when you importa mesh everything imported is selected by default)

- Last note the ff7 tool currently dose not read anything from the effects, character and lighting folders, so the tool will not use there models when generating ascii from umap extracting this means there will still be missing things in the map for example the fountain in sector 8 its model in in effects so it wont show up when you imports the umaps ascii. For now we have to add these manually
## Post #101
- Username: grimino
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 30, 2016 8:40 pm
- Post datetime: 2020-06-04T20:08:13+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from speaker60 ↑Thu Jun 04, 2020 6:31 am at Thu Jun 04, 2020 6:31 am
>
> 
For those who want to export umaps and recreate maps 
here is how 

- First having dled all paks open umodel and save packages for blueprints, environments, levels, effects and lighting(all of these contain models related to scenery, many maps share models between them so you need to extract all)

- place the ff7 tool into UmodelSaved\End\Content\GameContents(this file path would have been created by umodel)

- run ff7 tool(double click the tool) it will extract all blueprints, environments, levels, effects and lighting assets

- You will end up with folders for materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw and textures and blueprint.db and material.db files and some loose .ascii models

- move materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw, textures a blueprint.db and material.db files and some loose .ascii models to the map folder you want to extract for example UmodelSaved\End\Content\GameContents\Level\Game\Field\020-TOWN8\Layout(must be 'layout' not 'layout merged')

- Drag a .umap onto the ff7 tool for example 020-TOWN8_Layout_010-OuterWall.umap(there will be many umaps with extra bits on there name like 020-TOWN8_Layout_010-OuterWall_Animation.umap and 020-TOWN8_Layout_010-OuterWall_Collision.umap igonore these there are also uexp files ignore these too)

- you will get 3 text log files like this 020-TOWN8_Layout_010-OuterWall.names.txt, 020-TOWN8_Layout_010-OuterWall.export.txt, 020-TOWN8_Layout_010-OuterWall.import.txt and .ascii files(you will get one or several of these .ascii they are generated with what seems to be a 100mb cap as there being generated if it hits this cap it splits off into another .ascii file)

- I then move the generated .ascii files into the textures folder that we got from the ff7 tool

- i also converted all dds textures in this texture folder to png as the .ascii expects png not dds(you can convert these many ways using verios tools umodel and do this too or you can use notepad++ to edit the .ascii and replace all .png references with .dds)

- Lastly use the blender addon that was linked with the game files to import the ascii, they will import sideways as there using y axis as up where as blender is z axis up by default

thank's for detailed guide, i follow that but when i try to import map into Blender i cannot see anything, Material has correct texture and file imported is 020-TOWN8_Layout_010-OuterWall_map0.ascii wich has 85 MB, there is something that i missed?
i use last version of XPS Tools (2.0.2)
[https://www.overpic.net/viewer.php?file ... 8vbxxc.png](https://www.overpic.net/viewer.php?file=xr3d4p7jiribrz8vbxxc.png)
## Post #102
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-04T20:15:17+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from grimino ↑Fri Jun 05, 2020 4:08 am at Fri Jun 05, 2020 4:08 am
>
> 
thank's for detailed guide, i follow that but when i try to import map into Blender i cannot see anything, Material has correct texture and file imported is 020-TOWN8_Layout_010-OuterWall_map0.ascii wich has 85 MB, there is something that i missed?
i use last version of XPS Tools (2.0.2)
https://www.overpic.net/viewer.php?file ... 8vbxxc.png

All maps are super huge in blender press n to bring up the right side panel click on the view tab
at the top you will have
focal length
clip start
end

change end to something like 1000000 its 1000 by default
blender has a minimum and maximum mesh clipping thing built in to help with performance but you can change that here 
you can also use number pad . it will jump the camera to a selected object(when you import everything is selected by default)

Ill add this to my original tutorial
## Post #103
- Username: gravureboxing
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 12, 2013 12:17 am
- Post datetime: 2020-06-05T00:57:47+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from speaker60 ↑Thu Jun 04, 2020 6:31 am at Thu Jun 04, 2020 6:31 am
>
> 
For those who want to export umaps and recreate maps
here is how

- First having dled all paks open umodel and save packages for blueprints, environments(and the environments folder thats inside the characters folder, you can just extract the whole characters folder which will give you all the character models or just the environment folder this contains all the moving parts for maps like doors and such), levels, effects and lighting(all of these contain models related to scenery, many maps share models between them so you need to extract all)

- place the ff7 tool into UmodelSaved\End\Content\GameContents(this file path would have been created by umodel)

- run ff7 tool(double click the tool) it will extract all blueprints, environments, levels, effects and lighting assets

- You will end up with folders for materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw and textures and blueprint.db and material.db files and some loose .ascii models

- move materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw, textures a blueprint.db and material.db files and some loose .ascii models to the map folder you want to extract for example UmodelSaved\End\Content\GameContents\Level\Game\Field\020-TOWN8\Layout(must be 'layout' not 'layout merged')

- Drag a .umap onto the ff7 tool for example 020-TOWN8_Layout_010-OuterWall.umap(there will be many umaps with extra bits on there name like 020-TOWN8_Layout_010-OuterWall_Animation.umap and 020-TOWN8_Layout_010-OuterWall_Collision.umap igonore these there are also uexp files ignore these too)

- you will get 3 text log files like this 020-TOWN8_Layout_010-OuterWall.names.txt, 020-TOWN8_Layout_010-OuterWall.export.txt, 020-TOWN8_Layout_010-OuterWall.import.txt and .ascii files(you will get one or several of these .ascii they are generated with what seems to be a 100mb cap as there being generated if it hits this cap it splits off into another .ascii file)

- I then move the generated .ascii files into the textures folder that we got from the ff7 tool

- i also converted all dds textures in this texture folder to png as the .ascii expects png not dds(you can convert these many ways using verios tools umodel and do this too or you can use notepad++ to edit the .ascii and replace all .png references with .dds)

- Lastly use the blender addon that was linked with the game files to import the ascii, they will import sideways as there using y axis as up where as blender is z axis up by default

All maps import super huge blender has a max view clipping so you wont see the meshes at first
In blender press n to bring up the right side panel click on the view tab
at the top you will have
focal length
clip start
end

change end to something like 1000000 its 1000 by default
and change clip start to 10(this will stop meshes doing a weird zfighting thing)
blender has a minimum and maximum mesh clipping view distance built in to help with performance but you can change that with these values
you can also use number pad . it will jump the camera to a selected object(when you importa mesh everything imported is selected by default)

Thanks for detailed guide, I was able to extract parts of map. However, I'm finding that they are missing certain features;
For an example, Corneo Colosseum as below is missing gates and floor trap that houses Hell House.

I think I know why but would love to get an answer.
When I extracted with ff7r tool, I wasn't able to get any skeletalmesh (I didn't get any of these files)
Would it be possible cause? If so, I'm not so sure why I didn't get any of skeletalmesh files - I did follow your guide precisely.   



If you could help me with, it'd be very much appreciated. Thanks in advance!
## Post #104
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-05T02:16:37+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from gravureboxing ↑Fri Jun 05, 2020 8:57 am at Fri Jun 05, 2020 8:57 am
>
> 

Thanks for detailed guide, I was able to extract parts of map. However, I'm finding that they are missing certain features;
For an example, Corneo Colosseum as below is missing gates and floor trap that houses Hell House.

I think I know why but would love to get an answer.
When I extracted with ff7r tool, I wasn't able to get any skeletalmesh (I didn't get any of these files)
Would it be possible cause? If so, I'm not so sure why I didn't get any of skeletalmesh files - I did follow your guide precisely.   

If you could help me with, it'd be very much appreciated. Thanks in advance!

I think i got skeletalmesh and skeletalmeshraw because i extracted the environments folder thats inside the characters folder
I guess as it says environments i figured id need them and forgot about that 
however i dont know if that is what will give you all the moving parts
ue4 treats statics and moving elements differently so it could be that the umap extraction is unable to understand the moving parts in this case 
Iv not experimented too much yet, once i figured out how to extract maps i thought id share so it makes it easier for others to do it if they want
ill add the character/environments to my guide

Edit - so in character/environments it contains alot of doors and other moving parts so this should give you the missing parts unless the umap extraction genuinely cant detect these(still not sure till we test)

Also could you edit your posts with my guide as a quote as it dosnt get my edits and people might read that without the new information, just crop it out would be fine, just so people see the proper edited guide its also abit too long to have repeated several times
## Post #105
- Username: gravureboxing
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 12, 2013 12:17 am
- Post datetime: 2020-06-05T02:38:51+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from speaker60 ↑Fri Jun 05, 2020 10:16 am at Fri Jun 05, 2020 10:16 am
>
> 
I think i got skeletalmesh and skeletalmeshraw because i extracted the environments folder thats inside the characters folder
I guess as it says environments i figured id need them and forgot about that 
however i dont know if that is what will give you all the moving parts
ue4 treats statics and moving elements differently so it could be that the umap extraction is unable to understand the moving parts in this case 
Iv not experimented too much yet, once i figured out how to extract maps i thought id share so it makes it easier for others to do it if they want
ill add the character/environments to my guide

Edit - so in character/environments it contains alot of doors and other moving parts so this should give you the missing parts unless the umap extraction genuinely cant detect these(still not sure till we test)

Also could you edit your posts with my guide as a quote as it dosnt get my edits and people might read that without the new information, just crop it out would be fine, just so people see the proper edited guide its also abit too long to have repeated several times

You've got a point there. I'll try exporting characters and then try again some time later. 
I did edit quotation of your guide, so should be good. Anyhow, thank you
## Post #106
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-05T02:46:46+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from gravureboxing ↑Fri Jun 05, 2020 10:38 am at Fri Jun 05, 2020 10:38 am
>
> 
You've got a point there. I'll try exporting characters and then try again some time later. 
I did edit quotation of your guide, so should be good. Anyhow, thank you

Thanks and hopefully it will work fine with the character parts 
so to explain in this game all moving parts must be using a skeletal rig so just like a character using a skeleton rig, doors and such here will have there own skeleton and play animations. doors can be done other ways without skeletal rigs but its just how the devs decided to do this
thats why these were put into the characters folder as this is where they have put everything thats rigged thus we get skeletalmesh folders :p
## Post #107
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-05T12:29:58+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Takato Matsukj ↑Sat May 16, 2020 7:36 am at Sat May 16, 2020 7:36 am
>
> 

Hi Takato whats your experience with missing elements for maps like the fountain in sector 8 or the midgar model(replica) thats in the shinra building

Various things dont get imported with the umap extraction these are obviously objects that are handled differently in such away that the ff7 tool cant account for or there stored in a location i haven't extracted yet. 

As you have done many extractions have you noticed a pattern to this? 
Where are these kind of objects stored, are they just mixed in with all the other models in staticmesh folder or are these in a specific location 

Just want to know what your experience is with these missing objects and how i can deal with them and find them easily
I searched for the word fountain but it didnt actually bring up the specific model for the fountain from what i have extracted with the ff7 tool
so its eather got a weird name or iv yet to extract it form the uassets. 

As well as figuring it out my self im trying to document and give a full guide that im editing as i figure bits out(on last page)
any help figuring this last bit out would be great from anyone
## Post #108
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-06-05T14:54:38+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from speaker60 ↑Fri Jun 05, 2020 8:29 pm at Fri Jun 05, 2020 8:29 pm
>
> 
Takato Matsukj wrote: ↑Sat May 16, 2020 7:36 am


Hi Takato whats your experience with missing elements for maps like the fountain in sector 8 or the midgar model(replica) thats in the shinra building

Various things dont get imported with the umap extraction these are obviously objects that are handled differently in such away that the ff7 tool cant account for or there stored in a location i haven't extracted yet. 

As you have done many extractions have you noticed a pattern to this? 
Where are these kind of objects stored, are they just mixed in with all the other models in staticmesh folder or are these in a specific location 

Just want to know what your experience is with these missing objects and how i can deal with them and find them easily
I searched for the word fountain but it didnt actually bring up the specific model for the fountain from what i have extracted with the ff7 tool
so its eather got a weird name or iv yet to extract it form the uassets. 

As well as figuring it out my self im trying to document and give a full guide that im editing as i figure bits out(on last page)
any help figuring this last bit out would be great from anyone

These specific models are considered to be 'effects'.
There are many blueprints and effects that contain meshes. Sometimes this is because those particular meshes have a lot of effects on them, and so they are considered to come under 'effects' by the development team.

I've found the fountain myself it was inside the effects folder. The best thing to do honestly is run the tool on most of the folders, as things are scattered around. For example the fountain, breaks the instant you get near to it, so its a breakable effect, its just broken in a cutscene as opposed to interactive with a character.

You're right that the tool doesn't read/look for effect data within the levels, if it did, it'd be really messy, considering there is smoke, dust, particles just about everywhere, it'd make levels completely unreadable in a 3D editor.
## Post #109
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-05T17:43:44+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Fri Jun 05, 2020 10:54 pm at Fri Jun 05, 2020 10:54 pm
>
> 

Ah thats where the fountain is cool dont know why i didnt think to look there
Im a ue4 dev my self so i fully understand all the differences of the files
and i assumed the ff7 tool wouldnt detect all these other effects and stuff for a reason
Ill note down people should look in effects and character environments for missing stuff
It would seem the ff7 tool dose handle blueprints thats what the blueprint.db is for it makes a database of all the models in bps and there location/rotation ect so atleast thats something not to worry about 

Would be nice it the tool did make an effects.db and we can choose to remove or leave and deal with the mess
What i would do if it could import effects is generate the .ASCII with the effects.db present import into blender and grab what i want that would be missing like the fountain and export them as fbx then re- generate the ASCII without the effects.db and re-import that into blender then just import the fbx for the missing stuff. That way you can have can still have all the correct locations/rotations for these objects

> Reply from daemon1 ↑Thu Apr 30, 2020 5:29 pm at Thu Apr 30, 2020 5:29 pm
>
> 
Would that be possible daemon1?
An effects.db so the tool can generate ascii for umaps with all the models form the effects folder
same for character(as theres environments stuff in there). 
People then can choose to use the effects.db and character.db for umap ascii generation and do what i described or remove them before they generate the ascii
## Post #110
- Username: gravureboxing
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 12, 2013 12:17 am
- Post datetime: 2020-06-05T21:05:52+00:00
- Post Title: Re: Final Fantasy 7 remake

Also, when exporting umap files, there are certain meshes connected with other file such as "animations"
I marked it for an example here
## Post #111
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-05T22:08:08+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from gravureboxing ↑Sat Jun 06, 2020 5:05 am at Sat Jun 06, 2020 5:05 am
>
> 
Also, when exporting umap files, there are certain meshes connected with other file such as "animations"
I marked it for an example here

Thats interesting, i swear i tried the ff7 tool on them but thanks for the info will add it to the guide

Just going though checking and you can do it to animation collision(but unneeded unless your sticking into a game engine you can use this for simplified collision mesh) envplan(which seems to be all the breakable creates) and lighting

Dont know why i thought they didnt have anything
## Post #112
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-06T00:59:58+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Fri Jun 05, 2020 10:54 pm at Fri Jun 05, 2020 10:54 pm
>
> 

So the fountain and pretty much all missing stuff benches bikes litter and other small physics based props are in
animation.umap
envplan.umap
lighting.umap(this is where all the lamps and all the missing lit windows for buildings)

these all work with the ff7 tool and will produce ascii files and will import into blender just fine

for example the fountain got placed by 020-TOWN8_Layout_070-FountainAve_Animation.umap and its ascii file it created

So solved all missing things are found that im aware of so far not done every map yet just thought id let you know and my detailed guide is updated on page 7
## Post #113
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-06-06T12:11:06+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from speaker60 ↑Sat Jun 06, 2020 8:59 am at Sat Jun 06, 2020 8:59 am
>
> 
lionheartuk wrote: ↑Fri Jun 05, 2020 10:54 pm


So the fountain and pretty much all missing stuff benches bikes litter and other small physics based props are in
animation.umap
envplan.umap
lighting.umap(this is where all the laps and all the missing lit windows for buildings)

these all work with the ff7 tool and will produce ascii files and will import into blender just fine

for example the fountain got placed by 020-TOWN8_Layout_070-FountainAve_Animation.umap and its ascii file it created

So solved all missing things are found that im aware of so far not done every map yet just thought id let you know and my detailed guide is updated on page 7

Yep this guy got it right. 

Those three includes additional meshes.
## Post #114
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-06-06T12:13:06+00:00
- Post Title: Re: Final Fantasy 7 remake

pakchunk3_s11 contains majority of the rigged props. So be sure to look in there.. If you want the rigs for doors, switches, etc... Anything that the player can interact with or something that moves will most likley be in that folder.
## Post #115
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-06-06T12:17:53+00:00
- Post Title: Re: Final Fantasy 7 remake

Like for example with the shinra lobby.
It looked like this originally. No lamps, no props like the front desk and statues and fixtures.  

After extracting the animation.umap and Lighting.umap(which gave me all the lamps, lights omfg thx...)| It included more props and I was able to work on it more in Unity


The escalators on the left side, it did not include them. I had to dig'em out myself out the mentioned pak folder above. Since it's a skeletalmesh not static.
## Post #116
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-06T12:31:59+00:00
- Post Title: Re: Final Fantasy 7 remake

So to recap this is the full guide with new edits from my previous one for those who want to export umaps 
and recreate maps in blender or any game engine
here a step by step how

- First having dled all paks from deviantart open umodel and save packages for blueprints, environments(and the environments folder thats inside the characters folder, you can just extract the whole characters folder which will give you all the character models or just the environment folder this contains all the moving parts for maps like doors and such), levels, effects and lighting(all of these contain models related to scenery, many maps share models between maps to maps so you need to extract all)

- Place the ff7 tool into UmodelSaved\End\Content\GameContents(this file path would have been created by umodel)

- Run ff7 tool(double click the tool) it will extract all blueprints, environments, levels, effects and lighting assets

- You will end up with folders for materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw and textures and blueprint.db and material.db files and some loose .ascii models

- Move materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw, textures a blueprint.db and material.db files and the loose .ascii models to the map folder you want to extract for example UmodelSaved\End\Content\GameContents\Level\Game\Field\020-TOWN8\Layout(must be 'layout' not 'layout merged')

- Drag a .umap onto the ff7 tool for example 020-TOWN8_Layout_010-OuterWall.umap(there will be many umaps with extra bits on there name like 020-TOWN8_Layout_010-OuterWall_Animation.umap and 020-TOWN8_Layout_010-OuterWall_collision.umap extract all the ones listed here;
Animation.umap(many doors and moving elements and many props and physics objects like blenches and other clutter are in here)
collision.umap(only if you want to put this in a game engine where you will want collision as this is a simplified collision mesh for the level)
envplan.umap(contains the breakable crates and good as props, these sometimes extract nothing probably because there was no crates in the level)
lighting.umap (these are the models for the lighting like lamp posts, wall hung lamps and lit windows but not actual light sources just models)
all of these contain models so extract them for there .ascii the rest you can ignore they dont seem extract anything there are also uexp files ignore these too)

- You will get 3 text log files like this 020-TOWN8_Layout_010-OuterWall.names.txt, 020-TOWN8_Layout_010-OuterWall.export.txt, 020-TOWN8_Layout_010-OuterWall.import.txt and .ascii files(you will get one or several of these .ascii they are generated with what seems to be a 100mb cap as there being generated if it hits this cap it splits off into another .ascii file each of these .ascii contain a section of the level)

- I then move all the generated .ascii files into the textures folder that we got from the ff7 tool

- I also converted all dds textures in this texture folder to png as the .ascii expects png not dds(you can convert textures in many ways using verious tools like photoshop or even umodel can do this too or you can use notepad++ to edit the .ascii files themselves  and replace all .png references with .dds this will make the ascii look for dds instead)

- Lastly use the blender addon that was linked with the game files on da to import the ascii, they will import sideways as there using y axis as up where as blender is z axis up by default

All maps import super huge blender has max view clipping set low by default so you wont see the meshes at first
In blender press n to bring up the right side panel click on the view tab
at the top you will have
focal length
clip start
end

Change end to something like 1000000 its 1000 by default
and change clip start to 10(this will stop meshes doing a weird zfighting)
blender has a minimum and maximum mesh clipping view distance built in to help with performance but you can change that with these values
you can also use number pad . it will jump the camera to a selected object(when you import a mesh everything imported is selected by default)

Thats it you should now be able to import any map in full with all objects, sometimes there is still the odd material/texture missing 
This will be its just using a flat color in the game and not using a texture or some other reason, but iv only found 1 missing mat for a light everything else is there for me having extracted everything first

There may also still be some missing objects due to them being a skeletal mesh, you will have to look and find them manually

Try not to quote this post its too long to have repeated several times and also if i make any edits to this post it wont show with any posts that quoted this post
## Post #117
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-06T12:36:38+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Takato Matsukj ↑Sat Jun 06, 2020 8:17 pm at Sat Jun 06, 2020 8:17 pm
>
> 

Looking good ill be putting them into ue4 at some point but iv set them up in blender evee  with all there emissives
It looks soo good with all the props and lights 

So you still find the odd thing missing, okay i left that as the last note in the guide i just reposed(thought i should repost it as theres some incorrect quoted ones that came after it)
## Post #118
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-06-06T12:40:29+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from speaker60 ↑Sat Jun 06, 2020 8:36 pm at Sat Jun 06, 2020 8:36 pm
>
> 
Takato Matsukj wrote: ↑Sat Jun 06, 2020 8:17 pm


Looking good ill be putting them into ue4 at some point but iv set them up in blender evee  with all there emissives
It looks soo good with all the props and lights 

So you still find the odd thing missing, okay i left that as the last note in the guide i just reposed(thought i should repost it as theres some incorrect quoted ones that came after it)

Thanks man. I'm more of a unity guy. These maps are so amazing to see in VR.

Ngl, these maps are easy to extract if you put your mind to it. It's just time consuming is all.... and if you have the space on your hard drive too.
## Post #119
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-06T13:08:03+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Takato Matsukj ↑Sat Jun 06, 2020 8:40 pm at Sat Jun 06, 2020 8:40 pm
>
> 

Well i did have space on my pc till this game came along lol
Im a ue4 dev i work on this title
[https://www.youtube.com/watch?v=LJlN5sgpLvc](https://www.youtube.com/watch?v=LJlN5sgpLvc)
This is a city model iv been making for a long wile still alot to do with it

Having just extracted loveless ave i never noticed now not quite accurate it is

I made some changes to give it a more accurate look
this street is meant to be a t junction ill probably change it to this and reedit the theater building 
Might add the marble tiles back to loveless plaza too along with the wall of billboards thats missing
## Post #120
- Username: R5GAMER
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Jun 08, 2015 5:41 am
- Post datetime: 2020-06-06T18:11:17+00:00
- Post Title: Re: Final Fantasy 7 remake

Can anyone give me the resources in mp?

Thank you.
## Post #121
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-06T19:28:19+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from R5GAMER ↑Sun Jun 07, 2020 2:11 am at Sun Jun 07, 2020 2:11 am
>
> 
Can anyone give me the resources in mp?

Thank you.

If you mean the game files read my guide gives you an idea where to get them the link is in this thread too
## Post #122
- Username: grimino
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 30, 2016 8:40 pm
- Post datetime: 2020-06-08T08:36:17+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from speaker60 ↑Sat Jun 06, 2020 9:08 pm at Sat Jun 06, 2020 9:08 pm
>
> 
Takato Matsukj wrote: ↑Sat Jun 06, 2020 8:40 pm

Sorry guys but i cannot see any lights or lamps, there is something that i missed? i think i have extracted everything properly.

[https://imgur.com/a/FDNPVAr](https://imgur.com/a/FDNPVAr)
## Post #123
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-09T00:06:45+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from grimino ↑Mon Jun 08, 2020 4:36 pm at Mon Jun 08, 2020 4:36 pm
>
> 
speaker60 wrote: ↑Sat Jun 06, 2020 9:08 pm
Takato Matsukj wrote: ↑Sat Jun 06, 2020 8:40 pm



Sorry guys but i cannot see any lights or lamps, there is something that i missed? i think i have extracted everything properly.

https://imgur.com/a/FDNPVAr

It will only import the models for the lights not the actual lights as in emitting light you have to set that up your self along with making various materials emissive
## Post #124
- Username: gravureboxing
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 12, 2013 12:17 am
- Post datetime: 2020-06-09T14:38:00+00:00
- Post Title: Re: Final Fantasy 7 remake

Out of curiosity, I wasn't able to extract audio files with UModel, or am I missing something? I just counted my pak files and it's 115gb... I'm pretty sure I have everything.. h mm
## Post #125
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-06-09T14:47:25+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from gravureboxing ↑Tue Jun 09, 2020 10:38 pm at Tue Jun 09, 2020 10:38 pm
>
> ...or am I missing something?
[viewtopic.php?p=162831#p162831](https://forum.xentax.com/viewtopic.php?p=162831#p162831)
## Post #126
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-06-09T14:53:58+00:00
- Post Title: Re: Final Fantasy 7 remake

[viewtopic.php?f=17&t=22154&p=163149#p163149](https://forum.xentax.com/viewtopic.php?f=17&t=22154&p=163149#p163149)
## Post #127
- Username: gravureboxing
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 12, 2013 12:17 am
- Post datetime: 2020-06-09T15:25:10+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from mono24 ↑Tue Jun 09, 2020 10:47 pm at Tue Jun 09, 2020 10:47 pm
>
> 
gravureboxing wrote: ↑Tue Jun 09, 2020 10:38 pm...or am I missing something?
viewtopic.php?p=162831#p162831

This method worked. Thank you!
## Post #128
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-07-03T03:12:26+00:00
- Post Title: Re: Final Fantasy 7 remake

There are many kinds of texture maps when I export a character,I want to use blender to render but not sure what they stand for.
I guess C base color ,A alpha ,N tangent normal, O roughness,M shallow color.... Am I correct?
So what does B  NB stand for and how can I use them in blender? Thx
## Post #129
- Username: Nihyaku
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 08, 2017 7:06 pm
- Post datetime: 2020-07-04T20:38:39+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from linsaberlove ↑Fri Jul 03, 2020 11:12 am at Fri Jul 03, 2020 11:12 am
>
> 
There are many kinds of texture maps when I export a character,I want to use blender to render but not sure what they stand for.
I guess C base color ,A alpha ,N tangent normal, O roughness,M shallow color.... Am I correct?
So what does B  NB stand for and how can I use them in blender? Thx

Hi! You're right for C, A and N texture maps! O should be ambient occlusion; as for M map, it contains informations about metallic and roughness maps: the red channel is the former and the green channel is the latter!
I've heard that some people use B map for subsurface scattering; personally, I use it as a mask texture to define which parts shouldn't be affected by a detail map (I don't use Blender, but another rendering software!)
As for NB texture map, I can't help you, because I don't know either!
I hope this helps! (◍•ᴗ•◍)
## Post #130
- Username: evergrazes
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 11, 2020 1:39 am
- Post datetime: 2020-07-10T19:33:48+00:00
- Post Title: Re: Final Fantasy 7 remake

someone could extract from the game the scene the promise of cloud and young girl tifa for a diorama in 3d printer,thankn youu
## Post #131
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-07-11T03:07:18+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Nihyaku ↑Sun Jul 05, 2020 4:38 am at Sun Jul 05, 2020 4:38 am
>
> 
linsaberlove wrote: ↑Fri Jul 03, 2020 11:12 am
There are many kinds of texture maps when I export a character,I want to use blender to render but not sure what they stand for.
I guess C base color ,A alpha ,N tangent normal, O roughness,M shallow color.... Am I correct?
So what does B  NB stand for and how can I use them in blender? Thx 


Hi! You're right for C, A and N texture maps! O should be ambient occlusion; as for M map, it contains informations about metallic and roughness maps: the red channel is the former and the green channel is the latter!
I've heard that some people use B map for subsurface scattering; personally, I use it as a mask texture to define which parts shouldn't be affected by a detail map (I don't use Blender, but another rendering software!)
As for NB texture map, I can't help you, because I don't know either!
I hope this helps! (◍•ᴗ•◍)

BIG THANKS!   There is alpha issue in hair and normal tangent also has weird effect, any idea  ?
[Image3 1.png](https://xentaxbackup.github.io/file/18437_Image3 1.png)
## Post #132
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-07-11T11:29:43+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Nihyaku ↑Sun Jul 05, 2020 4:38 am at Sun Jul 05, 2020 4:38 am
>
> 
linsaberlove wrote: ↑Fri Jul 03, 2020 11:12 am
There are many kinds of texture maps when I export a character,I want to use blender to render but not sure what they stand for.
I guess C base color ,A alpha ,N tangent normal, O roughness,M shallow color.... Am I correct?
So what does B  NB stand for and how can I use them in blender? Thx 


Hi! You're right for C, A and N texture maps! O should be ambient occlusion; as for M map, it contains informations about metallic and roughness maps: the red channel is the former and the green channel is the latter!
I've heard that some people use B map for subsurface scattering; personally, I use it as a mask texture to define which parts shouldn't be affected by a detail map (I don't use Blender, but another rendering software!)
As for NB texture map, I can't help you, because I don't know either!
I hope this helps! (◍•ᴗ•◍)

NB is Normal Bent , its a Bent Normal Map, its a special type of normal map, if you're using Blender theres probably a plug for it, in other 3D software I don't know, I've only ever used it inside of unreal, and I'd imagine unity has it too.
## Post #133
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-07-11T12:36:47+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Sat Jul 11, 2020 7:29 pm at Sat Jul 11, 2020 7:29 pm
>
> 
Nihyaku wrote: ↑Sun Jul 05, 2020 4:38 am
linsaberlove wrote: ↑Fri Jul 03, 2020 11:12 am
There are many kinds of texture maps when I export a character,I want to use blender to render but not sure what they stand for.
I guess C base color ,A alpha ,N tangent normal, O roughness,M shallow color.... Am I correct?
So what does B  NB stand for and how can I use them in blender? Thx 


Hi! You're right for C, A and N texture maps! O should be ambient occlusion; as for M map, it contains informations about metallic and roughness maps: the red channel is the former and the green channel is the latter!
I've heard that some people use B map for subsurface scattering; personally, I use it as a mask texture to define which parts shouldn't be affected by a detail map (I don't use Blender, but another rendering software!)
As for NB texture map, I can't help you, because I don't know either!
I hope this helps! (◍•ᴗ•◍)


NB is Normal Bent , its a Bent Normal Map, its a special type of normal map, if you're using Blender theres probably a plug for it, in other 3D software I don't know, I've only ever used it inside of unreal, and I'd imagine unity has it too.
  I'll do some google , do you know the alpha issue and normal map effect I just mentioned above ?
## Post #134
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2020-07-12T06:44:51+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Sat Jul 11, 2020 7:29 pm at Sat Jul 11, 2020 7:29 pm
>
> 
Nihyaku wrote: ↑Sun Jul 05, 2020 4:38 am
linsaberlove wrote: ↑Fri Jul 03, 2020 11:12 am
There are many kinds of texture maps when I export a character,I want to use blender to render but not sure what they stand for.
I guess C base color ,A alpha ,N tangent normal, O roughness,M shallow color.... Am I correct?
So what does B  NB stand for and how can I use them in blender? Thx 


Hi! You're right for C, A and N texture maps! O should be ambient occlusion; as for M map, it contains informations about metallic and roughness maps: the red channel is the former and the green channel is the latter!
I've heard that some people use B map for subsurface scattering; personally, I use it as a mask texture to define which parts shouldn't be affected by a detail map (I don't use Blender, but another rendering software!)
As for NB texture map, I can't help you, because I don't know either!
I hope this helps! (◍•ᴗ•◍)


NB is Normal Bent , its a Bent Normal Map, its a special type of normal map, if you're using Blender theres probably a plug for it, in other 3D software I don't know, I've only ever used it inside of unreal, and I'd imagine unity has it too.

Basically a flowmap or tangent shift map for anisotropic reflections.
## Post #135
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-07-12T11:15:02+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Darko ↑Sun Jul 12, 2020 2:44 pm at Sun Jul 12, 2020 2:44 pm
>
> 
lionheartuk wrote: ↑Sat Jul 11, 2020 7:29 pm
Nihyaku wrote: ↑Sun Jul 05, 2020 4:38 am


Hi! You're right for C, A and N texture maps! O should be ambient occlusion; as for M map, it contains informations about metallic and roughness maps: the red channel is the former and the green channel is the latter!
I've heard that some people use B map for subsurface scattering; personally, I use it as a mask texture to define which parts shouldn't be affected by a detail map (I don't use Blender, but another rendering software!)
As for NB texture map, I can't help you, because I don't know either!
I hope this helps! (◍•ᴗ•◍)


NB is Normal Bent , its a Bent Normal Map, its a special type of normal map, if you're using Blender theres probably a plug for it, in other 3D software I don't know, I've only ever used it inside of unreal, and I'd imagine unity has it too.


Basically a flowmap or tangent shift map for anisotropic reflections.

Some people just link the map to the tangent node in principle BSDF in blender, but I can't see the difference in render results..Not sure if it is the right way.
## Post #136
- Username: Nihyaku
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 08, 2017 7:06 pm
- Post datetime: 2020-07-14T17:33:03+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from linsaberlove ↑Fri Jul 03, 2020 11:12 am at Fri Jul 03, 2020 11:12 am
>
> 

Anytime!! (●˙꒳˙●)
Unfortunately, I don't know how to fix the alpha issue... I copied the alpha texture (A) into the alpha channel of the diffuse (C), but I don't have this kind of problem in my rendering software (I use Marmoset Toolbag 3). Same for the normal map. I hope that someone else can help you!

> Reply from lionheartuk ↑Sat Jul 11, 2020 7:29 pm at Sat Jul 11, 2020 7:29 pm
>
> 

Thank you kindly for letting me know about this! (◍•ᴗ•◍)

> Reply from Darko ↑Sun Jul 12, 2020 2:44 pm at Sun Jul 12, 2020 2:44 pm
>
> 

That makes sense! I use Marmoset Toolbag 3 and there's a feature that allows me to control the anisotropic reflections! I'll try it immediately! Thank you very much! (.◜ω◝.)
## Post #137
- Username: bethanyannie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 11, 2020 9:45 pm
- Post datetime: 2020-07-20T16:14:35+00:00
- Post Title: Re: Final Fantasy 7 remake

I am BEGGING FOR HELP!!! I have downloaded all the necessary files and am opening ASCII in Blender. I want to extract environments (Jessie's house, Aerith's house, etc) but I can only import one item at a time in Blender, the tool will not extract anything from UMAPS, no textures are assigned (to character too) even though everything is in the same folder - so, to sum it up, say I extract Jessie's house, I can only import one massive un-textured item randomly into Blender, please help me! I've followed every guide on here!
## Post #138
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-07-20T16:26:46+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from bethanyannie ↑Tue Jul 21, 2020 12:14 am at Tue Jul 21, 2020 12:14 am
>
> 
the tool will not extract anything from UMAPS
it means you did something wrong
you have to explain what you did, so someone can help you
## Post #139
- Username: bethanyannie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 11, 2020 9:45 pm
- Post datetime: 2020-07-20T16:55:05+00:00
- Post Title: Re: Final Fantasy 7 remake

Using Umodel I saved 0thEventShinra (Presidents Office) and exported the textures as PNG (tried TGA too), I ran the tool in the saved folder and put all converted ASCII in the texture folder, I opened the ASCII in Blender (Noesis not working) but could only import one mesh (a wall), it was un-textured and I realised it had no map assigned.

Did the same thing with Town7 but saved the UMAP from Game - Field... and ran the tool to convert it but the tool did nothing. 
Same problem, no assigned textures, can only import one mesh at a time and UMAP not working.

Can anyone help please? I'm having the same issue with characters.
## Post #140
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-07-20T19:03:15+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from bethanyannie ↑Tue Jul 21, 2020 12:55 am at Tue Jul 21, 2020 12:55 am
>
> 
Using Umodel I saved 0thEventShinra (Presidents Office) and exported the textures as PNG (tried TGA too), I ran the tool in the saved folder and put all converted ASCII in the texture folder, I opened the ASCII in Blender (Noesis not working) but could only import one mesh (a wall), it was un-textured and I realised it had no map assigned.

Did the same thing with Town7 but saved the UMAP from Game - Field... and ran the tool to convert it but the tool did nothing. 
Same problem, no assigned textures, can only import one mesh at a time and UMAP not working.

Can anyone help please? I'm having the same issue with characters.
it doesnt work like that.
you have to read guides or my explanation in the 1st post
## Post #141
- Username: bethanyannie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 11, 2020 9:45 pm
- Post datetime: 2020-07-20T19:54:15+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from daemon1 ↑Tue Jul 21, 2020 3:03 am at Tue Jul 21, 2020 3:03 am
>
> 
bethanyannie wrote: ↑Tue Jul 21, 2020 12:55 am
Using Umodel I saved 0thEventShinra (Presidents Office) and exported the textures as PNG (tried TGA too), I ran the tool in the saved folder and put all converted ASCII in the texture folder, I opened the ASCII in Blender (Noesis not working) but could only import one mesh (a wall), it was un-textured and I realised it had no map assigned.

Did the same thing with Town7 but saved the UMAP from Game - Field... and ran the tool to convert it but the tool did nothing. 
Same problem, no assigned textures, can only import one mesh at a time and UMAP not working.

Can anyone help please? I'm having the same issue with characters.

it doesnt work like that.
you have to read guides or my explanation in the 1st post

I have read the guides, can you tell me what I'm doing wrong? This is what I understood from them
## Post #142
- Username: bethanyannie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 11, 2020 9:45 pm
- Post datetime: 2020-07-21T10:34:34+00:00
- Post Title: Re: Final Fantasy 7 remake

I've read through every guide on here and still can't understand what I'm doing wrong, I have literally dropped every mesh, texture and UMAP onto the tool and still get un-textured models in Blender, can anyone please help me? I've been stuck on this for days. I'm trying to texture scenes (such as Town7) and assign their correct textures, but everything loads blank in the middle of the screen.

1. I saved the wanted models from Umodel
2. I extracted the textures as PNG because that's what Blender looks for
3. I saved the UMAP from Levels
4. I put them all in the same folder and ran the tool, dropping UMAP on the tool
5. I put the static Mesh in the same folder as everything else
6. I open them in Blender using the XPS add-on, can only load one object at a time, all of which is untextured and 'enviroment models' have no assigned location so load as a a jumbo in the middle of the screen.

Can someone please tell me what I'm doing wrong! It's been a week!
## Post #143
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-07-21T13:41:38+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from bethanyannie ↑Tue Jul 21, 2020 6:34 pm at Tue Jul 21, 2020 6:34 pm
>
> Can someone please tell me what I'm doing wrong!
Extracting some files you think you need using Umodel from the PAKs is not going to work for you ever, using this tool.
You MUST unpack all PAKs the game has because some assets are scattered around.

First thing you need to do is load the main folder with the PAKs you have from the game in Umodel.
Then perform a full file/folder structure extraction with everything intact.
At the root folder where you extracted all assets from the PAKs run the tool to convert all assets.
You will get some extra folders at the root as well such as "textures", "staticmesh.raw" & "skeletalmesh.raw" and two files "material.db", "blueprint.db".
Now you can convert all DDS textures in that "textures" folder to PNG.
Once everything is converted, be prepared to wait a VERY long time, this is not something that takes 30sec, depending on your specs it may vary.
Now all you gotta do is make sure that "staticmesh.raw" and "material.db"/"blueprint.db" are in same folder with the UMAP map files your trying to convert.
Or simply move the map files you want to convert at root folder then convert, and you'll get ASCIIs with everything loaded in Blender with correct coordinates and textures.
THEN you'll get what your looking for.
for this entire process make sure you have at least 200GB+ of free space or more.
## Post #144
- Username: Stallone
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Mar 12, 2020 5:24 am
- Post datetime: 2020-07-21T21:30:29+00:00
- Post Title: Re: Final Fantasy 7 remake

Hello guys!

Can someone pull the Bombing Countdown background image and font please? 

I am no expert in those things, unfortunately...
## Post #145
- Username: bethanyannie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 11, 2020 9:45 pm
- Post datetime: 2020-07-27T22:36:15+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from speaker60 ↑Thu Jun 04, 2020 6:31 am at Thu Jun 04, 2020 6:31 am
>
> 
For those who want to export umaps and recreate maps 
here is how 

- First having dled all paks open umodel and save packages for blueprints, environments(and the environments folder thats inside the characters folder, you can just extract the whole characters folder which will give you all the character models or just the environment folder this contains all the moving parts for maps like doors and such), levels, effects and lighting(all of these contain models related to scenery, many maps share models between them so you need to extract all)

- place the ff7 tool into UmodelSaved\End\Content\GameContents(this file path would have been created by umodel)

- run ff7 tool(double click the tool) it will extract all blueprints, environments, levels, effects and lighting assets

- You will end up with folders for materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw and textures and blueprint.db and material.db files and some loose .ascii models

- move materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw, textures a blueprint.db and material.db files and some loose .ascii models to the map folder you want to extract for example UmodelSaved\End\Content\GameContents\Level\Game\Field\020-TOWN8\Layout(must be 'layout' not 'layout merged')

- Drag a .umap onto the ff7 tool for example 020-TOWN8_Layout_010-OuterWall.umap(there will be many umaps with extra bits on there name like 020-TOWN8_Layout_010-OuterWall_Animation.umap and 020-TOWN8_Layout_010-OuterWall_animation.umap extract all the ones listed here;
Animation.umap(many doors and moving elements are in here)
collision.umap(only if you want to put this in a game engine where you will want collision as this is a simplified collision mesh for the level) 
envplan.umap(contains the breakable crates that are ingame but good as props)
lighting.umap (these are the models for the lighting as well as the models for lit windows ect)
all of these contain models so extract them for there .ascii the rest you can ignore they dont seem extract anything there are also uexp files ignore these too)

- you will get 3 text log files like this 020-TOWN8_Layout_010-OuterWall.names.txt, 020-TOWN8_Layout_010-OuterWall.export.txt, 020-TOWN8_Layout_010-OuterWall.import.txt and .ascii files(you will get one or several of these .ascii they are generated with what seems to be a 100mb cap as there being generated if it hits this cap it splits off into another .ascii file)

- I then move the generated .ascii files into the textures folder that we got from the ff7 tool

- i also converted all dds textures in this texture folder to png as the .ascii expects png not dds(you can convert these many ways using verios tools umodel and do this too or you can use notepad++ to edit the .ascii and replace all .png references with .dds)

- Lastly use the blender addon that was linked with the game files to import the ascii, they will import sideways as there using y axis as up where as blender is z axis up by default

All maps import super huge blender has a max view clipping so you wont see the meshes at first
In blender press n to bring up the right side panel click on the view tab
at the top you will have
focal length
clip start
end

change end to something like 1000000 its 1000 by default
and change clip start to 10(this will stop meshes doing a weird zfighting thing)
blender has a minimum and maximum mesh clipping view distance built in to help with performance but you can change that with these values 
you can also use number pad . it will jump the camera to a selected object(when you importa mesh everything imported is selected by default)

- Last note the ff7 tool currently dose not read anything from the effects, character and lighting folders, so the tool will not use there models when generating ascii from umap extracting this means there will still be missing things in the map for example the fountain in sector 8 its model in in effects so it wont show up when you imports the umaps ascii. For now we have to add these manually

Thank you so much for this amazing guide! I got the furthest I ever have but ran into some problems - 

In Umodel I saved the Environments, blueprints, levels, effects and lighting assets, I converted them using the FF7R Tool, then I put them in umodel_win32\UmodelSaved\End\Content\GameContents\Level\Game\Field\140-SBIL0\Layout\CMPNY and dropped the UMAPS onto the FF7R TOOL (several at a time), it made 3 ASCII files that were very small, the largest being 19KB. I put them in the textures folder then imported the ASCII's into Blender and they loaded a square and some floating dots, I adjusted the clip and there was no change to what I was seeing.

Can anyone help me understand why the UMAPS isn't extracting the correct ASCII's please? 



Untitled-2-Recovered.jpg (102 KiB) Viewed 687 times
## Post #146
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2020-07-31T16:31:49+00:00
- Post Title: Re: Final Fantasy 7 remake

Found a lot of great info in this thread and finally started to get Noesis to directly export the UASSET model files, but I still cannot get it to export or display animations (even after instructing it to use the right version of U4 and the 7R tool).

Could anyone give me some tips about how to get animations to export from noesis?  That would be greatly appreciated!  Thanks
## Post #147
- Username: GuillermoGatoto
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 09, 2018 1:56 pm
- Post datetime: 2020-08-20T23:09:33+00:00
- Post Title: Re: Final Fantasy 7 remake

Could anyone send me a link to the PKG and the decryption key? I would appreciate it a lot! Thanks
## Post #148
- Username: rshadow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 12, 2020 5:51 pm
- Post datetime: 2020-09-08T02:16:45+00:00
- Post Title: Re: Final Fantasy 7 remake

Does anyone have the "Unable to read beyond the end of stream" error with umap conversion?
I extracted all files from GameContents, ran ff7r and got all materials, skeletalmesh, skeletalmesh.raw, staticmesh, staticmesh.raw, textures a blueprint.db and material.db, moved all of the above folders/files and other ascii files along with ff7r to a new folder, then drop a umap file to ff7r.exe.
However I only had the 3 txt file generated properly. No ascii file generated and the error "unable to read beyond the end of stream" occurred.
I tried the whole process on two computers, both returning the same error.
## Post #149
- Username: bethanyannie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jun 11, 2020 9:45 pm
- Post datetime: 2020-09-11T11:16:58+00:00
- Post Title: Re: Final Fantasy 7 remake

Is it possible to extract ASCII from the TOWN7 UMAPS? I've managed every other UMAP but TOWN7 reads as missing and will only extract the Light ASCII's... just want to check it's the folder and not me, thanks!
## Post #150
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2020-09-12T14:58:13+00:00
- Post Title: Re: Final Fantasy 7 remake

Does anyone know how to get Noesis to export the Backcloth files?  they display fine in Noesis, but when I export they are blank white files.  Thanks!
## Post #151
- Username: Fuegoo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 04, 2020 10:14 pm
- Post datetime: 2020-11-03T08:40:13+00:00
- Post Title: Re: Final Fantasy 7 remake

Hi,

with Noesis I cannot export the animations I have problems when I put an animation on the model I have problems

Help me please

possible to make the FF7 Remake tool compatible with the animations please
[FF7 Remake.jpg](https://xentaxbackup.github.io/file/18945_FF7 Remake.jpg)
## Post #152
- Username: Fuegoo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 04, 2020 10:14 pm
- Post datetime: 2020-11-03T08:42:02+00:00
- Post Title: Re: Final Fantasy 7 remake

I can export the animations with Noesis
[FF7.jpg](https://xentaxbackup.github.io/file/18946_FF7.jpg)
## Post #153
- Username: klee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 14, 2020 8:36 pm
- Post datetime: 2020-11-23T03:39:59+00:00
- Post Title: Re: Final Fantasy 7 remake

Thank you for the tool! It's my first time trying to extract models.I can't extract player animation,please help me
## Post #154
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2020-11-26T15:14:37+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Nihyaku ↑Sun Jul 05, 2020 4:38 am at Sun Jul 05, 2020 4:38 am
>
> 
linsaberlove wrote: ↑Fri Jul 03, 2020 11:12 am
There are many kinds of texture maps when I export a character,I want to use blender to render but not sure what they stand for.
I guess C base color ,A alpha ,N tangent normal, O roughness,M shallow color.... Am I correct?
So what does B  NB stand for and how can I use them in blender? Thx 


Hi! You're right for C, A and N texture maps! O should be ambient occlusion; as for M map, it contains informations about metallic and roughness maps: the red channel is the former and the green channel is the latter!
I've heard that some people use B map for subsurface scattering; personally, I use it as a mask texture to define which parts shouldn't be affected by a detail map (I don't use Blender, but another rendering software!)
As for NB texture map, I can't help you, because I don't know either!
I hope this helps! (◍•ᴗ•◍)

Hi,it seems the B chaneel of M map is not always empty,what does it do? In the common texture there are leather,fabric and skin detail map,are they the datail maps you mentioned? It seems they are all normal map ? How to use them?
## Post #155
- Username: Nihyaku
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 08, 2017 7:06 pm
- Post datetime: 2020-12-09T16:40:01+00:00
- Post Title: Re: Final Fantasy 7 remake

> Hi,it seems the B chaneel of M map is not always empty,what does it do? In the common texture there are leather,fabric and skin detail map,are they the datail maps you mentioned? It seems they are all normal map ? How to use them?

To tell the truth, I don't know about the B channel. Sometimes it contains information about transparency, sometimes emissive maps or even masks. If I remember well, I read somewhere that the B channel is called "variant map", so it depends on the mesh it's applied to.
Yes, leather, fabric and skin are detail maps. They add details to the mesh they're applied to. For example, the skin detail map simulates the skin pores! I'm sure they're usable in Blender Cycles, but I don't know how. I'm sorry!
## Post #156
- Username: jusete
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 19, 2014 8:00 pm
- Post datetime: 2020-12-29T00:41:54+00:00
- Post Title: Re: Final Fantasy 7 remake

Hi! How can I load a model with textures in noesis? Can see the model but with a metallic texture only. Thank you!
## Post #157
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2021-01-01T05:55:28+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Nihyaku ↑Thu Dec 10, 2020 12:40 am at Thu Dec 10, 2020 12:40 am
>
> 
Hi,it seems the B chaneel of M map is not always empty,what does it do? In the common texture there are leather,fabric and skin detail map,are they the datail maps you mentioned? It seems they are all normal map ? How to use them?


To tell the truth, I don't know about the B channel. Sometimes it contains information about transparency, sometimes emissive maps or even masks. If I remember well, I read somewhere that the B channel is called "variant map", so it depends on the mesh it's applied to.
Yes, leather, fabric and skin are detail maps. They add details to the mesh they're applied to. For example, the skin detail map simulates the skin pores! I'm sure they're usable in Blender Cycles, but I don't know how. I'm sorry!

..The detail maps are normal maps,however these meshes already have normal maps.That's the confusing point - -
## Post #158
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-01-03T06:05:03+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from linsaberlove ↑Fri Jan 01, 2021 1:55 pm at Fri Jan 01, 2021 1:55 pm
>
> 
Nihyaku wrote: ↑Thu Dec 10, 2020 12:40 am
Hi,it seems the B chaneel of M map is not always empty,what does it do? In the common texture there are leather,fabric and skin detail map,are they the datail maps you mentioned? It seems they are all normal map ? How to use them?


To tell the truth, I don't know about the B channel. Sometimes it contains information about transparency, sometimes emissive maps or even masks. If I remember well, I read somewhere that the B channel is called "variant map", so it depends on the mesh it's applied to.
Yes, leather, fabric and skin are detail maps. They add details to the mesh they're applied to. For example, the skin detail map simulates the skin pores! I'm sure they're usable in Blender Cycles, but I don't know how. I'm sorry!


..The detail maps are normal maps,however these meshes already have normal maps.That's the confusing point - -
Consider them mini normals, they are there to add even more details, stuff like dots to leather, stiching, extra fabric details, stuff like that
## Post #159
- Username: flutch
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 22, 2011 3:13 am
- Post datetime: 2021-01-13T00:37:22+00:00
- Post Title: Re: Final Fantasy 7 remake

so, is there any animation or something like gravity for the fabric that can be convert to other 3d software?
## Post #160
- Username: Kogekko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 12, 2015 7:25 pm
- Post datetime: 2021-01-16T17:23:44+00:00
- Post Title: Re: Final Fantasy 7 remake

Hello everyone. Nice to meet you all. I need to edit the fonts of this game (dialogue font, in-game system font...). Does anyone know which .pak contain the fonts? And how can I edit them? I need to edit those fonts to make a translation. Thanks for your help.
## Post #161
- Username: AxelNova12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 29, 2021 1:25 am
- Post datetime: 2021-01-28T17:33:36+00:00
- Post Title: Re: Final Fantasy 7 remake

Hi guys, 
Kinda new here, Just wanted to ask if Simeone has the Mako Station Stage files for Blender...or can You help me get them ?
## Post #162
- Username: thomas39120
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 26, 2021 3:20 pm
- Post datetime: 2021-03-26T07:41:58+00:00
- Post Title: Re: Final Fantasy 7 remake

Can someone please tell me where I can get the game data to be extracted from, a PS4 disc is not recognized by the PC , Because I want to export some of the landscapes and buildings
## Post #163
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2021-03-31T21:31:28+00:00
- Post Title: Re: Final Fantasy 7 remake

So noesis dont work with automatic assign texture, only blender or i have the wrong plugin for ascii. if so can someone share the the link for right ascii plugin (noesis) if ask to much.
## Post #164
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-04-01T18:54:57+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from neusi ↑Thu Apr 01, 2021 5:31 am at Thu Apr 01, 2021 5:31 am
>
> ... can someone share the the link for right ascii plugin (noesis) if ask to much.
There isn't one, only Blender does it.
## Post #165
- Username: thesinfulpuppeteer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 4:02 am
- Post datetime: 2021-04-11T18:20:45+00:00
- Post Title: Re: Final Fantasy 7 remake

The tool works great and I was able to extract Corneo's office and a few other locations plus furnishings.  However only the color map is automatically assigned when I upload into Blender.  Does the Tool auto assign the normals, MRVs, and occlusions maps as well?

Also, does the auto assign work on characters, weapons and enemies too?  I know how to connect the maps in blender manually, but it is time consuming.

Thank you for any assistance.
## Post #166
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-04-12T11:33:15+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from thesinfulpuppeteer ↑Mon Apr 12, 2021 2:20 am at Mon Apr 12, 2021 2:20 am
>
> 
The tool works great and I was able to extract Corneo's office and a few other locations plus furnishings.  However only the color map is automatically assigned when I upload into Blender.  Does the Tool auto assign the normals, MRVs, and occlusions maps as well?

Also, does the auto assign work on characters, weapons and enemies too?  I know how to connect the maps in blender manually, but it is time consuming.

Thank you for any assistance.

The auto assign for the BC should work on more or less everything I think.
But MRV, doesn't work, that requires a custom shader setup in blender since its texture packing, each channel of MRV serves a different purpose.
## Post #167
- Username: thesinfulpuppeteer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 23, 2020 4:02 am
- Post datetime: 2021-04-14T14:38:28+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Mon Apr 12, 2021 7:33 pm at Mon Apr 12, 2021 7:33 pm
>
> 
But MRV, doesn't work, that requires a custom shader setup in blender since its texture packing, each channel of MRV serves a different purpose.
Thank you for your reply.  I had a feeling that was going to be the case.  I know a workaround with the RGB separator, so I'm good there.

> Reply from lionheartuk ↑Mon Apr 12, 2021 7:33 pm at Mon Apr 12, 2021 7:33 pm
>
> 
The auto assign for the BC should work on more or less everything I think.
I gave it another go, and yes the tool does assign maps like so (don't mind the purples, I can fix that), but I have to set them up manually.  Doing this myself is easy for smaller files with fewer sub-meshes, but time consuming for the larger ones.  Also, it only worked for environments, props, and weapons, but not the characters and villains.

My new question now is there another Blender addon or tool that will save time setting up the nodes, or should I use a different program like Unity or DAZ?
## Post #168
- Username: rickypow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 10, 2020 5:34 am
- Post datetime: 2021-05-07T23:45:33+00:00
- Post Title: Re: Final Fantasy 7 remake

For those who have ported levels from Blender to Unity, what format are you exporting to keep the textures in tact? My models are textured properly in blender but when I save as a blend or export as FBX, the textures are not applied automatically in Unity, even with all textures and models uploaded in the same asset folder. I appreciate any help anyone can offer!
## Post #169
- Username: Stallone
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Mar 12, 2020 5:24 am
- Post datetime: 2021-05-25T19:51:12+00:00
- Post Title: Re: Final Fantasy 7 remake

Hello, Does someone have the fonts for the game? Like menu, dialogs, subtitles fonts? I would really like to have the ttf files. I can"t find them in the assets
## Post #170
- Username: lsbg18
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 26, 2021 6:20 pm
- Post datetime: 2021-05-26T10:44:52+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from linsaberlove ↑Sun May 24, 2020 9:21 pm at Sun May 24, 2020 9:21 pm
>
> 
Anyone who know how to export animation?
could you tell me what's the key（the passcode） of FF7 r pkg？if we need it?
## Post #171
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-05-26T11:26:52+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lsbg18 ↑Wed May 26, 2021 6:44 pm at Wed May 26, 2021 6:44 pm
>
> 
linsaberlove wrote: ↑Sun May 24, 2020 9:21 pm
Anyone who know how to export animation? 

could you tell me what's the key（the passcode） of FF7 r pkg？if we need it?

99% chance its just as many 0's as the box will allow, I think it might be 11, just hold 0 until no more 0's appear, and that should be it.

The majority of dumped PS4 PKG files have been decrypted with a password of all 0's.
If you've dumped it yourself though... then its whatever you set I think.
## Post #172
- Username: lsbg18
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 26, 2021 6:20 pm
- Post datetime: 2021-05-26T15:37:02+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Wed May 26, 2021 7:26 pm at Wed May 26, 2021 7:26 pm
>
> 
lsbg18 wrote: ↑Wed May 26, 2021 6:44 pm
linsaberlove wrote: ↑Sun May 24, 2020 9:21 pm
Anyone who know how to export animation? 

could you tell me what's the key（the passcode） of FF7 r pkg？if we need it?


99% chance its just as many 0's as the box will allow, I think it might be 11, just hold 0 until no more 0's appear, and that should be it.

The majority of dumped PS4 PKG files have been decrypted with a password of all 0's.
If you've dumped it yourself though... then its whatever you set I think.
Thank you! I'll try it.
## Post #173
- Username: LuzThePog
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 12, 2021 4:38 am
- Post datetime: 2021-06-11T22:00:22+00:00
- Post Title: Re: Final Fantasy 7 remake

Hi!, I'm quite new here, So I was wondering where I could get the files for the game to export and view models? Would love any help! Thank you in advance if anyone is Kind enough to help!
## Post #174
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-06-11T23:17:07+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from LuzThePog ↑Sat Jun 12, 2021 6:00 am at Sat Jun 12, 2021 6:00 am
>
> 
Hi!, I'm quite new here, So I was wondering where I could get the files for the game to export and view models? Would love any help! Thank you in advance if anyone is Kind enough to help!
If you just google the PKG you will get many links of any kind, really.
## Post #175
- Username: LuzThePog
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 12, 2021 4:38 am
- Post datetime: 2021-06-12T20:36:16+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from mono24 ↑Sat Jun 12, 2021 7:17 am at Sat Jun 12, 2021 7:17 am
>
> 
LuzThePog wrote: ↑Sat Jun 12, 2021 6:00 am
Hi!, I'm quite new here, So I was wondering where I could get the files for the game to export and view models? Would love any help! Thank you in advance if anyone is Kind enough to help!

If you just google the PKG you will get many links of any kind, really.
Do you think you could link me the site that most people are downloading from, and what to do after? I'm sorry if I'm asking abit too much, it's just that I sometimes worry if these sites could have put malware or any of those sort of things
## Post #176
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2021-06-15T17:50:38+00:00
- Post Title: Re: Final Fantasy 7 remake

Has anyone had success getting into the Intergrade files yet?
## Post #177
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-06-16T02:22:04+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from metapoodle ↑Wed Jun 16, 2021 1:50 am at Wed Jun 16, 2021 1:50 am
>
> 
Has anyone had success getting into the Intergrade files yet?

No, and likely not for a long time, there hasn't been any progress on hacking the PS5, so until then no PS5 games will be touchable.
## Post #178
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2021-06-16T03:35:22+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Wed Jun 16, 2021 10:22 am at Wed Jun 16, 2021 10:22 am
>
> 
metapoodle wrote: ↑Wed Jun 16, 2021 1:50 am
Has anyone had success getting into the Intergrade files yet?


No, and likely not for a long time, there hasn't been any progress on hacking the PS5, so until then no PS5 games will be touchable.

I had a feeling that would be the case--thanks for the update though!
## Post #179
- Username: Caleb123459
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Nov 29, 2019 8:54 am
- Post datetime: 2021-06-19T02:27:49+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from lionheartuk ↑Wed Jun 16, 2021 10:22 am at Wed Jun 16, 2021 10:22 am
>
> 
metapoodle wrote: ↑Wed Jun 16, 2021 1:50 am
Has anyone had success getting into the Intergrade files yet?


No, and likely not for a long time, there hasn't been any progress on hacking the PS5, so until then no PS5 games will be touchable.

There's a tool capable of decompiling PS5 PKG files, tho its not finished and seems to have trouble with large PKG files. Unfortunately, the INTERmission PKGs are too big for the program as they will create a MemoryError. I reported the bug to the devs in hopes they can get the program fully working as I'd love to rip Weiss and Nero ^^

Here's the PKG tool if you're interested: [https://github.com/SKFU/ps5tools](https://github.com/SKFU/ps5tools)
I've tested it on several PKG files, but like I said big ones such as the INTERmission PKGs will not work atm.
## Post #180
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-06-19T12:42:56+00:00
- Post Title: Re: Final Fantasy 7 remake

@Caleb123459: Those tools are for parsing some unencrypted info from firmware (PUP) and a few other system files, like SLB2, FIH and CNT. It has nothing to do with actual game data (which is fully encrypted), nor it will in the future.
## Post #181
- Username: LuzThePog
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 12, 2021 4:38 am
- Post datetime: 2021-06-22T00:26:40+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from LuzThePog ↑Sun Jun 13, 2021 4:36 am at Sun Jun 13, 2021 4:36 am
>
> 
mono24 wrote: ↑Sat Jun 12, 2021 7:17 am
LuzThePog wrote: ↑Sat Jun 12, 2021 6:00 am
Hi!, I'm quite new here, So I was wondering where I could get the files for the game to export and view models? Would love any help! Thank you in advance if anyone is Kind enough to help!

If you just google the PKG you will get many links of any kind, really.

Do you think you could link me the site that most people are downloading from, and what to do after? I'm sorry if I'm asking abit too much, it's just that I sometimes worry if these sites could have put malware or any of those sort of things
Any help? I downloaded the PKG and I don't know what to do next
## Post #182
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-06-24T14:48:57+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from LuzThePog ↑Tue Jun 22, 2021 8:26 am at Tue Jun 22, 2021 8:26 am
>
> 
LuzThePog wrote: ↑Sun Jun 13, 2021 4:36 am
mono24 wrote: ↑Sat Jun 12, 2021 7:17 am

If you just google the PKG you will get many links of any kind, really.

Do you think you could link me the site that most people are downloading from, and what to do after? I'm sorry if I'm asking abit too much, it's just that I sometimes worry if these sites could have put malware or any of those sort of things

Any help? I downloaded the PKG and I don't know what to do next
Search a Tool like unpkg Editor
## Post #183
- Username: ZackFair00210
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 01, 2021 8:04 pm
- Post datetime: 2021-07-01T12:08:50+00:00
- Post Title: Re: Final Fantasy 7 remake

Hey...uh guys aren`t we gonna talk about the INTEGRADE models? isn`t there a way to get`em yet??
## Post #184
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-07-01T14:50:22+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from ZackFair00210 ↑Thu Jul 01, 2021 8:08 pm at Thu Jul 01, 2021 8:08 pm
>
> 
Hey...uh guys aren`t we gonna talk about the INTEGRADE models? isn`t there a way to get`em yet??

No, there's no PS5 rom dumps yet.
## Post #185
- Username: ArtFromCode
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 21, 2011 9:20 am
- Post datetime: 2021-07-15T22:27:47+00:00
- Post Title: Re: Final Fantasy 7 remake

I ran into a problem exporting the heliport from the Shinra Building.  Basically, it says this:

```
Unknown matrix size 0
iUnknown matrix size 9054
Error exporting asset*directory*140-SBIL0_Layout__CMPNY_160-F70Heliport.umap
Unable to read beyond the end of the stream.
   at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
   at System.IO.BinaryReader.ReadSingle()
   at UE4.ue4.Main(String[] args)
```


Am I doing something wrong here?
## Post #186
- Username: CyphersAscent
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 20, 2020 4:19 am
- Post datetime: 2021-07-24T23:31:17+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from DioBrando ↑Tue May 26, 2020 12:48 pm at Tue May 26, 2020 12:48 pm
>
> 
gamenpc wrote: ↑Tue May 26, 2020 12:14 pm
DioBrando wrote: ↑Tue May 26, 2020 8:56 am


Probably the dress is simulated. You'll need to run some kind of cloth sim.

There is a lot nicer way to view animations to:
Set “Tools->Data Viewer->Other->Default preview commands” to:
-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath "F:\FF7_Remake\End2\Content\GameContents"

"F:\FF7_Remake\End2\Content\GameContents" will be your GameContents with all the extracted packages obviously. This will load all the textures in the preview window too.

Load the model and just drag-and-drop the anim you want to apply to it over the preview window from windows explorer, or use the “apply to preview” script in optionalplugins.


Thanks, I did it. Buy……  


I want to import unity. 
Sorry, my English is terrible.


You can work directly with the uassets in Noesis, nothing else is required. You can then go to "file->export from preview" to export an fbx model with the animation attached. It will load to Unity. In the Noesis tools menu you can create a Batch Process to export all animation in the game to fbx using those same export commands "-ue4anims -ue4tex1dthin -ue4tex1dalign -ue4datapath"
474846.jpg

Is there any way someone could upload a video on how to do these batch exports? I'm trying to get all of Cloud's battle animations, and I've been going through and exporting from preview with each individual animation, but I'd like to know exactly how to do use the batch process to save time from exporting hundreds of files. Been at it for the past two hours but none of what I'm doing is working. Noesis keeps telling me it can't find the skeleton, but I have no idea how to load the skeleton in with the batch tool. Could anyone help at all? Thanks!
## Post #187
- Username: Irnkman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 30, 2021 5:09 am
- Post datetime: 2021-12-17T20:43:41+00:00
- Post Title: Re: Final Fantasy 7 remake

Anyone have the AES key for the PC release?
## Post #188
- Username: CyphersAscent
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 20, 2020 4:19 am
- Post datetime: 2021-12-17T20:49:12+00:00
- Post Title: Re: Final Fantasy 7 remake

This should work, just scroll to FF7R

[https://cs.rin.ru/forum/viewtopic.php?f=10&t=100672](https://cs.rin.ru/forum/viewtopic.php?f=10&t=100672)
## Post #189
- Username: VictorGopher
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 09, 2021 1:04 am
- Post datetime: 2021-12-18T14:20:49+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from CyphersAscent ↑Sat Dec 18, 2021 4:49 am at Sat Dec 18, 2021 4:49 am
>
> 
This should work, just scroll to FF7R

https://cs.rin.ru/forum/viewtopic.php?f=10&t=100672

AES key works, but I got an index out of bound error when I tried to extract character uasset
nor did the Umodel works
## Post #190
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2021-12-18T17:29:24+00:00
- Post Title: Re: Final Fantasy 7 remake

Check the ffvii thread in gildor's forum.

[https://www.gildor.org/smf/index.php/to ... 5.120.html](https://www.gildor.org/smf/index.php/topic,6925.120.html)
## Post #191
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2022-01-08T21:39:34+00:00
- Post Title: Re: Final Fantasy 7 remake

Final Fantasy VII: The First Soldier is a ue4 game 
Its 4.25
[https://www.gildor.org/smf/index.php?topic=7769.0](https://www.gildor.org/smf/index.php?topic=7769.0)
Any chance this tool can support this as id like to be able to recreate the maps

Although there lowpoly mobile models i recon i can look through the remake models and find and replace the mobile models to make a remake equivalent of the slums seen in first soldier.

Just need a way to rebuild the umaps into blender like i can with your awesome tool daemon1
## Post #192
- Username: RadiantPulse
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 01, 2021 12:35 am
- Post datetime: 2022-01-18T00:18:11+00:00
- Post Title: Re: Final Fantasy 7 remake

Is there any video tutorial ? I know there's a pretty detailed post explaining every step of the process on how to extract a map but I can't find that import script for Blender ;_;
Any kind soul that could give me some help ?
Thanks
## Post #193
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2022-01-18T04:14:28+00:00
- Post Title: Re: Final Fantasy 7 remake

well indivually i can grab the mesh parts but im wondering that myself  as well how do ppl export the whole map any advice would be useful regarding instructions to do so ; some of these maps have over 400 meshes so its not practical to port each item 1 by 1
## Post #194
- Username: brolly234
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 19, 2018 7:32 pm
- Post datetime: 2022-01-19T14:07:43+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from VictorGopher ↑Sat Dec 18, 2021 10:20 pm at Sat Dec 18, 2021 10:20 pm
>
> 
CyphersAscent wrote: ↑Sat Dec 18, 2021 4:49 am
This should work, just scroll to FF7R

https://cs.rin.ru/forum/viewtopic.php?f=10&t=100672


AES key works, but I got an index out of bound error when I tried to extract character uasset
nor did the Umodel works

I am getting same error. Did you found any soln??
## Post #195
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2022-01-20T04:46:26+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from speaker60 ↑Sun Jan 09, 2022 5:39 am at Sun Jan 09, 2022 5:39 am
>
> 
Final Fantasy VII: The First Soldier is a ue4 game 
Its 4.25
https://www.gildor.org/smf/index.php?topic=7769.0
Any chance this tool can support this as id like to be able to recreate the maps

Although there lowpoly mobile models i recon i can look through the remake models and find and replace the mobile models to make a remake equivalent of the slums seen in first soldier.

Just need a way to rebuild the umaps into blender like i can with your awesome tool daemon1

Version is 4.18, no 4.25
## Post #196
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-01-21T02:56:17+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from Darko ↑Thu Jan 20, 2022 12:46 pm at Thu Jan 20, 2022 12:46 pm
>
> 
Version is 4.18, no 4.25
I suppose he is referencing to The First Soldier, which is totally different game and built with UE 4.25. It's just there are not much map tools around, so people may ask about unrelated stuff in similar topics instead of creating new ones.
## Post #197
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2022-02-22T00:36:45+00:00
- Post Title: Re: Final Fantasy 7 remake

Is the source code available for this? I would love to make some tweaks, (specifically, exporting position and rotation data) and trying my hand at Intergrade support.
## Post #198
- Username: laughingorc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 10, 2021 3:45 pm
- Post datetime: 2022-05-18T19:13:40+00:00
- Post Title: Re: Final Fantasy 7 remake

sorry to necro an old thread, but I'm following the instructions - I saved the packages from umodel for the whole Gamecontents folder -  and the tool is throwing up a string of errors - all it does is return this for every file, starting with- 

Error exporting asset J:\End\Content\GameContents\Lighting\Texture\light_MRV.uasset
Index was outside the bounds of the array.
   at UE4.ue4.readprops(List`1 plist, MemoryStream fs, BinaryReader br)
   at UE4.ue4.Main(String[] args)

Eventually it finishes and I'm left with a blueprint.db file and no other new folders.
Presumably I'm missing something, or I've done something wrong, but I've no idea what   

Any help would be greatly appreciated!
## Post #199
- Username: annabanana
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 11, 2022 9:24 pm
- Post datetime: 2022-06-11T13:28:05+00:00
- Post Title: Re: Final Fantasy 7 remake

Hello, I am looking for ingame models of Aeirith lily flowers with textures. Both the highpoly version that Aerith holds in her hands and a low poly model that are placed on the churche's ground. Could anyone please share the files or help me with locating them in the extracted files? Thank you.
## Post #200
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2022-06-15T18:56:08+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from laughingorc ↑Thu May 19, 2022 3:13 am at Thu May 19, 2022 3:13 am
>
> 
sorry to necro an old thread, but I'm following the instructions - I saved the packages from umodel for the whole Gamecontents folder -  and the tool is throwing up a string of errors - all it does is return this for every file, starting with- 

Error exporting asset J:\End\Content\GameContents\Lighting\Texture\light_MRV.uasset
Index was outside the bounds of the array.
   at UE4.ue4.readprops(List`1 plist, MemoryStream fs, BinaryReader br)
   at UE4.ue4.Main(String[] args)

Eventually it finishes and I'm left with a blueprint.db file and no other new folders.
Presumably I'm missing something, or I've done something wrong, but I've no idea what   

Any help would be greatly appreciated!

This tool wasnt made for intergrade but the ps4 version so im guessing it would need to be updated for intergrade support as i just tried and got the same errors as you
## Post #201
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2022-06-23T01:11:34+00:00
- Post Title: Re: Final Fantasy 7 remake

Can I use this with the Steam Version? Or is that version not supported?
## Post #202
- Username: hz12345678
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 17, 2022 2:23 pm
- Post datetime: 2022-07-17T06:24:23+00:00
- Post Title: Re: Final Fantasy 7 remake

how to import the generated ASCII from UMAP to blender ?
## Post #203
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-08-19T11:52:28+00:00
- Post Title: Re: Final Fantasy 7 remake

For those who interested, Intergrade animations are now mostly supported in separate umodel build (more info [here](https://www.gildor.org/smf/index.php/topic,6925.msg43676.html#msg43676)).
## Post #204
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2022-11-13T23:00:06+00:00
- Post Title: Re: Final Fantasy 7 remake

Would someone please help me? I've got this error: s
+ 0000000000000049 12995      Mob\MB0000_00_Boy_Standard\Model\MB0000_00_Skeleton.uasset
  0000000000000000 0          Mob\MG0000_00_Girl_Standard\Model\MG0000_00_Skeleton.uasset
+ 0000000000001849 14486      Mob\MG0000_00_Girl_Standard\Model\MG0000_00_Skeleton.uasset
Info:  algorithm   250
       offset      0000000000001849
       input size  0x000000000000125a 4698
       output size 0x0000000000003896 14486
       result      0xffffffffffffffff -1

Error: uncompressed data (-1) bigger than allocated buffer (14486)
       It usually means that data is not compressed or uses another algorithm

Last script line before the error or that produced the error:
  233 clog NAME CHUNK_OFFSET CHUNK_ZSIZE CHUNK_SIZE 0 CHUNK_XSIZE

- OFFSET       0x0000000000001849
- ZSIZE        0x000000000000125a
- SIZE         0x0000000000003896
  coverage file 0     0%   2938155    2557878709 . offset 0000000000002aa3
  coverage file -10   0%   326        2933408    . offset 0000000000000146
## Post #205
- Username: xxx66778899
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 06, 2022 11:31 pm
- Post datetime: 2022-12-06T15:33:33+00:00
- Post Title: Re: Final Fantasy 7 remake

Very good sharing thanks
## Post #206
- Username: whyfory
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 30, 2023 2:48 pm
- Post datetime: 2023-04-30T09:15:14+00:00
- Post Title: Re: Final Fantasy 7 remake

Thank you very much for creating this tool, but can you publish your source code for learning? Because I encountered a "bad allocation" error when exporting the model using Umode. I tried to debug in Visual Studio, but couldn't find the true cause. The only clue is that this seems to be caused by an inability to access memory. Does this mean that the model file of FF7Re is relatively special and cannot be exported, Or can you explain the principle of this tool？
## Post #207
- Username: Matheuh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2022 6:25 am
- Post datetime: 2023-05-30T16:41:57+00:00
- Post Title: Re: Final Fantasy 7 remake

Hi daemon! Is it possible to get a tutorial for A WAY OUT Extract Maps? I can pay for it 
Followed the full tutorial, but the umap exporter only lights into the ascii
## Post #208
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-30T20:40:31+00:00
- Post Title: Re: Final Fantasy 7 remake

Can you go back to your post and edit it, there's no need to quote the whole thing and make such a mess.

> Reply from Matheuh ↑Wed May 31, 2023 12:41 am at Wed May 31, 2023 12:41 am
>
> ...Is it possible to get a tutorial for A WAY OUT Extract Maps?...
What is wrong with this quick example? [viewtopic.php?p=165180#p165180](https://forum.xentax.com/viewtopic.php?p=165180#p165180)
## Post #209
- Username: Matheuh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2022 6:25 am
- Post datetime: 2023-05-30T22:24:18+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from mono24 ↑Wed May 31, 2023 4:40 am at Wed May 31, 2023 4:40 am
>
> 
Can you go back to your post and edit it, there's no need to quote the whole thing and make such a mess.
Matheuh wrote: ↑Wed May 31, 2023 12:41 am...Is it possible to get a tutorial for A WAY OUT Extract Maps?...
What is wrong with this quick example? viewtopic.php?p=165180#p165180

Done sorry
## Post #210
- Username: Matheuh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2022 6:25 am
- Post datetime: 2023-06-01T09:03:54+00:00
- Post Title: Re: Final Fantasy 7 remake

> Reply from mono24 ↑Wed May 31, 2023 4:40 am at Wed May 31, 2023 4:40 am
>
> 
Can you go back to your post and edit it, there's no need to quote the whole thing and make such a mess.
Matheuh wrote: ↑Wed May 31, 2023 12:41 am...Is it possible to get a tutorial for A WAY OUT Extract Maps?...
What is wrong with this quick example? viewtopic.php?p=165180#p165180

What is wrong?
Well it's exporting only lights
