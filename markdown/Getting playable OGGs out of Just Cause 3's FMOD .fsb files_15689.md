## Post #1
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2017-01-06T17:18:02+00:00
- Post Title: Getting playable OGGs out of Just Cause 3's FMOD .fsb files

I realize that this is a problem likely as old as time itself, but:

I used Gibbed's tools to extract JC3's arc/tab files and then used this QuickBMS script to extract FSBs from the extracted .bank files:

```
    goto OFFSET
    findloc OFFSET string "FSB5"
    goto OFFSET
    getdstring FSB_SIGN 4   # FSOUND_FSB_HEADER_FSB5 (fsb.h)
    get version long
    get numsamples long
    get shdrsize long
    get namesize long
    get datasize long
    xmath SIZE "0x3c + shdrsize + namesize + datasize"
    log "" OFFSET SIZE
next OFFSET + SIZE
```

It's from somewhere in this forum, I forgot from where exactly.

Next, I used Aezay's FSB Extractor (I probably could've used fsbext.exe, but this GUI was nice to use and displayed extra info) to try to extract the actual music from these files, but all I got were weird OGG files with what seems to be a missing header.
Now, I used Google extensively before writing this post and it seems that the only solutions to this problem are:
1. Using FMOD Designer to rejigger the FSB files, which is pretty hard because one can't actually download it anymore without emailing their sales dept
2. Recording the output of some tool called "Music Player Ex" which I can't find because there are so many malware sites using that name

I realize that the OGG format (or at least the version used by the FMOD thingy) makes it difficult if not impossible to restore a generic header.
Still, I'd like to avoid reencoding the sound files if at all possible. Has someone solved the problem of extracting FMOD files yet?

If anyone wants to take a shot at extracting the music, here's one of the OGG files: [https://bubbelsearch.de/files/jc3/jc3_m ... rd_end.ogg](https://bubbelsearch.de/files/jc3/jc3_mus_guitarchord_end.ogg)
## Post #2
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2017-01-07T03:56:32+00:00
- Post Title: Getting playable OGGs out of Just Cause 3's FMOD .fsb files

Welp, I figured out how to do it.
A kind soul by the name of Tomasz Miąsko wrote a tool to extract samples from FSB5 files, but included an assertion that made the program fail on unexpected headers, making extraction from Just Cause 3's files impossible.
I fixed that assertion to make it possible: [https://github.com/SamusAranX/fsb-vorbis-extractor](https://github.com/SamusAranX/fsb-vorbis-extractor)
It's seemingly Linux-only, but that shouldn't be a problem. If I did it, everyone else with access to a working Linux system should be able to do it as well.

It still crashes on FSBs that contain non-music files, namely on these:
character
debug
dialog
diegetic
effects
game_objects
gui
vehicles*
weapons*

Luckily, all the music gets exported correctly, as far as I can tell. Here's the contents of my music_challenges folder after extraction:

And best of all, it doesn't seem to get re-encoded, so you're getting it as the devs intended it to be heard: In ~200-300 kb/s Ogg Vorbis. 
(Seriously, I can't effing wait for an official soundtrack release on CD. Take all my money, Avalanche.)
## Post #3
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2017-11-07T21:30:59+00:00
- Post Title: Getting playable OGGs out of Just Cause 3's FMOD .fsb files

[http://zenhax.com/viewtopic.php?f=17&t=1901](http://zenhax.com/viewtopic.php?f=17&t=1901)
