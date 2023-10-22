## Post #1
- Username: Omission7x
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Nov 15, 2014 4:15 pm
- Post datetime: 2014-11-15T08:38:25+00:00
- Post Title: Final Fantasy XIII PC Modding.

Is there any way to enhance the models to be like the ones found in pre-rendered movies? Or possibly model swap the characters, has there been any success to this?
## Post #2
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2014-11-15T13:15:01+00:00
- Post Title: Final Fantasy XIII PC Modding.

No not really.

We can extract the big archives, but so far no one bothered to reverse the PC formats, which for the most part are slightly scrambled versions of the console counterparts.
It is possible to force the game to use the high-poly model, but they seem to have different skeleton setup than normal ingame ones, thus in normal gameplay they look like an abomination.

And since we can neither fix existing model nor re-rig and re-import high-poly one, the mod potential is zero.

Which is a damn shame, because original XIII series were reversed almost entirely, but it had no real application besides ripping stuff.
Now that we could mod things, nobody feels like doing it because it's an old game.

Additionally i think we can also say thank you to Square for being mod friendly as always. Most of the visible work they spent on PC version was making sure that we don't get mods too soon (if ever).
## Post #3
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-11-15T18:10:07+00:00
- Post Title: Final Fantasy XIII PC Modding.

Forget that. Has anyone found a way to add .mp4 compressed files to the PC game? Because the PS3 PAMF are far superior to quality then the garbage Square gave in the PC release
## Post #4
- Username: Omission7x
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Nov 15, 2014 4:15 pm
- Post datetime: 2014-11-15T20:01:08+00:00
- Post Title: Final Fantasy XIII PC Modding.

> Reply from SkacikPL
>
> No not really.

We can extract the big archives, but so far no one bothered to reverse the PC formats, which for the most part are slightly scrambled versions of the console counterparts.
It is possible to force the game to use the high-poly model, but they seem to have different skeleton setup than normal ingame ones, thus in normal gameplay they look like an abomination.

And since we can neither fix existing model nor re-rig and re-import high-poly one, the mod potential is zero.

Which is a damn shame, because original XIII series were reversed almost entirely, but it had no real application besides ripping stuff.
Now that we could mod things, nobody feels like doing it because it's an old game.

Additionally i think we can also say thank you to Square for being mod friendly as always. Most of the visible work they spent on PC version was making sure that we don't get mods too soon (if ever).

I see, that sucks. well any mod is worth trying for this game. custom music or the inclusion of better quality movies would also work for me. Are there any tools that can read the internal file formats of this game yet?
## Post #5
- Username: Omission7x
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Nov 15, 2014 4:15 pm
- Post datetime: 2014-11-16T20:56:23+00:00
- Post Title: Final Fantasy XIII PC Modding.

Some of the high resolution models do appear rendered in game such as Cid and Serah.




It's sad to know that these models can't be unlocked for game play, without having re-rig them.
## Post #6
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-11-22T14:18:18+00:00
- Post Title: Final Fantasy XIII PC Modding.

Does anyone know where PS3 button textures would be?
## Post #7
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2014-11-23T03:30:37+00:00
- Post Title: Final Fantasy XIII PC Modding.

It seems like those miscellaneous textures were xgr or xfv files in the /vfx directory.
I might have made a Noesis plugin - I'll have to find it.

