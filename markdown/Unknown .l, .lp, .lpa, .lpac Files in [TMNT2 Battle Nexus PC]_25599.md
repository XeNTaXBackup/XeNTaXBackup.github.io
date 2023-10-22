## Post #1
- Username: JuicyLumba
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 15, 2022 10:03 pm
- Post datetime: 2022-07-08T17:56:31+00:00
- Post Title: Unknown .l, .lp, .lpa, .lpac Files in [TMNT2 Battle Nexus PC]

Sample Files:
[https://www.dropbox.com/sh/p9fda5knjzii ... xBcRa?dl=0](https://www.dropbox.com/sh/p9fda5knjziika9/AADv1mDz_okbAAajTCe9xBcRa?dl=0)


So TMNT 2 Battle Nexus has a .AFS file which contains all of the games data
And when you extract the data this is the type of files you will see:

[](https://ibb.co/yp8jZnT)

I'm almost certain that zlip compression method is used for these files. because AFSExplorer recognized it!
but extraction game me a .bin file as same as the previous file. Im so confused.

.lpac files!? At first it looks like all of them are just audio but thats not the case, there are models inside of some of these files
I think some of them are just audio files ,I opened them with VLC Media Player, but what I'm really looking for here is 3d models/meshes and they should be somewhere here

Can you give me some help for figuring out these file types/ or maybe a way to decrypt/extract them?

In HxD:
[](https://ibb.co/1dsvFGN)

p.s
If you don't have the time to fix my problem, I'd appreciate it if you gave me a clear road to extracting this. I know its hard and the reverse engineering games is super hard, but if you think some kind of tutorial is best suited for me in this case (.lpac file) I means a lot to me if you shared it
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-10T10:54:42+00:00
- Post Title: Unknown .l, .lp, .lpa, .lpac Files in [TMNT2 Battle Nexus PC]

> I'd appreciate it if you gave me a clear road to extracting this. I know its hard and the reverse engineering games is super hard, but if you think some kind of tutorial is best suited for me in this case (.lpac file) I means a lot to me if you shared it

There is no one clear road in reverse engineering. There are few methods of getting what you want (e.g. static analysis or dynamic analysis).

Static analysis is good for simple cases when you are almost sure what is the file format by just looking at the file in the hex editor.
Your case seems to be more complicated, so you would need to learn dynamic analysis (using IDA and Ghidra for debugging).

Here is good starting point --> [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
Just choose what you want to learn from the list and start reading articles.
