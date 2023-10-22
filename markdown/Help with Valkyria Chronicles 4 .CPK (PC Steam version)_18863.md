## Post #1
- Username: DoomyDoom
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 27, 2018 12:49 am
- Post datetime: 2018-09-26T17:36:34+00:00
- Post Title: Help with Valkyria Chronicles 4 .CPK (PC Steam version)

Hello.

So VC4 got released yesterday, and I'm having some trouble with unpacking its files. I'm not knowledgeable about the ways of archiving, compression and encryption algorithms, so I'm requesting some help.

The CPK file appears to be extractable by a couple of tools. Specifically, quickBMS with script from official page (0.3.3) and CriPakTools can list and extract... let's say SOME files, because I'm not sure they've read ALL of them. Most likely all, but that's an assumption from my part. Those files are provably readable and have expected things in them, so there appears to be no file-level encryption going on.

Now, the issue comes around when I need to pack things back in. Creating an archive from scratch with CriPakTools sure packs them in (and can naturally extract back correctly everything it packs), but there appears to be some magic/format alteration at the beginning which results in an archive that the game does not read (CTD on load, which was typical for incorrect files in VC1 as well). 

Looking closer, it might be similar to this case: [viewtopic.php?f=10&t=5067](http://forum.xentax.com/viewtopic.php?f=10&t=5067)
There's same-ish thing with CPK header and TOC header starting off with a lot of similar bytes and some differencies, so I guess it's necessary to figure out how to create an expected CPK header from TOC and some magic numbers+algo?

Could also be a different compression algorithm, file size packed by CriPakTools is slightly smaller.

Oh, the file in question
{{scrapped as promised below}}
There's of course a lot more, but this one is the only small one (68 MB, the one I'm more interested in is 23 GB of base game data). I'll take it down after it's no longer necessary.
## Post #2
- Username: Giza
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 22, 2018 2:51 pm
- Post datetime: 2018-09-29T05:04:42+00:00
- Post Title: Help with Valkyria Chronicles 4 .CPK (PC Steam version)

> Reply from DoomyDoom
>
> 
used YACpkTool [https://github.com/Brolijah/YACpkTool](https://github.com/Brolijah/YACpkTool)
## Post #3
- Username: DoomyDoom
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 27, 2018 12:49 am
- Post datetime: 2018-09-29T12:27:01+00:00
- Post Title: Help with Valkyria Chronicles 4 .CPK (PC Steam version)

Tanks, this indeed seems to have worked. At least the game launched correctly after repacking (didn't try editing though, but that's a tale for another day). Apparently my issues were (and still are) just Denuvo being Denuvo and not letting me lauch on one of my PCs.
