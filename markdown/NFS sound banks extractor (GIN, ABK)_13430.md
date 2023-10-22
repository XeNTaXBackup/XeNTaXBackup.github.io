## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-17T17:35:12+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

Extractors/decoders for old Need For Speed audiobanks.

GIN files are the same for Most Wanted 2005, Carbon, and other games.
These contain engine acceleration/deceleration.

ABK files now only supported for Most Wanted 2005. Other games will be supported later.
These contain all other sounds/sfx like engine sounds, sirens, traffic, menu, etc

Just drag the file onto the EXE or use command line.
[nfs_snd_decoders.rar](https://xentaxbackup.github.io/file/9873_nfs_snd_decoders.rar)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-10-29T14:43:02+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

Nice work have you ever looked at their package format before the one that is made up of mini chunks?
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-29T15:20:00+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

You mean audio package or something else?
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-10-29T15:24:14+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

Data package which holds like Chunk_geo Chunk_tpk etc
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-29T15:41:42+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

No. Some people just asked me to change sounds. What's the task about those packages?
## Post #6
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2015-11-20T21:18:58+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

> Reply from cra0
>
> Nice work have you ever looked at their package format before the one that is made up of mini chunks?
I'm starting to look at the Hot Pursuit 2 version last week. (Even though I lack the skills to recognize 3d data stored in binary)

Ironically. (or maybe not) the PS2 version uses the same .bin archives, but offsets are ordered differently. And in geometry.bin files, the chunks are laid out different order. (compared to the PC version of Underground 1)

Digging through old threads on (English) NFS fansites atm, to have background material to start from.

add-on: PS2 version of HP2, uses PS2 VAG audio formats. (Stuck with the audio codec for .avi clips though)
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-11-22T03:13:21+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

> Reply from N/A
>
> cra0 wrote:Nice work have you ever looked at their package format before the one that is made up of mini chunks?
I'm starting to look at the Hot Pursuit 2 version last week. (Even though I lack the skills to recognize 3d data stored in binary)

Ironically. (or maybe not) the PS2 version uses the same .bin archives, but offsets are ordered differently. And in geometry.bin files, the chunks are laid out different order. (compared to the PC version of Underground 1)

Digging through old threads on (English) NFS fansites atm, to have background material to start from.

add-on: PS2 version of HP2, uses PS2 VAG audio formats. (Stuck with the audio codec for .avi clips though)

I've been reversing need for speed underground2 not sure if anyone else is interested but I was planning on extracting the entire city which is made up of geometry chunks.
## Post #8
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2015-11-22T21:27:59+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

I'm interested in the findings/documentation. XD (or a generic tool for EAGL-based NFS games.)
I'm not a fan of the Underground sub-series though. (For well, neons, and riced bodykits)

But I see the potential of applying it to say NFS:W as an efficient way of porting the map, instead of driving, ripping, driving, ripping, etc, and port it to another game. (after decompressing the files)

Or patch NFSW to fix the incomplete region, then adding the maps from U1/U2/Undercover. (Essentially finished what the devs left behind), but is low priority for me atm as I want to look at changing or extracting vinyls, which would make porting designs to other games easier, and investigating how many licence plates the client actually has. (instead of those that are loadable)

I could point you a small working group [Here](http://www.nfscars.net/forum/car-editing-discussion/53655-nfs-world-ripping-models-textures-overhaul.html)
If you want to talk about exacting Rockport/Palmont directly from the files. (Don't PM N/A, that's me, & I only rip bodykit stuff I can easily reuse), but the current method is rather... inefficient.

Would be fun to have a tool to port different regions to different EAGL versions though, like having Bayview in NFS:MW, Rockport in NFS:Underground 1, etc

Anyways should we fork discussion to a new thread in the 3D section? (Quick forum search and I don't think any general Black Box specific EAGL 3D thread exists)

Add-on: And I wanted to port the PS2 content from Hot Pursuit 2 to the PC version. (All the .o documentation seems lost though...)
## Post #9
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-11-26T02:36:30+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

Make a new thread and link it here.

My research from a while ago
[https://gist.github.com/cra0kalo/c92c589b9d6e2ee9e9f8](https://gist.github.com/cra0kalo/c92c589b9d6e2ee9e9f8)
## Post #10
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2015-12-07T04:35:49+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

meep: [viewtopic.php?f=16&t=13632](http://forum.xentax.com/viewtopic.php?f=16&t=13632)
Right off the bat, I noticed the archive types are different by 1 byte.
And the offsets are in slightly different places, but other than that, it's working so far.
## Post #11
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-09-14T09:33:02+00:00
- Post Title: NFS sound banks extractor (GIN, ABK)

bumping this topic with new gintool made by The_Unpunished: [https://nfsmods.xyz/mod/3499](https://nfsmods.xyz/mod/3499)

as well as CrabJournal's ABK_Insert: [https://github.com/CrabJournal/ABK_Insert](https://github.com/CrabJournal/ABK_Insert)

both their respective source codes are from id-daemon
