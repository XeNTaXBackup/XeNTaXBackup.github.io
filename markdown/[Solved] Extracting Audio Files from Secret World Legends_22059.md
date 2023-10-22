## Post #1
- Username: Apexination
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 24, 2020 6:24 pm
- Post datetime: 2020-04-24T10:49:45+00:00
- Post Title: [Solved] Extracting Audio Files from Secret World Legends

I would like help with figuring out how exactly to do this. There's a particular song in the game played that is NOT listed as an official song from the soundtrack, nor has it been identified via the [Songs Used in Secret World [WIP]](https://www.reddit.com/r/SecretWorldLegends/comments/6kdrtb/songs_used_in_secret_world_wip/) over on Reddit. Even ingame, song finders such as Soundhound, Shazam, Beatfind, etc.. can't ID the track either, so I'm doing this as a last resort.

I have looked to see if there was anyone else who tried ripping these files and there was. (There's even a youtube link on how to do it [Here](https://www.youtube.com/watch?v=vzChsmS9hU4), and it's completed(?) within the first 3 minutes of the video.) The only problem is that I have no idea how the heck to even do what they did to extract the files that easily. x.x'

There's the video, there's the [written version of the tutorial](https://bevisbear.com/how-to-export-tsw-rdbdata-file), and there's the required [github page](https://github.com/joakibj/tswrdb) used through both Java and SBT, but I have absolutely no idea how or what to do with any of this. I know nothing of those two programs whatsoever, unfortunately.

  I'm mad at myself because it seems like a simple destination from Point A to Point B, but I'm so lost, it's like I'm stuck in my driveway wondering how to start the damn car, if you feel me. 

I would love any and all advice for this. Even if I need to have it babied to me in order for me to understand it, I'd totally be ready and willing to listen.

Thank you in advance.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-04-24T20:36:51+00:00
- Post Title: [Solved] Extracting Audio Files from Secret World Legends

An easier method, if you just want all of the audio, is to use my attached QuickBMS script.

It will give you 20,717 Ogg audio files

If you don't that, you can get it from Luigi's site: [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)

It's fairly simple to use, but shout if you need further help.


Dave
[rdb.zip](https://xentaxbackup.github.io/file/18023_rdb.zip)
## Post #3
- Username: Apexination
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 24, 2020 6:24 pm
- Post datetime: 2020-04-25T00:17:20+00:00
- Post Title: [Solved] Extracting Audio Files from Secret World Legends

DKDave, I have absolutely no idea how to thank you enough for what you've helped with. !!!!

Thanks to you, I was able to easily extract the music section of the game (from RDB_TYPE = 1020005 --> 1,055 Audio Files) and locate the exact song files I was aiming to download from the game through your .txt file.  A huge shoutout to Luigi's Quick BMS to help with the extraction as well. ^^

Man, I'm beyond happy. I've been trying to find out a way on how to acquire these songs since the original 'The Secret World' game came out back in 2012! No luck until now. 

Thank you, thank you, thank you!
## Post #4
- Username: Zonnenkreeger
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 28, 2016 9:59 pm
- Post datetime: 2020-08-08T20:14:56+00:00
- Post Title: [Solved] Extracting Audio Files from Secret World Legends

> Reply from Apexination ↑Sat Apr 25, 2020 8:17 am at Sat Apr 25, 2020 8:17 am
>
> Thanks to you, I was able to easily extract the music section of the game (from RDB_TYPE = 1020005 --> 1,055 Audio Files) and locate the exact song files I was aiming to download from the game through your .txt file

I'm sorry for hijacking this thread and asking an inane question, but how were you able to deduce that 1020005 marked the beginning of the music files? I'm trying to extract the German language voice lines, as they are not among the 21,000 files extracted by using the RDB_TYPE = 1020002 parameter from the original script. Do you know the correct RDB_TYPE = number that gives me access to those voice lines, or at least how I can find out the relevant number? Any help would be greatly appreciated.
