## Post #1
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-02-06T13:03:29+00:00
- Post Title: Queen's Blade MMO

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-06T14:33:49+00:00
- Post Title: Queen's Blade MMO

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-06T21:59:05+00:00
- Post Title: Queen's Blade MMO

Wow her nipple isn't even covered up.
Only korea can get away with this in an MMO.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T02:36:16+00:00
- Post Title: Queen's Blade MMO

Someone want to help figure out skeleton data? I only converted the meshes 



All of the files required at stored in a single folder, so you don't have to go looking for stuff.
Except textures. Those are stored in a separate tex folder for some reason even though each material library references a tex file stored in a local subfolder.

Bones and animation are stored in separate files as well.

So far pretty much everything I parsed is still unknowns.

The header contains a bunch of integers which I don't know what they are for.

Material path names contain korean characters and ascii characters. That causes problems...
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-08T02:43:58+00:00
- Post Title: Queen's Blade MMO

Oh, I missed this topic apparently. Is the animation data compressed? I can have a look if you need, just PM over your script so far or something I guess. Assuming the MMO client is free to download.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T02:54:15+00:00
- Post Title: Queen's Blade MMO

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T22:30:20+00:00
- Post Title: Queen's Blade MMO

Liveplex's other games (Invincible, Dragona) also use the same format. Identical I believe.

Here's a model from Invincible Online.



I've updated the script slightly to do some silly hacks while reading the mat/tex names ...
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-08T23:09:19+00:00
- Post Title: Queen's Blade MMO

> Reply from finale00
>
> Liveplex's other games (Invincible, Dragona) also use the same format. Identical I believe.

Here's a model from Invincible Online.



I've updated the script slightly to do some silly hacks while reading the mat/tex names ...tested in Dragona and not worked.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T23:20:37+00:00
- Post Title: Queen's Blade MMO

Doesn't?

I didn't parse all meshes (only the first), but it shouldn't crash or anything.
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-08T23:31:47+00:00
- Post Title: Queen's Blade MMO

this is what I get when try load format of dragona .mesh

> Detected file type: Dragon Oath
>
> 
>
> Unknown Vert size: 4739
>
> WARNING: Tried to CommitTriangles without even a position buffer bound!
>
> Traceback (most recent call last):
>
>   File "C:\Program Files\Noesis 3.81\plugins\python\fmt_DragonOath_mesh.py", line 24, in noepyLoadModel
>
>     mdl = rapi.rpgConstructModel()
>
> RuntimeError: Failed to construct model from rpgeo context.
>
> Cleaned 8.00MB (in 2 pools).

and ofc I select fmt_queensBlade_mesh.py for load model but in error show load model with script of DragonOath oO
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T23:34:02+00:00
- Post Title: Queen's Blade MMO

Remove the dragon oath plugin.

