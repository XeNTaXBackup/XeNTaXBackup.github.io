## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-16T15:48:48+00:00
- Post Title: UniViewer - Multiple Games Tool

I decided to collect my works into a single tool. There will be a base program that you need to download once, I will release small dll plugins for each new game. This should decrease the file size and also make it easier to manage.

How To Use

Launcher

Run the UniLauncher.exe first. It will show you all the game plugins inside the "Plugins" folder. Select the plugin you want to use and click the "Launch" button.



Program



Load

Model File : Path of the model file. Use "..." for file browser.
Skeleton File : Only required if the game uses separate skeleton files for models. Use "..." for file browser.
Load : Loads the model and shows it in preview window.
Notes

Game specific information.
Export

NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format : Nex Script
IQE : Exports the model in IQE format. Read here to see how to load IQE : http://forum.xentax.com/viewtopic.php?p=138153#p138153
Note  : Models will be exported into the folder Export.
Note 2  : Exporting might take some time depending on the game/model. Be patient with it.
Download : [https://www.mediafire.com/file/sefg2xpg ... 2.rar/file](https://www.mediafire.com/file/sefg2xpglfst4b2/UniViewer_U2.rar/file)

Result




Game Plugins

Plugins are .dll files that need to placed inside the Plugins folder.

Plugin Download : [https://www.mediafire.com/folder/agmytf24e5cja/](https://www.mediafire.com/folder/agmytf24e5cja/)

Supported Games

 - Danganronpa Ultra Despair Girls

Note  : Made based on few uploaded samples. Might not work with everything.
 - Dawn of Titans

BMS script for .bof archives : BOF Script
Tool for extracting textures : DotImgEx . Use Compressonator for loading the extracted .dds files.
 - Final Fantasy Type-0 HD

BMS script for the archive unpacking : http://forum.xentax.com/viewtopic.php?f=10&t=13224 
 - Summon Night 6

Works with Digimon Story: Cyber Sleuth – Hacker's Memory too, and possibly other Media Vision games.
 - Ty the Tasmanian Tiger 2/3

BMS script for the archive (.rkv) unpacking : RKV Script 
 - Valkyrie Anatomia
## Post #2
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T02:03:27+00:00
- Post Title: UniViewer - Multiple Games Tool

Very good tool. You are a genius.
However, in the process of extracting, I found that some of them could be displayed normally, while others could not. Can you see why?
I think it may be the problem of QuickBMS extracting script, some of which are normal and some are wrong.
## Post #3
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T02:09:36+00:00
- Post Title: UniViewer - Multiple Games Tool

This is a question screenshot.
[01420.png](https://xentaxbackup.github.io/file/15191_01420.png)
## Post #4
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T02:12:21+00:00
- Post Title: UniViewer - Multiple Games Tool

This is a question screenshot.
[100845.png](https://xentaxbackup.github.io/file/15189_100845.png)
## Post #5
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T02:12:59+00:00
- Post Title: UniViewer - Multiple Games Tool

This is a question screenshot.
[01116.png](https://xentaxbackup.github.io/file/15190_01116.png)
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-17T02:44:52+00:00
- Post Title: UniViewer - Multiple Games Tool

That was my bad. I didn't do many tests with map files. They are working fine now. Also I have noticed that the meshes are loaded mirrored. That is what happens when you don't play the game and don't know what characters should look like 

Use the new plugin : [DoT New Plugin](http://www.mediafire.com/file/84x1yj7x8dwnoy3/Dawn_Of_Titans_U1.rar/file) . There is still a problem with "Clavicle" bones. Nothing too serious, but maybe I can try to fix them later.
## Post #7
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T03:14:42+00:00
- Post Title: UniViewer - Multiple Games Tool

Your Nex script can not be installed and used, nor does it support Blender2.8.
## Post #8
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T03:17:01+00:00
- Post Title: UniViewer - Multiple Games Tool

How do I export texture? Thank you
## Post #9
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T04:24:45+00:00
- Post Title: UniViewer - Multiple Games Tool

There is a new problem. Some models are incorrect after extraction, and some files can not be extracted. The screenshots are as follows:
[352.png](https://xentaxbackup.github.io/file/15193_352.png)
## Post #10
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T04:25:34+00:00
- Post Title: UniViewer - Multiple Games Tool

some files can not be extracted. The screenshots are as follows:
[20843.png](https://xentaxbackup.github.io/file/15194_20843.png)
## Post #11
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T04:31:00+00:00
- Post Title: UniViewer - Multiple Games Tool

Error report
[115544.png](https://xentaxbackup.github.io/file/15195_115544.png)
## Post #12
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-17T09:42:01+00:00
- Post Title: UniViewer - Multiple Games Tool

@xtiger Please don't double post that much . I appreciate you reporting the problems but better pm them to me instead of multiple comments.

> Reply from xtiger
>
> Your Nex script can not be installed and used, nor does it support Blender2.8.
Nex script is not a Blender script, it is for Noesis.

> Reply from xtiger
>
> How do I export texture?
I hhaven't released the tool for extracting the textures yet, I will do it some time.

> Reply from xtiger
>
> some files can not be extracted
Change the output size in script. In dot_bof.bms change value 10000000 to something larger, like 15000000.
## Post #13
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T10:34:48+00:00
- Post Title: UniViewer - Multiple Games Tool

OK,Thank you
This game's texture extraction script (.BMS), can you provide it to me? Thank you
[viewtopic.php?%20F=16&t=19062&start=15](http://forum.xentax.com/viewtopic.php?%20F=16&t=19062&start=15)
NPK
[https://www49.zippyshare.com/v/xKzfyZND/file.html](https://www49.zippyshare.com/v/xKzfyZND/file.html)
## Post #14
- Username: Ziella
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 04, 2018 12:45 pm
- Post datetime: 2018-11-20T08:59:07+00:00
- Post Title: UniViewer - Multiple Games Tool

Would there happen to be any chance of sharing the source code for the plugins? Would like to take a look at the Danganronpa Another Episode one and see how it works and compare it to a maxscript I was given a while back which can read the normals as well for the few models it worked with.
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-20T13:01:37+00:00
- Post Title: UniViewer - Multiple Games Tool

I won't be sharing the source code of the plugins.

You can take a look at the discussion of the .bnc format : [viewtopic.php?f=16&t=16463](http://forum.xentax.com/viewtopic.php?f=16&t=16463) The plugin is more or less the product of this research.
## Post #16
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2018-11-20T16:50:01+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur
>
> 
[*]NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis.

I have never heard about the .nex format before.
Is it your own format?

(Or which program uses it officially?)
## Post #17
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-20T16:54:22+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from Karpati
>
> 
Is it your own format?
It is. That is why I wrote "custom".
## Post #18
- Username: Ziella
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 04, 2018 12:45 pm
- Post datetime: 2018-11-21T05:51:52+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur
>
> I won't be sharing the source code of the plugins.

You can take a look at the discussion of the .bnc format : viewtopic.php?f=16&t=16463 The plugin is more or less the product of this research.
Ah I see, alright then. Any plans to add support to read the normals from .bnc files in that case then?
## Post #19
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-21T20:24:23+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from Ziella
>
> 
Ah I see, alright then. Any plans to add support to read the normals from .bnc files in that case then?
Normals are not inside the vertex blocks, they are stored separately for some reason. That is why I didn't bother getting the normals.

I can update the plugin to load the normals too. I will do it when I have the time.
## Post #20
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-04T03:19:36+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

NEW GAME : Summon Night 6

Released a new plugin for Summon Night 6 on PS Vita. It also works with  Digimon Story: Cyber Sleuth – Hacker's Memory.

Example exported model




Preview Digimon models
## Post #21
- Username: kenwandou
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 02, 2014 1:08 pm
- Post datetime: 2018-12-29T09:48:27+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

Can you update it to open the texture?
## Post #22
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-29T10:54:59+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from kenwandou
>
> Can you update it to open the texture?
For which game? I am guessing you mean Summon Night/Digimon. Those games use standard GXT format if I remember correctly. You should be able to load them with Noesis.
## Post #23
- Username: kenwandou
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 02, 2014 1:08 pm
- Post datetime: 2018-12-29T14:59:44+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur
>
> kenwandou wrote:Can you update it to open the texture? 
For which game? I am guessing you mean Summon Night/Digimon. Those games use standard GXT format if I remember correctly. You should be able to load them with Noesis.
 Dawn of Titans, Media\Flow\Textures\     How to open these ETC files? 
Thanks~
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-29T16:53:11+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from kenwandou
>
> 
 Dawn of Titans, Media\Flow\Textures\     How to open these ETC files?
I actually made a tool for extracting the textures, but forgot to post it. I am on holiday atm, I will post it after I get back. Like in a week or so.
## Post #25
- Username: kenwandou
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 02, 2014 1:08 pm
- Post datetime: 2019-01-09T15:35:16+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur
>
> kenwandou wrote:
 Dawn of Titans, Media\Flow\Textures\     How to open these ETC files? 
I actually made a tool for extracting the textures, but forgot to post it. I am on holiday atm, I will post it after I get back. Like in a week or so.
  I hope you haven't forgotten it.
## Post #26
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-17T20:59:08+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

BASE PROGRAM UPDATE

- Exporting textures as png (if supported)
- Exporting models with texture maps
- Much faster model exporting

Make sure to download  the new base program and the new Nex script from the first post.

NEW GAME : Final Fantasy Type-0 HD

Everything is supported including skinning and texture maps. Requires the latest tool/script.



Misc.
- Released a new tool for extracting textures from DoT files.
## Post #27
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-01-18T03:24:06+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur
>
> BASE PROGRAM UPDATE

- Exporting textures as png (if supported)
- Exporting models with texture maps
- Much faster model exporting

Make sure to download  the new base program and the new Nex script from the first post.

NEW GAME : Final Fantasy Type-0 HD

Everything is supported including skinning and texture maps. Requires the latest tool/script.



Misc.
- Released a new tool for extracting textures from DoT files.

This is pretty great

Do environments also load without issue?
## Post #28
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-18T10:55:38+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from lionheartuk
>
> 
Do environments also load without issue?
I haven't even tried loading them tbh  Anything without skeleton should fail though.

I can add support for maps, it would just require a few changes. I will let you know when I update the plugin.
## Post #29
- Username: NovaChrystalia
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 16, 2015 9:26 am
- Post datetime: 2019-01-18T15:32:26+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur
>
> BASE PROGRAM UPDATE

NEW GAME : Final Fantasy Type-0 HD

YOU DON'T KNOW HOW GRATEFUL I AM SEEING YOUR POST!!!!
THANK YOU SOOOOOOOOO MUCHHHH FOR YOUR HARD WORK!! (sorry for the caplocks but I've been waiting for someone to help extracting FF Type-0 HD models for 4 years, yep)

I'm looking forward to seeing new environments from type-0 being supported! xD
Thank you so much x1000000000000000000000 times again!! You made my whole year jdkslajekwa ;;;;;
## Post #30
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-18T23:56:57+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

Updated FFT0 plugin to support maps, but had to update the base program again to add OBJ export. So download the base and the plugin again. I recommend exporting all maps as OBJ.

Preview of a map in UniViewer



School map loaded in Maya
## Post #31
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-01-19T02:12:56+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

That looks great, thankyou.
In almost everygame its the environments I'm after, so I love when someones willing to support them.
## Post #32
- Username: NovaChrystalia
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 16, 2015 9:26 am
- Post datetime: 2019-01-19T22:30:56+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur
>
> Updated FFT0 plugin to support maps, but had to update the base program again to add OBJ export. So download the base and the plugin again. I recommend exporting all maps as OBJ.
YOU'RE AN ANGEL!!!!

Now I can go and make some fun memes with type-0 characters to my heart's content xD
## Post #33
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-28T19:41:32+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

NEW GAME : Ty the Tasmanian Tiger 2/3 (PC)

I remember having fun playing this series when I was younger. The model format was also fun, but kinda troublesome  Probably because it was designed for PS2.

I tested this mostly with Ty 3 models, but Ty 2 seems to have the same format. Skinned models was the main focus. Still environment models should load fine too. They might not appear in preview, because of their scale.

MDG and MDL files are necessary, ANM is optional (for skeleton).
## Post #34
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-01-31T19:12:58+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur
>
> NEW GAME : Ty the Tasmanian Tiger 2/3 (PC)

I remember having fun playing this series when I was younger. The model format was also fun, but kinda troublesome  Probably because it was designed for PS2.

I tested this mostly with Ty 3 models, but Ty 2 seems to have the same format. Skinned models was the main focus. Still environment models should load fine too. They might not appear in preview, because of their scale.

MDG and MDL files are necessary, ANM is optional (for skeleton).

I remember that game when i was younger
Playing it alot on PS2
## Post #35
- Username: SalemTheCat
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 26, 2019 7:34 am
- Post datetime: 2019-03-06T20:45:43+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

How can i create my own plugin? For this program of course..
## Post #36
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-06T20:56:57+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from SalemTheCat ↑Thu Mar 07, 2019 4:45 am at Thu Mar 07, 2019 4:45 am
>
> 
How can i create my own plugin?
You can't. This is just something to collect my smaller personal works into a single program. It isn't a full-fledged model viewer with plugin support. That would be Noesis
## Post #37
- Username: SalemTheCat
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 26, 2019 7:34 am
- Post datetime: 2019-03-06T20:58:12+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur ↑Thu Mar 07, 2019 4:56 am at Thu Mar 07, 2019 4:56 am
>
> 
SalemTheCat wrote: ↑Thu Mar 07, 2019 4:45 am
How can i create my own plugin?

You can't. This is just something to collect my smaller personal works into a single program. It isn't a full-fledged model viewer with plugin support. That would be Noesis Thank you! Also your tool is nice as well.
## Post #38
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2019-03-15T00:33:09+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

Hi there, love the program here!

I was wondering if you wanted to add support for other games made by Krome Studios.

Details in a private message that I've sent to you.
## Post #39
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-06-14T07:34:29+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

The updates with the Type-0 Map support seem to work perfectly.
Thankyou so much for this, its really appreciated.
I was wondering if you have plans to support any other games in future via the same tool.
They're both PS1 games, Breath of Fire III and IV, nobody has been interested in the games enough to hack them open.
Coincidentally a number of Capcom games on Ps1 and Ps2 use the same file formats, so it could be an instance of supporting 1 game intentionally, and supporting 10 others unintentionally (provided they didn't change it, but from looking at the files they look similar)
## Post #40
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-14T11:42:55+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from lionheartuk ↑Fri Jun 14, 2019 3:34 pm at Fri Jun 14, 2019 3:34 pm
>
> 
I was wondering if you have plans to support any other games in future via the same tool.
I have plans to release other plugins for this tool, but I rarely do maps. Only when they aren't much different than character model loading. Like FFT0 for example.

> Reply from lionheartuk ↑Fri Jun 14, 2019 3:34 pm at Fri Jun 14, 2019 3:34 pm
>
> They're both PS1 games
PS1 is a bit too old for my taste. Also I have other games that I am working on atm. So unfortunately I won't have the time to look at the games you mentioned.
## Post #41
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2019-07-08T17:08:09+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur ↑Thu Mar 07, 2019 4:56 am at Thu Mar 07, 2019 4:56 am
>
> 
SalemTheCat wrote: ↑Thu Mar 07, 2019 4:45 am
How can i create my own plugin?

You can't. This is just something to collect my smaller personal works into a single program. It isn't a full-fledged model viewer with plugin support. That would be Noesis

hello, i found 1 tool you wrote in 2016. Link: [https://www.reddit.com/r/blackdesertonl ... _explorer/](https://www.reddit.com/r/blackdesertonline/comments/434pl2/tool_black_desert_explorer/)
But I have an error, please help me
[66143641_459104364913631_7282171119711289344_n.png](https://xentaxbackup.github.io/file/16441_66143641_459104364913631_7282171119711289344_n.png)
## Post #42
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-08T17:14:01+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from usabdt ↑Tue Jul 09, 2019 1:08 am at Tue Jul 09, 2019 1:08 am
>
> 
But I have an error, please help me
Yes, the reason being it was made in 2016 

Try out some of the more up to date scripts on xentax. Online game formats go through small changes over time, so anything old would probably not work.
## Post #43
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2019-07-08T18:23:26+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from akderebur ↑Tue Jul 09, 2019 1:14 am at Tue Jul 09, 2019 1:14 am
>
> 
usabdt wrote: ↑Tue Jul 09, 2019 1:08 am
But I have an error, please help me

Yes, the reason being it was made in 2016 

Try out some of the more up to date scripts on xentax. Online game formats go through small changes over time, so anything old would probably not work.

I know the blender script, but there are many files that can't be opened, can you update? for both .srt files in speedtree how to open. I tried with ue4 but couldn't open it
## Post #44
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-25T15:27:51+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

NEW GAME : Valkyrie Anatomia (Android)

Finally had the time to release this plugin. Tested with bunch of skinned models, and it seems to work fine.

Unfortunately I haven't figured out how to get the textures working. So only models atm.
## Post #45
- Username: herrfraulein
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 28, 2019 8:17 am
- Post datetime: 2019-08-28T00:31:12+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

How do I extract textures from Danganronpa: Ultra Despair Girls?
## Post #46
- Username: zgmfx14a
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Oct 19, 2019 8:11 am
- Post datetime: 2019-12-12T03:58:50+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

I have the Digimon Story: CyberSleuth hackers memories file in mvgl format. How can I turn him into a model file?
## Post #47
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-12-12T06:28:08+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from zgmfx14a ↑Thu Dec 12, 2019 11:58 am at Thu Dec 12, 2019 11:58 am
>
> 
How can I turn him into a model file?
I don't remember the files of that game exactly. Mvgl seems like an archive. Maybe try this to extract it : [viewtopic.php?f=10&t=12666](https://forum.xentax.com/viewtopic.php?f=10&t=12666)
## Post #48
- Username: zgmfx14a
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Oct 19, 2019 8:11 am
- Post datetime: 2019-12-12T07:52:15+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

Thank you, but how to use that tool? It's just some code.
## Post #49
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-12-12T08:12:26+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from zgmfx14a ↑Thu Dec 12, 2019 3:52 pm at Thu Dec 12, 2019 3:52 pm
>
> 
Thank you, but how to use that tool? It's just some code.

It is a quickbms script. Search for quickbms on xentax, zenhax or google. There are probably lots of tutorials on how to use it.
## Post #50
- Username: zgmfx14a
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Oct 19, 2019 8:11 am
- Post datetime: 2019-12-17T08:54:34+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

- open input file D:\game\Extract\file\Original file\DSDB.steam.mvgl
- open script D:\game\Extract\quickbms\SMBBForceUnpacker.bms
- set output folder D:\game\Extract\file\Unpack file

offset filesize filename
--------------------------------------

- signature of 4 bytes at offset 0x0000000000000000 doesn't match the one
expected by the script:

this one: "`"
0c 92 8d 60 ...`

expected: "MDB1"
4d 44 42 31 MDB1

- 0 files found in 0 seconds
coverage file 0 0% 4 2682654775 . offset 0000000000000004

Press ENTER or close the window to quit

I used this code to extract the model but failed. Above is the error message. Can you tell me how to extract the Digimon Story Cyber Sleuth Hacker's Memory（PC） model? 
Please help me.
## Post #51
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-09-26T17:55:17+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

any way to fix support for Dawn of Titans?
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1LNXiJyPUShzMJbc4Sc9cxb8XCpEx9Uz9?usp=sharing)
## Post #52
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-09-26T20:26:59+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

> Reply from Tosyk ↑Sun Sep 27, 2020 1:55 am at Sun Sep 27, 2020 1:55 am
>
> 
any way to fix support for Dawn of Titans?
It works fine for me. That nex file you uploaded isn't a nex model. It is a bof file. I don't know how it got that extension. Anyway rename its extension to bof. Then you can load it with UniViewer and export it as nex. Finally use the nex script for loading it in Noesis.
## Post #53
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-09-26T21:49:32+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

thanks for reply! so you tell me that UniViewer will only open bof? why there's bof unpacker then? do I have to use it?
whatever I do it gives me Error loading model

edit: I'm sure is it me. because I've tried several game version and can't load models from any of it. can you explain how to do it?

edit2: the issue was because I had both DLL and ZIP files of same plugin in Plugin directory. when I kept only DLL the models have started to working

edit3: textures doesn't convert properly with latest build of android (v1.39.1). I've checked DOT versions (android). somewhere between 1.3.4 and 1.3.0 devs did something with texture compression. so texture from version 1.3.2 should be convertible. I don't know the exact version but only a date for the build: 2019 july 18. keep in mind it was a year ago, many models could be added since then.
## Post #54
- Username: bongomongo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 28, 2021 6:47 am
- Post datetime: 2021-08-27T22:50:57+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

Hi, I was wondering if you also considered creating a plugin for the models from Ty 1?
## Post #55
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2023-05-16T15:57:33+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

Do anyone figure it out how to Exporting  the  summon night 6  textures.
## Post #56
- Username: Rathian23
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 09, 2023 10:51 pm
- Post datetime: 2023-06-30T11:32:30+00:00
- Post Title: Re: UniViewer - Multiple Games Tool

hi could you make a univiewer can extract some animation from Dawn Of titan
