## Post #1
- Username: Chaosdragonkg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 11, 2012 2:06 pm
- Post datetime: 2012-05-12T10:09:43+00:00
- Post Title: [Solved] Mercenaries 2: Problem With .block Files

Alright, just gonna make this quick and clear.

All I want to do is get to the very source of the models in Mercenaries 2. Using aluigi's QuickBMS application and his script for Mercenaries 2(.wad) as well, I successful opened and got the extracted .block files from vz.wad.

Now here is the problem.

Three block files:
wpn_sniperrifle_P000_Q3.block
wpn_sniperrifle_P000_Q3.block_0
wpn_sniperrifle_P000_Q3.block_1

The first being 2 KB, second 1,672 KB, third 1 KB.
With limited knowledge of archives, I'm guessing these three are separated parts of one whole.

But, whenever I attempt to use the same exact script which was made for block files in the first place,
I end up with an offset error like so:
[http://postimage.org/image/gtb5kii1d/](http://postimage.org/image/gtb5kii1d/)

Experimented with the script a few times afterwards in an attempt to workaround it, ended up with undesired results.

So my question here is: 
Can there be a workaround, a simple fix to the script, or even an entirely different method by any means necessary to get the data out of these files? Or am I entirely ignorant and I'm using the wrong tools?

I'll provide the links to what I used:

Application

```
http://aluigi.altervista.org/quickbms.htm
```

Script

```
http://aluigi.altervista.org/papers/bms/mercs2.bms
```

Block Files
These are files from the game?  Don't post them
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-12T18:59:31+00:00
- Post Title: [Solved] Mercenaries 2: Problem With .block Files

In the second block file, did you spot the vertex and index buffer? I looked at this game last year, and it was a mess. Fun game, would have been nice to extract the catsuit, but oh well.
## Post #3
- Username: Chaosdragonkg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 11, 2012 2:06 pm
- Post datetime: 2012-05-12T23:06:09+00:00
- Post Title: [Solved] Mercenaries 2: Problem With .block Files

No, probably not possible on my end using Notpad++ to do the viewing and my very little knowledge of scripting language and archives; Just a sea of NUL, SOH, STX, CAN, and all those other characters which are unintelligible to me. I can, although, see the signature "UCFX" at the very beginning which is mentioned in the script and in the QuickBMS window. "data" is also shown mid-way into the first line. No sign of "FFCS" at all. Although, I'm speaking about stuff that I haven't a clue what-n-that does. That's basically why I need some help.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-12T23:53:53+00:00
- Post Title: [Solved] Mercenaries 2: Problem With .block Files

Oh Ok, then to answer your first post, you have it mostly right. Luigi's BMS script just decompresses the blocks in the WAD archives and dumps the uncompressed data. That, you're OK. Taking the resulting files and running the script again won't do anything as nobody has written a model extractor for this game yet.

Last year I tried extracting the models and gave up since the data was a mess. I don't remember why I thought it was impossible to extract, but I own the game, and if you send me those sniper rifle files via PM (I'm too lazy to rip the disc again), I'll take a look at it again really quick.