I used the extraction tool here: [https://steamcommunity.com/app/292120/d ... 277998633/](https://steamcommunity.com/app/292120/discussions/0/613939294277998633/)
and then tried Noesis on one of the models and it crashed. The strange thing is, my Autodesk importers still work just fine. [https://onedrive.live.com/redir?resid=5 ... DBF2%21521](https://onedrive.live.com/redir?resid=5563CAB21EADBF2%21521)
## Post #8
- Username: Omission7x
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Nov 15, 2014 4:15 pm
- Post datetime: 2014-11-23T19:57:10+00:00
- Post Title: Final Fantasy XIII PC Modding.

FFXIII crystal tools engine natively supports Autodesk Maya i believe, as one part of their slides shows.




Is it possible to write unpacking and repacking plugins or middle tools for that program instead?
## Post #9
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-12-03T04:34:50+00:00
- Post Title: Final Fantasy XIII PC Modding.

Regarding videos someone from Gamefaqs found the offsets to replace the pre-rendered scenes on PC.


[http://www.gamefaqs.com/boards/846192-f ... i/70394566](http://www.gamefaqs.com/boards/846192-final-fantasy-xiii/70394566)

Only issue is the PC version can't read H.264 files and only Bink 1 & 2. this is because it's using the Bink library for reading videos files. I really wish square used libavcodec or any open source mp4 library, but whatever we can mod I guess.

If someone could theoretically get libavcodec libraries to run alongside this game I bet we can use the PS3 files directly since libavcodec can read both h.264 and aa3 encoded video/audio respectively (well not directly still got to put it in mp4 container )
## Post #10
- Username: Omission7x
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Nov 15, 2014 4:15 pm
- Post datetime: 2014-12-09T06:10:35+00:00
- Post Title: Final Fantasy XIII PC Modding.

That's great news, unfortunately I don't have access to the ps3 version. I support this though. We could also try asking square if they could make FFXIII 30 gbs with original quality movies, and allow us to download the jappanies movies optional. As part of their next update. Just a thought.
## Post #11
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2014-12-12T07:59:49+00:00
- Post Title: Final Fantasy XIII PC Modding.

Just thought I'd tune in for a sec.. XIII-2 for the PC was just released some hours ago. I've already been prodding at it, and from the looks of it the containers extract relatively easily (much like with XIII) but the same problem with the models persist. At a glance, I can't really tell exactly what's different, but they don't appear too dissimilar to the console versions.

I'm really hoping some research is put into this, since the original games were dissected so thoroughly already it honestly wouldn't take that much effort using what knowledge is already out there to bust the PC versions wide open.
## Post #12
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2014-12-13T00:02:08+00:00
- Post Title: Final Fantasy XIII PC Modding.

> Reply from Krisan Thyme
>
> Just thought I'd tune in for a sec.. XIII-2 for the PC was just released some hours ago. I've already been prodding at it, and from the looks of it the containers extract relatively easily (much like with XIII) but the same problem with the models persist. At a glance, I can't really tell exactly what's different, but they don't appear too dissimilar to the console versions.

I'm really hoping some research is put into this, since the original games were dissected so thoroughly already it honestly wouldn't take that much effort using what knowledge is already out there to bust the PC versions wide open.

Perhaps, but the steam and hype died as essentially it is an old game and nobody competent enough to get stuff done cares anymore.
Shame, because on PC we could've gotten so much more.
## Post #13
- Username: rhadamants
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 10, 2014 3:13 am
- Post datetime: 2014-12-14T01:22:03+00:00
- Post Title: Final Fantasy XIII PC Modding.

Is there any way how to extract the files from the PC version of FFXIII-2.
## Post #14
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2014-12-14T02:42:20+00:00
- Post Title: Final Fantasy XIII PC Modding.

There's nothing special to extracting it, it's essentially the same exact type of container as the console versions.
## Post #15
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-12-17T13:55:25+00:00
- Post Title: Final Fantasy XIII PC Modding.

The guy who made FF13 pc unpacker/repacker has updating his tool to support FFXIII-2 PC. Here it is [http://www.tzarsectus.com/tools/ff13tool.rar](http://www.tzarsectus.com/tools/ff13tool.rar) but you need decrypt the filelist first using tool from here [viewtopic.php?p=90451#p90451](http://forum.xentax.com/viewtopic.php?p=90451#p90451)

Btw,what version of maya need to run FFXIII importer that TheDude said above???
## Post #16
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-12-22T01:50:18+00:00
- Post Title: Re: Final Fantasy XIII PC Modding.

How do we go about getting these back in the game?




They are hidden in the PC version of the game in system_ck.img and system_ck.xgr in the gui folder of the resident folder of imgc extract. I tried to replace and repack but it won't switch
