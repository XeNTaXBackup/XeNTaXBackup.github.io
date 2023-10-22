## Post #1
- Username: trussive
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 06, 2019 5:51 am
- Post datetime: 2022-02-08T01:11:03+00:00
- Post Title: Nicktoons Unite (NDS)

I decided to look into this game today to find an archive called packfile.pak. I had also looked at the ROM, and it has file names and directories, which is not in packfile.pak. A different Climax game does this in a similar way (SpongeBob SquarePants: SuperSponge), where the archive is just for game resources, and the file list is compiled with the game, separate from the actual resource archive. If you want to see how this is done in SuperSponge, the source code is public ([https://github.com/philosophofee/SBSPSS](https://github.com/philosophofee/SBSPSS)), as well as all of its tools for compiling the game - you'll find what I'm talking about if you look through the tools.

Here's an example of a directory I found in the ROM: Data/Characters/PC/Spongebob/SB.chr
Only thing is that I'm not very sure how to read from this package.

I would send samples, but I would just be sending all of the games resources no matter if I send the ROM in its entirety, or if I only send packfile.pak.
