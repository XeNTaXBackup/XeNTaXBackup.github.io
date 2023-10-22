## Post #1
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-09-16T17:19:05+00:00
- Post Title: Modern Warfare Series

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: novemba
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 10, 2011 5:17 am
- Post datetime: 2011-10-17T18:12:45+00:00
- Post Title: Modern Warfare Series

Nice tool! Waiting for inject. Can someone do it?
## Post #3
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-11-13T11:53:51+00:00
- Post Title: Modern Warfare Series

bump for mw3.
## Post #4
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2011-11-14T16:18:04+00:00
- Post Title: Modern Warfare Series

mw2/mw3 uses encryption for .ff files. So without a key no chance to repack (text translate) them
## Post #5
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-11-14T17:21:36+00:00
- Post Title: Modern Warfare Series

I'm not a programmer, how to get/make a key?
## Post #6
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2011-11-14T19:52:34+00:00
- Post Title: Modern Warfare Series

i'm not programmer too. Key is stored (and crypted too) in .exe. And at this time nobody cant extract key, no decrypt algorithm and nobody can't repack .ff's files
## Post #7
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-11-15T00:31:43+00:00
- Post Title: Modern Warfare Series

> Reply from Gagarin
>
> i'm not programmer too. Key is stored (and crypted too) in .exe. And at this time nobody cant extract key, no decrypt algorithm and nobody can't repack .ff's files
You are very wrong.
You can recreate the fast files using the MODTools. All texts are in "raw\english\localizedstrings\" (Files of MODTools).
Translation process:
Example: ac130.str

```
LANG_ENGLISH        "Press ^3[{weapnext}]^7 to cycle through weapons."
```

You can change the text in the quotes, like:

```
LANG_ENGLISH        "Pressione ^3[{weapnext}]^7 para alternar entre as armas."
```

After translation, you need to compile the localizations.
I created a new folder inside CoD4\mods\ and called it translation. In this folder i got a batch script to compile, a zone file to specify the files to get compiled and another batch script to quickly run CoD with my mod.
Compile script: makeMod.bat

```
del mod.ff
copy /Y mod.csv ..\..\zone_source
cd ..\..\bin
rem -compress 
linker_pc.exe -language english -compress -cleanup mod
cd ..\mods\translation\
copy ..\..\zone\english\mod.ff
pause
```

zone file:mod.csv

```
ignore,common
localize,killhouse
localize,menu
localize,messagebox
localize,jeepride
localize,introscreen
localize,game
localize,exe
localize,embassy
localize,marksman
localize,launchfacility_a
localize,launchfacility_b
localize,icbm
localize,hunted
localize,rallypoint
localize,rank
localize,rivertown
localize,sandstorm
localize,school
localize,scoutsniper
localize,null
localize,objectives
localize,village_defend
localize,village_assault
localize,vidsubtitles
localize,starts
localize,armada
```

Localize is the keyword to specify a *.str file, after a comma goes the str filename (as you see, without file extension and path). I added a bunch of the stock localizations above, cause i wanted to test how many assets are possible.
Run script: runModSP.bat

```
cd ..\..\
iw3sp.exe +set developer 1 +set fs_game mods/translation
```

Double-click the makeMod.bat and see the compiler working. When done, a file called mod.ff should be in your mod folder.
Double-click runModSP.bat to launch the game. With the above zone file, CoD crashes immediately, as there are too many localize-assets - max. is 6144. Note, that i did not add all SP *.str files yet but it's already not working.
This is the only problem with this process: localize-assets limit. But this can easily be solved by adaptation of the text.
Enjoy. 


Credits: Sevenz
## Post #8
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2011-11-15T05:10:20+00:00
- Post Title: Modern Warfare Series

lol ?

I'm talking about mw2/mw3. I know about cod4 and modbuilder. But there is different case cause there is no encryption, just zlib archive + header
## Post #9
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-11-15T05:26:50+00:00
- Post Title: Modern Warfare Series

> Reply from Gagarin
>
> lol ?

I'm talking about mw2/mw3. I know about cod4 and modbuilder. But there is different case cause there is no encryption, just zlib archive + header
Sorry, I just read your last comment.
Anyway, I think our friend up there know where to start.
## Post #10
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-11-15T13:33:10+00:00
- Post Title: Modern Warfare Series

I've already translated CoD4.
## Post #11
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-11-17T14:00:54+00:00
- Post Title: Modern Warfare Series

By the way, what about the these ff extractors? Like FFviewer or other programs?
