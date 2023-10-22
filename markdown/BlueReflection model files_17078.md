## Post #1
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-09-28T12:36:17+00:00
- Post Title: BlueReflection model files

Steam 
[http://store.steampowered.com/app/65826 ... EFLECTION/](http://store.steampowered.com/app/658260/BLUE_REFLECTION__BLUE_REFLECTION/)


These samples may contain models, can anyone help?

".elixir.gz" samples(pc ver.) 
[https://drive.google.com/file/d/0B_EOJK ... sp=sharing](https://drive.google.com/file/d/0B_EOJKLZ9WswVlRLZ3FFcXhCdmc/view?usp=sharing)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-28T21:54:04+00:00
- Post Title: BlueReflection model files

this bms script will decompress your .gz samples  

```

comtype zlib_noerror
get NAME basename
do
	get ZSIZE long
	savepos OFFSET
	append
	clog NAME OFFSET ZSIZE ZSIZE
	append
	math OFFSET + ZSIZE
	goto OFFSET
while ZSIZE != 0

```


edit
first submesh in pc00_scl.elixir  



pc00_scl_elixir.png (34.35 KiB) Viewed 1294 times
## Post #3
- Username: rauldj
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 12, 2017 7:39 pm
- Post datetime: 2017-09-29T11:23:27+00:00
- Post Title: BlueReflection model files

Is there a way to extract the .elixir files? It seems that PS3 tools to do that do not work here.
## Post #4
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2017-09-29T19:22:06+00:00
- Post Title: BlueReflection model files

> Reply from rauldj
>
> Is there a way to extract the .elixir files? It seems that PS3 tools to do that do not work here.
[Here's](https://www.dropbox.com/s/6o7q7zxqb20kveq/BlueReflection.bms?dl=0) an all in one extractor for the original gz files. Currently working on a maxscript to import the g1m files.
## Post #5
- Username: rauldj
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 12, 2017 7:39 pm
- Post datetime: 2017-09-29T20:29:39+00:00
- Post Title: BlueReflection model files

> Reply from killercracker
>
> Here's an all in one extractor for the original gz files. Currently working on a maxscript to import the g1m files.

Nice, thank you very much, you're the best!

I'm trying to extract models from Atelier Sophie PC but now it seems that the Dinasty Warriors 7 script for 3ds Max to open the .g1m files doesn't work with these , so hopefully your script will be able to overcome it .
## Post #6
- Username: kayaha
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 09, 2017 11:15 pm
- Post datetime: 2017-10-01T04:05:23+00:00
- Post Title: BlueReflection model files

killercracker's bms script is working perfectly. Thanks killercracker.
However blue reflection g1m file could not be imported with maxscript for DW 7.
([https://forum.xentax.com/viewtopic.php?f=16&t=6252](https://forum.xentax.com/viewtopic.php?f=16&t=6252))
3dsmax said the same thing as the image of rauldj

Is there another maxscript that can import g1m?
## Post #7
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-10-04T22:11:37+00:00
- Post Title: BlueReflection model files

> Reply from killercracker
>
> rauldj wrote:Is there a way to extract the .elixir files? It seems that PS3 tools to do that do not work here.
Here's an all in one extractor for the original gz files. Currently working on a maxscript to import the g1m files.

Thanks for the extractor. I used it to help figure out a few costumes for some model swaps (super easy, just copy/paste and renaming files). 

How's work on the maxscript going?
## Post #8
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2017-10-05T02:36:41+00:00
- Post Title: BlueReflection model files

> Reply from ssringo
>
> killercracker wrote:rauldj wrote:Is there a way to extract the .elixir files? It seems that PS3 tools to do that do not work here.
Here's an all in one extractor for the original gz files. Currently working on a maxscript to import the g1m files.

Thanks for the extractor. I used it to help figure out a few costumes for some model swaps (super easy, just copy/paste and renaming files). 

How's work on the maxscript going?

I stopped working on it after I remembered that issue with g1m files needing extra work done to render cloths of other materials alike correctly. You can use [Steven's Gas Machine](http://xnalara.org/viewtopic.php?f=17&t=1001&sid=ed244bc969c0df4de6990c93fabafbb3) to load the models correctly though, they'll have no skeleton. Just select [PC] Dragon Quest Heroes Slime Edition as the game and hit ok when the process g1m files prompt comes up.
## Post #9
- Username: rauldj
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 12, 2017 7:39 pm
- Post datetime: 2017-10-05T11:45:16+00:00
- Post Title: BlueReflection model files

> Reply from killercracker
>
> I stopped working on it after I remembered that issue with g1m files needing extra work done to render cloths of other materials alike correctly. You can use Steven's Gas Machine to load the models correctly though, they'll have no skeleton. Just select [PC] Dragon Quest Heroes Slime Edition as the game and hit ok when the process g1m files prompt comes up.

Well, too bad. Thanks for your extractor and for guiding us to use that other software though!
## Post #10
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-10-06T12:56:27+00:00
- Post Title: BlueReflection model files

> Reply from killercracker
>
> 
I stopped working on it after I remembered that issue with g1m files needing extra work done to render cloths of other materials alike correctly. You can use Steven's Gas Machine to load the models correctly though, they'll have no skeleton. Just select [PC] Dragon Quest Heroes Slime Edition as the game and hit ok when the process g1m files prompt comes up.
Not all physical mesh is like a "piece", some of them still can be used.
Ingore this problem, can your "Unfinished Script" import the g1m file with bones ?
I mean other meshs.
## Post #11
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-06T14:01:55+00:00
- Post Title: BlueReflection model files

Steven's Gas Machine can get the models with bones and weights just fine. The only problem is some of the physic parts at the moment, which export as flat meshes. He said he's looking into it, so i think sooner or later it will be possible to get those parts too  Load the .smc files with the included script into Blender 2.49b (*_skel_00.smc first) and enable vertex groups in the armature modifier in Blender.
## Post #12
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-10-06T15:06:38+00:00
- Post Title: BlueReflection model files

> Reply from o0Crofty0o
>
> Steven's Gas Machine can get the models with bones and weights just fine. The only problem is some of the physic parts at the moment, which export as flat meshes. He said he's looking into it, so i think sooner or later it will be possible to get those parts too  Load the .smc files with the included script into Blender 2.49b (*_skel_00.smc first) and enable vertex groups in the armature modifier in Blender.

Maybe i should study Blender first, thx.
## Post #13
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-10-16T23:49:05+00:00
- Post Title: BlueReflection model files

Nvm lol
