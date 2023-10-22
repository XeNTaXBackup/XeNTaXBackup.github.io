## Post #1
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2019-02-16T22:56:45+00:00
- Post Title: God Eater 3

GE3's files come in three parts; a pfs, pk, and pkh file.

The PFS file holds all the file name strings and is separated into 3 chunks. The first chunk I haven't quite figured out but has less entries than the total string count but has a size of 0x18 bytes per entry. The second chunk is just a list of offsets that are used by the string table, and the last chunk is the string table itself.

The pk file is just a large collection of zlib files that holds all the games data, pretty self explanatory on that one.

The pkh file holds the offsets to the different zlib files plus some other data i haven't figured out yet. I do know that each entry is again only 0x18 bytes long with the dword at 0x10 being the offset of the zlib file.

I'm hoping someone can figure out how the pkh and pfs are linked so we can get proper file name extraction and eventually repacking for the sake of mods. Since the patch file is small and follows the same structure as the main archive, I have a link to it here. It's only 25 megs.

[https://drive.google.com/open?id=11JzPG ... BjGfZ4oTQ-](https://drive.google.com/open?id=11JzPGhm3QHZxg5W5ujxWoCBjGfZ4oTQ-)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-02-17T01:43:51+00:00
- Post Title: God Eater 3

its most likely related to this
[viewtopic.php?f=10&t=16595](http://forum.xentax.com/viewtopic.php?f=10&t=16595)
## Post #3
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2019-02-17T01:56:01+00:00
- Post Title: God Eater 3

hmm. you are right that they are using similar file setups. The quick bms script even starts to output the file structure. It does seem to get stuck and fail after a while though so the bms will need to be tweaked slightly
## Post #4
- Username: Vuze
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 11, 2018 4:33 am
- Post datetime: 2019-02-17T12:20:06+00:00
- Post Title: God Eater 3

This tool seems to work perfectly (on the patch file at least): [https://github.com/kotcrab/fate-explorer/releases](https://github.com/kotcrab/fate-explorer/releases)

The game doesnt't natively prioritize unpacked files over the packed ones, need to unmount the archive so to speak (aka delete it or move it out of directory), then just place the unpacked files in the correct path relative to the archive root. Allows for modding, verified with quick string edit, 100% traveling merchant appearance rate, modified item shop with all consumables and adjusted inventory item limits.
## Post #5
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2019-02-17T19:10:08+00:00
- Post Title: God Eater 3

when using that tool, i got an error on the archive 0 near the end. About to test archive1



edit: Archive 1 did the same thing 10038/11385 then it crashed with the header error
## Post #6
- Username: jtrainor
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Dec 25, 2006 9:23 am
- Post datetime: 2019-07-05T13:02:37+00:00
- Post Title: God Eater 3

We need an updated tool for God Eater 1.4 if possible.
## Post #7
- Username: jtrainor
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Dec 25, 2006 9:23 am
- Post datetime: 2020-05-19T08:29:49+00:00
- Post Title: God Eater 3

This game has had it's final patch and thus any tool made now will work presumably forever.
## Post #8
- Username: RYUKIxna
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 07, 2019 2:53 pm
- Post datetime: 2020-05-28T04:41:05+00:00
- Post Title: God Eater 3

> Reply from Vuze ↑Sun Feb 17, 2019 8:20 pm at Sun Feb 17, 2019 8:20 pm
>
> 
This tool seems to work perfectly (on the patch file at least): https://github.com/kotcrab/fate-explorer/releases

The game doesnt't natively prioritize unpacked files over the packed ones, need to unmount the archive so to speak (aka delete it or move it out of directory), then just place the unpacked files in the correct path relative to the archive root. Allows for modding, verified with quick string edit, 100% traveling merchant appearance rate, modified item shop with all consumables and adjusted inventory item limits.

The tool seems to be out of date or something. I tried ripping using the latest version of fate-explorer, but the outfolder(which supposedly is where the  extracted files go.) shows folders with the pk file names but they come up empty.
God Eater 3 is currently in v2.51 but should the tool able to extract from this version? I really wanna extract the god arcs so this is a must-know. Thank you in advance.
## Post #9
- Username: pm0del
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 07, 2021 10:08 pm
- Post datetime: 2021-04-07T14:16:24+00:00
- Post Title: God Eater 3

The CRC table has changed.
and there has been an aditional 4-byte-header in pkh file.
I just made an old tool available for GE3 2.5.1
Since this tool compiles easier for me.
[https://github.com/pmodel/GE3-Extractor](https://github.com/pmodel/GE3-Extractor)

But I know nothing about modeling and the .mdl model file.
Shall anyone tells me how to open .mdl file?
## Post #10
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-04-07T17:02:38+00:00
- Post Title: God Eater 3

> Reply from pm0del ↑Wed Apr 07, 2021 10:16 pm at Wed Apr 07, 2021 10:16 pm
>
> 
The CRC table has changed.
and there has been an aditional 4-byte-header in pkh file.
I just made an old tool available for GE3 2.5.1
Since this tool compiles easier for me.
https://github.com/pmodel/GE3-Extractor

But I know nothing about modeling and the .mdl model file.
Shall anyone tells me how to open .mdl file?

Welp... I'll be damned, it works:




noesis.jpg (239.62 KiB) Viewed 403 times



if you want to mess with the models use Noesis (search for the latest version by date):

[http://www.richwhitehouse.com/index.php ... nc_res.php](http://www.richwhitehouse.com/index.php?content=inc_res.php)

with this "plugin":

[viewtopic.php?f=16&t=17834&start=15#p148419](https://forum.xentax.com/viewtopic.php?f=16&t=17834&start=15#p148419)
## Post #11
- Username: canaltecniqueza
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 21, 2021 12:57 am
- Post datetime: 2021-08-30T09:14:48+00:00
- Post Title: God Eater 3

I've been trying for a few weeks to recreate the .pk file after extracting and modifying it, but it doesn't seem like there is a way to recreate the file or am I wrong?
## Post #12
- Username: Zbzb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 26, 2021 12:32 pm
- Post datetime: 2021-10-26T07:12:29+00:00
- Post Title: God Eater 3

Hey, i know this is an old thread and all.

But i want to know how do i properly export edited meshes into .mdl files? There are plugins for blender, but it's mostly used for quake2 and Warcraft, so i don't know if it will work properly...
## Post #13
- Username: Bob7
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 19, 2021 12:29 am
- Post datetime: 2021-11-26T02:38:45+00:00
- Post Title: God Eater 3

> Reply from Zbzb ↑Tue Oct 26, 2021 3:12 pm at Tue Oct 26, 2021 3:12 pm
>
> 
Hey, i know this is an old thread and all.

But i want to know how do i properly export edited meshes into .mdl files? There are plugins for blender, but it's mostly used for quake2 and Warcraft, so i don't know if it will work properly...

All I know is that they use similar files to fate extella link, they both have KPK heaeders instead of MDL5, MDL7 or any other variation I've seen, I don't think there's a way tor ecreate them to be honest.
## Post #14
- Username: ziguzaguma
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 07, 2020 9:25 pm
- Post datetime: 2021-12-06T08:11:13+00:00
- Post Title: God Eater 3

Can someone please post a link to the 3d models of Keith, Claire and Lulu?
I can't wait to get them running in MMD
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-06T09:37:45+00:00
- Post Title: God Eater 3

> Can someone please post a link to the 3d models of Keith, Claire and Lulu?
Asking for assets is forbidden on this forum.
## Post #16
- Username: BiteMeUniverse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 19, 2018 8:59 am
- Post datetime: 2022-07-26T05:09:10+00:00
- Post Title: Re: God Eater 3

A friend is trying to use this, but both his and my windows defender are flagging it as a torjan. Can anyone confirm this works?
## Post #17
- Username: Bob7
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 19, 2021 12:29 am
- Post datetime: 2022-07-31T18:21:33+00:00
- Post Title: Re: God Eater 3

> Reply from BiteMeUniverse ↑Tue Jul 26, 2022 1:09 pm at Tue Jul 26, 2022 1:09 pm
>
> 
A friend is trying to use this, but both his and my windows defender are flagging it as a torjan. Can anyone confirm this works?

The extraction tool? Its a false positive, the tool is safe to use.
## Post #18
- Username: Irnkman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 30, 2021 5:09 am
- Post datetime: 2023-05-25T20:26:14+00:00
- Post Title: Re: God Eater 3

Is it possible to apply animation files (.mtb) to mdl files?