It's probably the one I wrote that didn't have proper type checking (in fact, you should just delete it completely since I never really worked on it, but I've fixed it by actually doing type-checking. Ogre3D meshes have their "Mesh Serializer" header)

Noesis checks the extension and then runs the type check. If it passes the type check then it'll try to parse it.
A lot of files don't have any unique header that I could use for type checking so those are unfortunate, but most files have idstrings.
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-08T23:40:39+00:00
- Post Title: Queen's Blade MMO

ok thanks for the info, I removed now but anyway still with problems here, not worked.

> Detected file type: Queen's Blade
>
> 8452
>
> Traceback (most recent call last):
>
>   File "C:\Program Files\Noesis 3.81\plugins\python\fmt_queensBlade_mesh.py", line 71, in noepyLoadModel
>
>     load_single_model(data, mdlList)
>
>   File "C:\Program Files\Noesis 3.81\plugins\python\fmt_queensBlade_mesh.py", line 59, in load_single_model
>
>     parser.parse_file()
>
>   File "C:\Program Files\Noesis 3.81\plugins\python\fmt_queensBlade_mesh.py", line 195, in parse_file
>
>     self.parse_vertices(numVerts)
>
>   File "C:\Program Files\Noesis 3.81\plugins\python\fmt_queensBlade_mesh.py", line 160, in parse_vertices
>
>     self.plot_points(numVerts)
>
> AttributeError: 'SanaeParser' object has no attribute 'plot_points'
>
> Cleaned 8.00MB (in 2 pools).
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T23:59:05+00:00
- Post Title: Queen's Blade MMO

Get the latest copy.
I probably left some test code in there.
## Post #14
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-09T00:15:57+00:00
- Post Title: Queen's Blade MMO

> Reply from finale00
>
> Get the latest copy.
I probably left some test code in there.ok now it's worked, thanks a lot finale00, added to queue The Invencible to test soon as possible
## Post #15
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-09T05:48:24+00:00
- Post Title: Queen's Blade MMO

The Invincible Online Monsters, good job finale, grateful for support.
## Post #16
- Username: alton
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 08, 2010 4:26 pm
- Post datetime: 2012-02-15T16:52:57+00:00
- Post Title: Re: Queen's Blade MMO

Thanks For Plugin. but some files not loading Perfectly. 

sorry fool english.
[QBTEST.jpg](https://xentaxbackup.github.io/file/5068_QBTEST.jpg)
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T16:59:41+00:00
- Post Title: Re: Queen's Blade MMO

Yes, I only load one mesh. Haven't looked at how to loop it
## Post #18
- Username: rhaehf2004
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 18, 2011 7:02 pm
- Post datetime: 2012-02-16T15:23:50+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from alton
>
> Thanks For Plugin. but some files not loading Perfectly. 

sorry fool english.

gfpk export How?
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T17:18:37+00:00
- Post Title: Re: Queen's Blade MMO

I've updated the script to load all meshes. It also parses the bone section, which is just a bunch of bone names.
Consider the size of each vertex, there might be indices into these bones. Or not, considering how many 0's there are.

It looks like the material names are defined with the meshes as well, but I still haven't parsed the mtl files properly so some of the textures won't be loaded.
## Post #20
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-16T17:28:47+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from rhaehf2004
>
> alton wrote:Thanks For Plugin. but some files not loading Perfectly. 

sorry fool english.

gfpk export How?here you have bms script of chrox.

```
get files short 
get null short 
filexor "0x73 0x64 0x66 0x61 0x73 0x6C 0x64 0x66 0x6B 0x6A 0x66 0x73 0x6C 0x6B 0x65 0xA4 0xA9 0xA4 0xB8 0xA4 0xA7 0xA4 0xA9 0xA4 0xA9 0xA4 0xA4 0xA4 0xB7 0x73 0x64 0x66 0x21 0x40 0x40 0x23 0x21 0x40 0x46 0x24 0x47 0x67 0x66 0x67 0x64 0x73 0x00" 
for i = 0 < files 
get id long 
putarray 0 i id 
next i 
for i = 0 < files 
get id1 long 
putarray 1 i id1 
next i 
for i = 0 < files 
getarray OFFSET 1 i 
if OFFSET == -1 
getdstring null 0x310 #this is the recursive directory info but we can skip it in this game 
endif 
if OFFSET != -1 
getdstring basename 0xF8 
get SIZE long 
get UNK01 long 
get UNK02 long 
getdstring NULL 0x18 
getdstring NAME 0x1EC 
getdstring basename 0x8 
putarray 2 i SIZE 
putarray 3 i NAME 
endif 
next i 
filexor "" 
savepos base 
for i = 0 < files 
getarray OFFSET 1 i 
getarray SIZE 2 i 
getarray NAME 3 i 
math OFFSET + base 
if NAME != 0 
log NAME OFFSET SIZE 
endif 
next i
```


> Reply from finale00
>
> I've updated the script to load all meshes. It also parses the bone section, which is just a bunch of bone names.
Consider the size of each vertex, there might be indices into these bones. Or not, considering how many 0's there are.

It looks like the material names are defined with the meshes as well, but I still haven't parsed the mtl files properly so some of the textures won't be loaded.

thanks for update man, really good work.
## Post #21
- Username: alton
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 08, 2010 4:26 pm
- Post datetime: 2012-02-17T01:27:41+00:00
- Post Title: Re: Queen's Blade MMO

Thanks for updating Scripit.
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-01T08:40:24+00:00
- Post Title: Re: Queen's Blade MMO

Forgot about this.
It now assigns materials to the correct mesh. For queen's blade anyways.
## Post #23
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-03-01T23:42:56+00:00
- Post Title: Re: Queen's Blade MMO

Its only mi imagination or this its hot models?.
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-02T01:14:25+00:00
- Post Title: Re: Queen's Blade MMO

Actually I guess it uses indices to determine which material is used, rather than by name as I had previously assumed...

[](http://i.imgur.com/JMuwY.jpg) [](http://i.imgur.com/XFna2.jpg)
## Post #25
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-03-02T15:58:49+00:00
- Post Title: Re: Queen's Blade MMO

Very nice! Thanks!
## Post #26
- Username: jangoclone
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:52 am
- Post datetime: 2012-03-14T00:00:21+00:00
- Post Title: Re: Queen's Blade MMO

Sorry to ask, but I can't find any textures, only for the maps, and when I open a mesh file it look like overlap various models, here is an example [](http://imageupload.org/es/file/199861/model.jpg.html)
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-14T00:11:21+00:00
- Post Title: Re: Queen's Blade MMO

At the top of the script there's a variable called MODE that's set to 0 or 1.
If it's set to 1 then all model files in the same folder as the model you chose will be loaded.

The textures are located in an archive called "texture" somewhere else
## Post #28
- Username: jangoclone
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:52 am
- Post datetime: 2012-03-14T00:25:07+00:00
- Post Title: Re: Queen's Blade MMO

Thanks ! ! ! now it worked...
## Post #29
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2012-03-24T10:33:27+00:00
- Post Title: Re: Queen's Blade MMO

For Blender249 importer:
-geometry with uv and vertex weighting(*.mesh)
-bones(*.bone)
-animation(*.ani)
-no materials assign

[http://www.mediafire.com/?bv78e4r59x7rd4f](http://www.mediafire.com/?bv78e4r59x7rd4f)
## Post #30
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-24T11:48:05+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from Szkaradek123
>
> http://www.mediafire.com/#77d7qyjzoufoc
Link is your personal folder
## Post #31
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-03-24T16:12:28+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from dj082502
>
> Szkaradek123 wrote:http://www.mediafire.com/#77d7qyjzoufoc
Link is your personal folderis just a little bug with mediafire I think, second time I open, it worked, here you have.
[Blender249_queens_blade by Szkaradek123.rar](https://xentaxbackup.github.io/file/5225_Blender249_queens_blade by Szkaradek123.rar)
## Post #32
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-24T16:21:58+00:00
- Post Title: Re: Queen's Blade MMO

He fixed the link afterwards.

Anyways, now to view the animations!
I'm curious what kind of animations they have.
## Post #33
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-31T03:22:58+00:00
- Post Title: Re: Queen's Blade MMO

Stupid question: does the armatur have to be displayed like this??

[](http://imageshack.us/photo/my-images/256/armature.jpg/)

Uploaded with [ImageShack.us](http://imageshack.us)

It's a little bit weird.

see ya!!!
## Post #34
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-31T14:19:24+00:00
- Post Title: Re: Queen's Blade MMO

it looks like you have not load up the .bone file. Also you can hide bones if they are to ugly
## Post #35
- Username: rueleonheart
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 17, 2012 7:47 am
- Post datetime: 2012-04-21T03:35:20+00:00
- Post Title: Re: Queen's Blade MMO

Hello guys, when I view the model in Noesis, every mesh has texture in it except for the hair. I placed the meshes and the textures on the same folder.
## Post #36
- Username: rueleonheart
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 17, 2012 7:47 am
- Post datetime: 2012-04-21T17:37:25+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from finale00
>
> He fixed the link afterwards.

Anyways, now to view the animations!
I'm curious what kind of animations they have.

I managed to import the models, texture, and an animation in blender. Here's a sample of one of the animations.

[http://www.youtube.com/watch?v=yN0ZgfBLYXI](http://www.youtube.com/watch?v=yN0ZgfBLYXI)
## Post #37
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-21T19:45:59+00:00
- Post Title: Re: Queen's Blade MMO

lol awesome.
## Post #38
- Username: cenjianneng
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 02, 2011 2:58 am
- Post datetime: 2012-04-28T19:25:08+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from jangoclone
>
> Thanks ! ! ! now it worked...

i can extract *.ani *.mesh *.bone files，but I can't find any dds files
where is dds files?
client is CBT2,  CBT1 client download link was fail.....

sorry for my bad english!
## Post #39
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-28T23:08:35+00:00
- Post Title: Re: Queen's Blade MMO

There should be a separate texture archive
## Post #40
- Username: cenjianneng
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 02, 2011 2:58 am
- Post datetime: 2012-04-29T03:51:01+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from finale00
>
> There should be a separate texture archive

*:\QueensBlade\Data\Map
in this folder, extract gfkp files have dds files

*:\QueensBlade\Data\Objects\NPC
*:\QueensBlade\Data\Objects\PC
in this folder, extract gfkp files have not dds files??
## Post #41
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-29T04:04:26+00:00
- Post Title: Re: Queen's Blade MMO

Then extract the texture gfpk.

Or maybe they moved it somewhere else?
## Post #42
- Username: cenjianneng
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 02, 2011 2:58 am
- Post datetime: 2012-05-03T09:52:50+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from finale00
>
> Then extract the texture gfpk.

Or maybe they moved it somewhere else?

maybe is CBT2 client problem...i was extract all gfpk files

example:
\ta\Objects\PC\DE\BD\DE_BD_N_06.mesh

open "DE_BD_N_06.mtl" then found "de_bd_n_06.dds" use for this mesh
and search "de_bd_n_06.dds" in the "ta" folder
but no result

here is CBT2 client 
[http://queens.zcdn.co.kr/queens/Client/ ... meclub.exe](http://queens.zcdn.co.kr/queens/Client/QueensClientSetup-CBT-Gameclub.exe)

you can try it
## Post #43
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-05-03T21:20:44+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from finale00
>
> 
here is CBT2 client 
http://queens.zcdn.co.kr/queens/Client/ ... meclub.exe

AFAIK this is the old client, the current one is v2 and is nearly 2 GB in size (the one above is 1.4 GB), unless they have released a newer version lately.

Can anyone confirm that?
## Post #44
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-05-04T04:54:42+00:00
- Post Title: Re: Queen's Blade MMO

So there isn't a folder called "tex" anymore in PC or NPC? lol
## Post #45
- Username: cenjianneng
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 02, 2011 2:58 am
- Post datetime: 2012-05-04T07:46:22+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from finale00
>
> So there isn't a folder called "tex" anymore in PC or NPC? lol

solved....when i reinstall client

it work now!
## Post #46
- Username: Kenoo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 03, 2011 3:31 am
- Post datetime: 2012-08-06T14:09:00+00:00
- Post Title: Re: Queen's Blade MMO

Sorry for reviving this, but i managed to extract all the files i need, but how do i extract .ani files?
i cant seem to find out how
## Post #47
- Username: ridgeracer
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 12:10 am
- Post datetime: 2012-08-21T19:32:22+00:00
- Post Title: Re: Queen's Blade MMO

anybody have the client? 

i can't find a download for it anywhere.
## Post #48
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2012-09-06T19:49:53+00:00
- Post Title: Re: Queen's Blade MMO

Two items (Dragona related, but I believe that may apply here since the models are the same):

1) When trying to load big meshes (above 1mb), Noesis hangs. It stays "loading..." the mesh and you have to kill it from the task manager (seems like an infinite loop or something like that).

2) Question: It is possible to view the animations from inside Noesis?
## Post #49
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-06T19:59:48+00:00
- Post Title: Re: Queen's Blade MMO

I never finished the script to add bones or animations.
## Post #50
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2012-09-06T20:05:32+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from finale00
>
> I never finished the script to add bones or animations.

Ah, ok... I peeked into the script to see if I was missing something and couldn't find anything... now I know why   

What about the hanging? It is possible that there is an infinite loop somewhere? Or it is just that the model is too big for the script to handle it?
## Post #51
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-06T20:47:52+00:00
- Post Title: Re: Queen's Blade MMO

Send me the file.
I don't have any while loops or jumping to specific offsets in the file (that the script might loop on) so it probably is a different issue.
## Post #52
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2012-09-06T20:55:34+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from finale00
>
> Send me the file.
I don't have any while loops or jumping to specific offsets in the file (that the script might loop on) so it probably is a different issue.

Sent via PM...
## Post #53
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2012-09-29T14:14:57+00:00
- Post Title: Re: Queen's Blade MMO

Bump :p

What is the Blender version used for the .mesh/.bone/.ani importer?
I tried 1.49, but blender didn't import anything   
It's for the game Dragona ^^
Thank you
## Post #54
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2012-10-09T07:08:52+00:00
- Post Title: Re: Queen's Blade MMO

JALB
Just Another Little Bump
## Post #55
- Username: gotoho
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 14, 2012 3:59 pm
- Post datetime: 2012-10-11T15:16:05+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from illian
>
> Bump :p

What is the Blender version used for the .mesh/.bone/.ani importer?
I tried 1.49, but blender didn't import anything   
It's for the game Dragona ^^
Thank you

For QB, could import mesh, bone and ani to Blender 2.49 using Szkaradek123's script
but no texture/material
## Post #56
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2012-10-12T23:14:22+00:00
- Post Title: Re: Queen's Blade MMO

I'm already using it ^^'
So I guess that ths importer don't work with Dragona 3D files
## Post #57
- Username: gotoho
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 14, 2012 3:59 pm
- Post datetime: 2012-10-13T13:43:53+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from illian
>
> I'm already using it ^^'
So I guess that ths importer don't work with Dragona 3D files

tried one model called aoi sola and looks good

sorry to all contributors, I am only an unskillful viewer 
waiting QB models be textured


------few hours update------
I was stupid, I just pick the dds into uv then it is done 
[untitled.jpg](https://xentaxbackup.github.io/file/5897_untitled.jpg)
## Post #58
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2012-10-14T18:36:23+00:00
- Post Title: Re: Queen's Blade MMO

I'll try again 
Blender 2.49, 2.49a or 2.49b?
## Post #59
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2012-10-25T21:06:36+00:00
- Post Title: Re: Queen's Blade MMO

Bump, the models from the game Dragona doesn't work, etheir they are in the same format than Queen's Blade
## Post #60
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-14T00:59:08+00:00
- Post Title: Re: Queen's Blade MMO

Can anyone figure out how the materials are assigned for the map files?

Samples: [http://www.mediafire.com/?wciv6np7drswddq](http://www.mediafire.com/?wciv6np7drswddq)

When I loaded the model with textures it was all wrong. the UV's are fine it's just I assigned the wrong material. Each mesh has a material name, and each material in the .mtl file also has a unique name, so I figured there was a one-to-one correspondence.

I haven't checked the .xmtl file but it probably isn't important.

Here is the plugin for the .map files: [http://db.tt/JHhJ10LH](http://db.tt/JHhJ10LH)
## Post #61
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2013-02-14T09:31:05+00:00
- Post Title: Re: Queen's Blade MMO

I'm here  

Edit: After some research in the tex/mtl files and folders, I guess that the materials are stored in the .mtl, and applied to the model by the .xmtl
## Post #62
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-14T16:19:06+00:00
- Post Title: Re: Queen's Blade MMO

Oh, maybe that's what it is for.
I wasn't really sure what the xmtl was for just thought it was redundant data LOL
## Post #63
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-18T03:11:39+00:00
- Post Title: Re: Queen's Blade MMO

Ok so I parsed the xmtl file instead of the mtl file and seem to have gotten somewhere
Doesn't work for most of the files though, so there's probably something else to it lol

I probably have to figure out how the mtl and xmtl are related.
Hopefully I don't have to parse the tmxlib files. They store information about materials but...ehhh too much work.

The script has been updated.
## Post #64
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2013-03-26T10:06:25+00:00
- Post Title: Re: Queen's Blade MMO

BMS don't open OBT gfpk!
Example [http://www.mediafire.com/?k78rzj2au2jk1pf](http://www.mediafire.com/?k78rzj2au2jk1pf)
## Post #65
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-26T10:34:04+00:00
- Post Title: Re: Queen's Blade MMO

extracts fine for me.
[viewtopic.php?f=16&t=8202&start=19](http://forum.xentax.com/viewtopic.php?f=16&t=8202&start=19)
## Post #66
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2013-03-26T11:32:55+00:00
- Post Title: Re: Queen's Blade MMO

Don't work
## Post #67
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-26T12:00:32+00:00
- Post Title: Re: Queen's Blade MMO

I just extracted the file you posted with the script you are doing something wrong.
open a command prompt and do this

c:\quickbms.exe c:\qb.bms c:\file.dat c:\extracted

and the files will be extracted you might want to re create the bms file I have a feeling you are using the wrong one.
## Post #68
- Username: dcurbow
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 18, 2010 10:57 am
- Post datetime: 2013-12-10T13:42:59+00:00
- Post Title: Re: Queen's Blade MMO

HI all, back from long sabbatical, IE. building a new house. Just finished unpacking and got step up again with the computer. Sadly after 2years offline I get back and  find scarlet blade start trying to work on it. But files don't unpack right, names lost, and I have found no way to get the Korean Queens Blade files to work with instead. Anyone able to help me here, I can send blank dvd disks to someone who has with return mailing box if they could burn the Korean Queens Blade files for me. Or if anyone has figured out how to unpack the scarlet blade files.
## Post #69
- Username: s25jin
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 15, 2011 1:11 am
- Post datetime: 2015-10-08T20:02:29+00:00
- Post Title: Re: Queen's Blade MMO

Do you know how to resolve such a problem ?
## Post #70
- Username: buggyflaxi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 21, 2017 12:45 pm
- Post datetime: 2018-06-24T04:41:15+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from CriticalError
>
> dj082502 wrote:Szkaradek123 wrote:http://www.mediafire.com/#77d7qyjzoufoc
Link is your personal folderis just a little bug with mediafire I think, second time I open, it worked, here you have.

Hi, guys I need some help I am a newbie in blender/ python actually in all this kind of cryptring/extracting stuff but so far I managed to get the meshes/tex evven import them to blender redo UV/maping, beside this I am working on restoring the shaders as in game.

I tried to use the importer to get the .ani / bone files added no success I added the missing "()" as I am using Blender 2.79b
it shows install successful for add-on but no import for .mesh / .ani . bone show under import sub menu.

is it only for 2.49?

Also is there a way to import .amo file since they have some bone info on them.

Thanks in advance
## Post #71
- Username: buggyflaxi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 21, 2017 12:45 pm
- Post datetime: 2018-06-24T04:43:32+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from s25jin
>
> 
Do you know how to resolve such a problem ?

Put all the files related to a model / meshe together in cluding teh .mtl / xmtl / tmlib and dds
## Post #72
- Username: Diol
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 05, 2017 6:37 am
- Post datetime: 2022-02-06T02:41:35+00:00
- Post Title: Re: Queen's Blade MMO

Hello! I was trying to open the .ani files inside blender 2.49

I open blender, I open "Blender249_queens_blade by Szkaradek123" file, I run the script and open a .mesh file, then I try to run the script again and import an .ani file, and the model just breaks, it animates, but it's broken.
I'm definetly doing something wrong, besides, I can only import 1 .mesh and I can't find the where .bone is located.

Help please!
## Post #73
- Username: throwaway003
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 14, 2022 1:54 pm
- Post datetime: 2022-11-02T21:35:33+00:00
- Post Title: Re: Queen's Blade MMO

Is it possible to export a mesh from blender 2.49 as the game's custom .mesh file? I've been able to mod textures and reinject them, but they use a common .dds format whereas I don't know of any program that can export the .mesh. Thanks!
## Post #74
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-03T04:55:33+00:00
- Post Title: Re: Queen's Blade MMO

> Reply from throwaway003 ↑Thu Nov 03, 2022 5:35 am at Thu Nov 03, 2022 5:35 am
>
> 
Is it possible to export a mesh from blender 2.49 as the game's custom .mesh file? [...] whereas I don't know of any program that can export the .mesh. Thanks!A tedious task to accomplish (as with any convert_to_some3D_format exporter). I'd be surprised if anyone tried. Especially when it comes to skeletons included:
.



Queensblade-mesh.jpg (194.57 KiB) Viewed 52 times
