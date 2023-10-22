## Post #1
- Username: axewendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 10, 2017 10:42 am
- Post datetime: 2017-02-17T06:13:28+00:00
- Post Title: Kingdoms of Amalur?

Sorry if this is in the wrong forum.

I have scoured this forum for any script to open up the big file / extract 3d Models. Not much Luck.
I was able to use Ninja to get some 3d Models but it's a very slow / cumbersome strategy (The models are broken up and need to actually render them in RAM - Thus I need to play through the game...)

I know KoA wasn't great but the art direction was amazing.. Anyone have newer information on this game or can point me in a direction?
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-17T14:19:49+00:00
- Post Title: Kingdoms of Amalur?

A fellow Raptor made an exelent extractor, but unfortunetly his hosting website is down.
Here is backup i found: [http://www.playground.ru/files/kingdoms ... tor-68789/](http://www.playground.ru/files/kingdoms_of_amalur_reckoning_amalur_extractor-68789/)

Files are hashed, I made an app few years back to rename them. All you need is to select symbol_table_%folder name%.bin file , and then select folder in assets directory. Its also texture converter. 
I also had unfinshed import script, model format is simple.
[Big Huge Renamer.zip](https://xentaxbackup.github.io/file/12465_Big Huge Renamer.zip)
## Post #3
- Username: axewendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 10, 2017 10:42 am
- Post datetime: 2017-02-17T14:26:28+00:00
- Post Title: Kingdoms of Amalur?

Yes! Thank you.. I wish we had more backups of the amazing work Raptor did. Amazing find on that backup location.
I will grab those files and report my progress.

As an aside.. some of raptor's files can be still found in the archived version of his utils directory.

[https://web.archive.org/web/*/http://ra ... les/utils/](https://web.archive.org/web/*/http://raptor.cestiny.cz/download/files/utils/)*

Please everyone grab them while you can.. It's not all of them though.
## Post #4
- Username: axewendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 10, 2017 10:42 am
- Post datetime: 2017-02-17T14:55:59+00:00
- Post Title: Kingdoms of Amalur?

> Reply from PredatorCZ
>
> A fellow Raptor made and exelent extractor, but unfortunetly his hosting website is down.
Here is backup i found: http://www.playground.ru/files/kingdoms ... tor-68789/

Files are hashed, I made an app few years back to rename them. All you need is to select bin file with folder name, and then select folder. Its also texture converter. 
I also had unfinshed import script, model format is simple.

Unpacker worked great.. Your renamer get's an OutOfMemory Exception. I could be using it incorrectly?

I noticed all the .DDS files have a header before the 'DDS'.. Wonder what that is for.. but if I delete it they open fine. I'm sure there is a script out there..

Just curious how I can get at the 3d Models..
## Post #5
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-17T15:02:56+00:00
- Post Title: Kingdoms of Amalur?

> Reply from axewendo
>
> Your renamer get's an OutOfMemory Exception. I could be using it incorrectly?

My apologies, you need to load symbol_table_%folder name%.bin file, and then select folder with same name as %folder name% in content/assets folder.

> Reply from axewendo
>
> I'm sure there is a script out there..

Program also converts DDS files, on second tab called "Texture Converter"
## Post #6
- Username: axewendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 10, 2017 10:42 am
- Post datetime: 2017-02-17T17:51:32+00:00
- Post Title: Kingdoms of Amalur?

> Reply from PredatorCZ
>
> 
My apologies, you need to load symbol_table_%folder name%.bin file, and then select folder with same name as %folder name% in content/assets folder.

Ah that worked.. But the file extension is like "terrain_streamable_bin".. 
Do you remember off hand where the statics / meshes are? And what format they should be in?

Thanks for your time - I hope this thread prevents future confusion about this game. 

I will go dig in the other threads to see if this part was answered before.


EDIT:

Also after converting .DDS files using your converter they become unreadable by photoshop.. I think the conversion is doing more then trimming the header..

Was Able to accomplish something similar with:
(Thanks to finale00)

```
#quickbms script

get SIZE asize
math SIZE -= 16
get NAME filename

log NAME 16 SIZE

```
## Post #7
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-17T22:48:57+00:00
- Post Title: Kingdoms of Amalur?

> Reply from axewendo
>
> 
Also after converting .DDS files using your converter they become unreadable by photoshop.. I think the conversion is doing more then trimming the header..
I never used Photoshop, im using XNView, it can view/convert most formats. The conversion only removes first 16 bytes and stores them in .tsph file so they can be converted back.

> Reply from axewendo
>
> 
Do you remember off hand where the statics / meshes are? And what format they should be in?
They are stored in fab folder. fab_xml are metadata file where is stored skeleton, havok collision, and maybye some simple animations. 
.fab_visual_data_streamable_bin are buffers, fairly simple format.


> Reply from axewendo
>
> 
But the file extension is like "terrain_streamable_bin"..

I dont want to even know what these files are, but program should prevent them from loading anyway.
## Post #8
- Username: axewendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 10, 2017 10:42 am
- Post datetime: 2017-02-18T01:47:07+00:00
- Post Title: Kingdoms of Amalur?

> Reply from PredatorCZ
>
> 
They are stored in fab folder. fab_xml are metadata file where is stored skeleton, havok collision, and maybye some simple animations. 
.fab_visual_data_streamable_bin are buffers, fairly simple format.

I have never worked with fab files.. I can't find any plugin or information on this format.. Is there a way to load these .fab_visual_data_streamable_bin in 3DS / Noesis / Blender?

I am trying to google it and the only information I can find is this thread.
## Post #9
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-19T11:53:32+00:00
- Post Title: Kingdoms of Amalur?

> Reply from axewendo
>
> 
I have never worked with fab files.. I can't find any plugin or information on this format.. Is there a way to load these .fab_visual_data_streamable_bin in 3DS / Noesis / Blender?

I am trying to google it and the only information I can find is this thread.

Well, its a short story, there is not any public tool/plugin yet. Those who wrote some, keeps them private, like myself. So no, there is no way to load them into 3ds max, yet. Once I will be satisfied with script, I'll release it to public.

Anyway, anybody can make script/plugin after all, even you, this format is great start point if you want start researching 3d formats.
## Post #10
- Username: axewendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 10, 2017 10:42 am
- Post datetime: 2017-02-19T17:59:12+00:00
- Post Title: Kingdoms of Amalur?

Ah - Well when you do finish it, if your interested in sharing please do post it back in this thread!

Hopefully if this thread indexes well on search engines we can resolve the Kingdom Of Amalur problem for every future person who visits this site.
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-20T01:14:03+00:00
- Post Title: Kingdoms of Amalur?

> Reply from axewendo
>
> Is there a way to load these .fab_visual_data_streamable_bin in 3DS / Noesis / Blender?
i don't see any samples posted to look at
