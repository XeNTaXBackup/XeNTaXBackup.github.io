## Post #1
- Username: carcade
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 08, 2023 3:25 am
- Post datetime: 2023-07-07T20:09:22+00:00
- Post Title: Extracting models and animations from The Warriors (PS2)

Hello!

I want to export models and animations from The Warriors game. I have a ps2 image, and ended up extracting .dat files from WARRIORS.WAD file.
I've also read old topic - [viewtopic.php?p=70249&hilit=the+warriors#p70249](https://forum.xentax.com/viewtopic.php?p=70249&hilit=the+warriors#p70249).

Is there any way to extract models and animations from this .dat files?
## Post #2
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-07-09T02:41:54+00:00
- Post Title: Extracting models and animations from The Warriors (PS2)

I don't remember very well but I think that game was made with Renderware. Upload a few samples to check that.
## Post #3
- Username: carcade
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 08, 2023 3:25 am
- Post datetime: 2023-07-09T12:07:38+00:00
- Post Title: Extracting models and animations from The Warriors (PS2)

roocker666, uploaded some samples, you can use any link.
It's definitely made with RenderWare. In .dat files engine version is 3.7.0.2
As stated in this thread ([viewtopic.php?p=70249&hilit=the+warriors#p70249](https://forum.xentax.com/viewtopic.php?p=70249&hilit=the+warriors#p70249)), if I delete some weird header via hex editor and open the modified .dat file in RWAnalyze app, it recognizes it. But if I use the file as DFF model, it's not imported in blender/3dsmax with DFF import plugin.

[https://drive.google.com/file/d/1wPEOeB ... drive_link](https://drive.google.com/file/d/1wPEOeBBmb8_fqTtFnWjSzykK_hyTL0k7/view?usp=drive_link)
[https://rapidshare.io/1VS2/some_dat_files.zip](https://rapidshare.io/1VS2/some_dat_files.zip)

You can download RWAnalyze app from here - [http://www.steve-m.com/downloads/tools/rwanalyze/](http://www.steve-m.com/downloads/tools/rwanalyze/)
## Post #4
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-07-11T03:44:26+00:00
- Post Title: Extracting models and animations from The Warriors (PS2)

> Reply from carcade ↑Sun Jul 09, 2023 8:07 pm at Sun Jul 09, 2023 8:07 pm
>
> 
roocker666, uploaded some samples, you can use any link...

Yeah, DFF plugin does not work, weird.. Ok, I tried with XBOX version, model format is not Renderware so it is more easy 
Models are inside those packed WAD files, I analyzed "Paks.wad0" and it has A LOT of models. It seems like all models have several clones or copies because I found same textures once and again. I think this is the 1st character in that file:




You can use texture finder to find textures(are DXTs) 



I extracted all the files from those wads but I don't recommend this because you will get like 10,000 files without names, lol
Better use Hex editor on each wad to find models and then use model researcher to extract them.

To find each model you need to search specific bytes in wad files, just let me check that because I am not really sure...
## Post #5
- Username: carcade
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 08, 2023 3:25 am
- Post datetime: 2023-07-11T09:57:36+00:00
- Post Title: Extracting models and animations from The Warriors (PS2)

> Reply from roocker666 ↑Tue Jul 11, 2023 11:44 am at Tue Jul 11, 2023 11:44 am
>
> 
carcade wrote: ↑Sun Jul 09, 2023 8:07 pm
roocker666, uploaded some samples, you can use any link...


Yeah, DFF plugin does not work, weird.. Ok, I tried with XBOX version, model format is not Renderware so it is more easy 
Models are inside those packed WAD files, I analyzed "Paks.wad0" and it has A LOT of models. It seems like all models have several clones or copies because I found same textures once and again. I think this is the 1st character in that file:




You can use texture finder to find textures(are DXTs) 



I extracted all the files from those wads but I don't recommend this because you will get like 10,000 files without names, lol
Better use Hex editor on each wad to find models and then use model researcher to extract them.

To find each model you need to search specific bytes in wad files, just let me check that because I am not really sure...


Thanks for help! I have also tried Xbox version, but can't unpack wad files. Will check with model researcher app when get home.
But why did you say, it's not renderware format? Game is definitely made with renderware engine.
Do you have any idea how to extract character animations too?
## Post #6
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-07-11T19:23:40+00:00
- Post Title: Extracting models and animations from The Warriors (PS2)

> Reply from carcade ↑Sun Jul 09, 2023 8:07 pm at Sun Jul 09, 2023 8:07 pm
>
> 
Thanks for help! I have also tried Xbox version, but can't unpack wad files. Will check with model researcher app when get home.
But why did you say, it's not renderware format? Game is definitely made with renderware engine.
Do you have any idea how to extract character animations too?

Xbox files don't look like RW format:


I can get models with model researcher but without bones so no animations. Probably animations are there too but I am not an expert with animations.
That is all I can do, sorry.
## Post #7
- Username: carcade
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 08, 2023 3:25 am
- Post datetime: 2023-07-11T20:09:59+00:00
- Post Title: Extracting models and animations from The Warriors (PS2)

> Reply from roocker666 ↑Wed Jul 12, 2023 3:23 am at Wed Jul 12, 2023 3:23 am
>
> 
Xbox files don't look like RW format:
I can get models with model researcher but without bones so no animations. Probably animations are there too but I am not an expert with animations.
That is all I can do, sorry.

I really appreciate your help! Thanks!

Can you explain how did you find models with Model Researcher? Did you find some pattern with hex editor before using model researcher?
## Post #8
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-07-11T20:36:33+00:00
- Post Title: Extracting models and animations from The Warriors (PS2)

> Reply from carcade ↑Wed Jul 12, 2023 4:09 am at Wed Jul 12, 2023 4:09 am
>
> 
roocker666 wrote: ↑Wed Jul 12, 2023 3:23 am
Xbox files don't look like RW format:
I can get models with model researcher but without bones so no animations. Probably animations are there too but I am not an expert with animations.
That is all I can do, sorry.


I really appreciate your help! Thanks!

Can you explain how did you find models with Model Researcher? Did you find some pattern with hex editor before using model researcher?

Open wad file in Hex editor and search for these bytes:
01 00 00 00 76 00 00 00 03 00 00 00
then press F3 to find next model header, then F3 again and again.. 

It seems like all models have those bytes in the header, vertices data is after this header, after vertices data there is a big block of unknow data and then faces data. I think texture of the model is at the end of faces data, so it is something like this:

model header
vertices data
unknow data
faces data
Texture

You can use texture finder to see all textures in wad files, that helps to find the offset of each texture. Check all wad files with this tool, some wad files don't have models but Paks.wad0 has like 800 models(like I said, a lot of clones or copies of same models)

That is my process to find model so far, lol. I don't know if all models have those bytes so you need to check that. 

Oh, I did not find vertices or faces count so you need to put random values until you get the complete mesh.
## Post #9
- Username: carcade
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 08, 2023 3:25 am
- Post datetime: 2023-07-11T20:42:24+00:00
- Post Title: Extracting models and animations from The Warriors (PS2)

> Reply from roocker666 ↑Wed Jul 12, 2023 4:36 am at Wed Jul 12, 2023 4:36 am
>
> 
Open wad file in Hex editor and search for these bytes:
01 00 00 00 76 00 00 00 03 00 00 00
then press F3 to find next model header, then F3 again and again.. 

It seems like all models have those bytes in the header, vertices data is after this header, after vertices data there is a big block of unknow data and then faces data. I think texture of the model is at the end of faces data, so it is something like this:

model header
vertices data
unknow data
faces data
Texture

You can use texture finder to see all textures in wad files, that helps to find the offset of each texture. Check all wad files with this tool, some wad files don't have models but Paks.wad0 has like 800 models(like I said, a lot of clones or copies of same models)

That is my process to find model so far, lol. I don't know if all models have those bytes so you need to check that. 

Oh, I did not find vertices or faces count so you need to put random values until you get the complete mesh.

Thanks! That is really helpful information!
