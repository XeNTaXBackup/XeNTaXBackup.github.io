## Post #1
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2015-08-02T17:16:12+00:00
- Post Title: King's Quest (2015)

Hi,
a new game from [King's Quest](http://store.steampowered.com/app/385721/) franchise has been released (on Unreal Engine 3) thanks to The Odd Gentlemen and Sierra Entertainment.

Game's scripts are located in GrahamsGame\Localization\INT folder and can be easily edited in any text editor .

Here're my problems:

1. Textures are located in GrahamsGame\CookedPC folder in one file called "Textures.tfc". How can I get into this file to unpack it, edit textures and rebuild it?

2. Where are the fonts located and how can I rebuild them? (most files in the game are .u, .BIN, .upk, .tfc and .umap).

Here's a link to Textures.tfc
[https://mega.nz/#!j55VUZyC!NduGqAO3HR-g ... RpI4lIer9g](https://mega.nz/#!j55VUZyC!NduGqAO3HR-gj84q2z1wT-GrcgolpUDPaRpI4lIer9g)
## Post #2
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2015-08-04T11:48:32+00:00
- Post Title: King's Quest (2015)

Game's scripts are located in "GrahamsGame\Localization\INT" folder but if you edit them, nothing change in-game (except for menu texts).
I think that real scripts are inside "GrahamsGame\CookedPC" folder, under .upk format, so we have the same problem, 'cause I'd like to editing subtitles, but I can't re-pack the modified .upk.
## Post #3
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2015-08-04T12:09:04+00:00
- Post Title: King's Quest (2015)

> Reply from Crybio
>
> Game's scripts are located in "GrahamsGame\Localization\INT" folder but if you edit them, nothing change in-game (except for menu texts).
I think that real scripts are inside "GrahamsGame\CookedPC" folder, under .upk format, so we have the same problem, 'cause I'd like to editing subtitles, but I can't re-pack the modified .upk.

Yes, I've just noticed that - nothing changes expect for menu). Does anyone know where are the texts located? As Cyrbio said, they might be under .upk files, but which one and how can I open them?
## Post #4
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2015-08-04T14:32:11+00:00
- Post Title: King's Quest (2015)

> Reply from Saturno
>
> Crybio wrote:Game's scripts are located in "GrahamsGame\Localization\INT" folder but if you edit them, nothing change in-game (except for menu texts).
I think that real scripts are inside "GrahamsGame\CookedPC" folder, under .upk format, so we have the same problem, 'cause I'd like to editing subtitles, but I can't re-pack the modified .upk.  

Yes, I've just noticed that - nothing changes expect for menu). Does anyone know where are the texts located? As Cyrbio said, they might be under .upk files, but which one and how can I open them?

The texts are inside "...\Steam\steamapps\common\King's Quest\GrahamsGame\CookedPC\Maps\E1" folder.

There are 98 "_LOC_INT.upk" files.

1 - extract the content of these .upk files with this [decompress tool](http://www.mediafire.com/download/ccdutd1p4p29872/1_decompress.rar). The result is a new .upk file with the same name of the previous file.

2 - with the [unpack tool](http://www.mediafire.com/download/r7y62yk56a659bq/2_unpack-repack.rar) you can unpack the new .upk file and find the texts inside SoundNodeWave files.

Now here's the problem. We have to EDIT this SoundNodeWave files and repack them in useful .upk files!
## Post #5
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2015-08-04T15:37:35+00:00
- Post Title: King's Quest (2015)

I managed to unpack and repack one file. If I change only one letter in a text, I can see it appearing in the game. But when I edit the whole sentence, the game crashes. I suspect that a text line has to be the same length as original. How to solve it?
## Post #6
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2015-08-04T16:32:29+00:00
- Post Title: King's Quest (2015)

> Reply from Saturno
>
> I managed to unpack and repack one file. If I change only one letter in a text, I can see it appearing in the game. But when I edit the whole sentence, the game crashes. I suspect that a text line has to be the same length as original. How to solve it?

What program did you use for SoundNodeWave editing? Did you replace the original .upk with the repacked one made with the second tool, right?
## Post #7
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2015-08-04T16:48:56+00:00
- Post Title: King's Quest (2015)

> Reply from Crybio
>
> What program did you use for SoundNodeWave editing? Did you replace the original .upk with the repacked one made with the second tool, right?

I used UPKunpack to unpack .upk file. I edited .SoundNodeWave file (with text in it) with Notepad++ and then repacked it with UPKrepack. Unfortunately, game crashes when I write sentences longer than original text. As you said, an editor or something to .SoundNodeWave files is needed.
## Post #8
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2015-08-04T21:50:13+00:00
- Post Title: King's Quest (2015)

> Reply from Saturno
>
> Crybio wrote:What program did you use for SoundNodeWave editing? Did you replace the original .upk with the repacked one made with the second tool, right?

I used UPKunpack to unpack .upk file. I edited .SoundNodeWave file (with text in it) with Notepad++ and then repacked it with UPKrepack. Unfortunately, game crashes when I write sentences longer than original text. As you said, an editor or something to .SoundNodeWave files is needed. 
Try this: [https://yadi.sk/d/ZT6nFEzniGqK5](https://yadi.sk/d/ZT6nFEzniGqK5) Tool by swuforce
## Post #9
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2015-08-05T09:33:41+00:00
- Post Title: King's Quest (2015)

> Reply from makcar
>
> Try this: https://yadi.sk/d/ZT6nFEzniGqK5 Tool by swuforce

Wow, many thanks for and swuforce. I checked it and it works just fine . Thank you, guys, really. I wouldn't suspect that someone was working on King's quest editor .

Now, I need to find out how to unpack "Textures.tfc" (or other files with textures), edit them and then repack. I also wonder how to edit fonts as they seem to be all over the place in .upk files.
## Post #10
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2015-08-05T10:21:53+00:00
- Post Title: King's Quest (2015)

Subtitles - GrahamsGame\CookedPC\Startup_LOC_INT.upk\gppfonts\Acadami\ (Texture font)
Menu etc - GrahamsGame\CookedPC\Maps\EpisodeSelector.umap (Flash fonts)
                GrahamsGame\CookedPC\Maps\Startup.upk (Flash fonts)
## Post #11
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2015-08-05T11:37:00+00:00
- Post Title: King's Quest (2015)

> Reply from Saturno
>
> makcar wrote:Try this: https://yadi.sk/d/ZT6nFEzniGqK5 Tool by swuforce

Wow, many thanks for and swuforce. I checked it and it works just fine . Thank you, guys, really. I wouldn't suspect that someone was working on King's quest editor .

Now, I need to find out how to unpack "Textures.tfc" (or other files with textures), edit them and then repack. I also wonder how to edit fonts as they seem to be all over the place in .upk files.

Thanks a lot swuforce and makcar!
## Post #12
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2015-08-05T17:33:02+00:00
- Post Title: King's Quest (2015)

Thank you .
But do you know how to unpack "Textures.tfc?
## Post #13
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2015-08-29T11:08:41+00:00
- Post Title: King's Quest (2015)

any idea how SoundNodeWave i have try [viewtopic.php?f=17&t=12380&p=109166#p109166](http://forum.xentax.com/viewtopic.php?f=17&t=12380&p=109166#p109166)
