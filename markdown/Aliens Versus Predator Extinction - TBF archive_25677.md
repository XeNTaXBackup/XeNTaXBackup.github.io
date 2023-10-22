## Post #1
- Username: Predator
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 07, 2022 10:45 pm
- Post datetime: 2022-08-07T14:58:28+00:00
- Post Title: Aliens Versus Predator: Extinction - TBF archive

Hi guys, I decided to create an account on this forum because I don't know what else I can do, I really like this game and I had the idea of ​​creating a mod to improve the textures of the game, since it is very old and we probably won't have one PC version for it. But because it is a Playstation 2 game, the process is much more complicated than I imagined, I was able to extract the game's ISO image files, and I was able to edit only the ".pss" video files, but the texture – which I believe is contained within the “tbf.tbf” file – are inaccessible.

I don't know anything about “ripping games”, much less about Playstation 2 games, can you help me? I've already downloaded several programs and saw that there is a possibility to extract the textures of the game using PCSX2 and the program "ninjaripper", but even if I do this as a "workaround", how will I be able to put these modified textures "inside the game" again?

Thank you!
[]s
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-07T19:50:24+00:00
- Post Title: Aliens Versus Predator: Extinction - TBF archive

> but the texture – which I believe is contained within the “tbf.tbf” file – are inaccessible.
Hi. If you want to extract/import textures from "TBF.TBF" archive, you need to reverse engineer it first.
There are no tools or specification for this type of archive, so you would need probably start from the 
beginning. There are some tutorials here on how to achieve this [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

Btw - archive starts with "RIFF" signature as standard WAV files, but the content of this RIFF container seems to be completely custom.

> how will I be able to put these modified textures "inside the game" again?
There is no way to inject textures from memory without knowing the file format of the archive and images inside.
## Post #3
- Username: Predator
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 07, 2022 10:45 pm
- Post datetime: 2022-08-08T16:27:30+00:00
- Post Title: Aliens Versus Predator: Extinction - TBF archive

> Reply from ikskoks ↑Mon Aug 08, 2022 3:50 am at Mon Aug 08, 2022 3:50 am
>
> 
but the texture – which I believe is contained within the “tbf.tbf” file – are inaccessible.
Hi. If you want to extract/import textures from "TBF.TBF" archive, you need to reverse engineer it first.
There are no tools or specification for this type of archive, so you would need probably start from the 
beginning. There are some tutorials here on how to achieve this viewtopic.php?f=29&t=22266

Btw - archive starts with "RIFF" signature as standard WAV files, but the content of this RIFF container seems to be completely custom.
how will I be able to put these modified textures "inside the game" again?
There is no way to inject textures from memory without knowing the file format of the archive and images inside.

First of all, thanks for replying to me and showing me these articles! Reverse engineering seems to be too complicated for me at the moment, luckily I found an alternative to my problem:

I'm using a version of PCSX2 called PCSX2-NIGHTLY that allows you to dump the game's textures and replace the existing ones in the game, I discovered this yesterday and since then I've been doing some restorations in some alien models and in the game's scenario, see:



I'm using AI to "restore" some textures.

Thanks again for commenting here!
## Post #4
- Username: johnlul
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 06, 2022 11:24 am
- Post datetime: 2022-12-15T22:17:32+00:00
- Post Title: Aliens Versus Predator: Extinction - TBF archive

any updates ?
## Post #5
- Username: SasoriZero
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 02, 2023 11:05 am
- Post datetime: 2023-07-02T03:08:00+00:00
- Post Title: Aliens Versus Predator: Extinction - TBF archive

Hey, I would love to talk more about this at length as I am actually trying to achieve something similar to REDRIVER2 but for AVP:E and Ring of Red, I sent a private message

I am a software engineer and would be very interested in creating a tool to read AVP:E's file types
