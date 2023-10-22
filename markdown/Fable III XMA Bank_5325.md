## Post #1
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-10-30T14:50:00+00:00
- Post Title: Fable III XMA Bank

Here's the first 10 megabytes of the XMA bank from Fable III

After finding all the XMA flag's I began having issues converting them to WAV after the address "00575C36"

Anyone know why?

[http://www.flameupload.com/files/1JZABGQK/Fable_III.xma](http://www.flameupload.com/files/1JZABGQK/Fable_III.xma)

EDIT: Figured out why for that. The xma was multi-channelled.

New issue, I have a 1GB XMA file going from the first six bytes before the XMA flag all the way down to the next flag. Naturally I can't run this through QuickBMS so I'm not sure what to do.

EDIT 2: Never mind. Thanks to the universal genius wisdom of barnaby64, I've now got it sorted.
## Post #2
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2010-11-12T01:11:11+00:00
- Post Title: Fable III XMA Bank

How do you convert these xma to wave?
I've tried "xmaencode" (from xdk) and "towav" and both tools cannot convert them.
Any manipulation needed with xma's extracted from bnk/dat before decoding them? or, maybe, another tool?
Thanks in advance.
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-11-12T01:23:43+00:00
- Post Title: Fable III XMA Bank

Get AlphaTwentyThree's WAVE Format Scanner script from his thread found [here](http://forum.xentax.com/viewtopic.php?f=13&t=4450)

Then run the script using QuickBMS on the streaming.bnk.dat file.

Let me know how that goes.
## Post #4
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2010-11-12T02:10:39+00:00
- Post Title: Fable III XMA Bank

I used the following script to extract files from streaming.bnk + streaming.bnk.dat, then I used it again on extracted music_region.bnk.dat + music_region.bnk (from "data\levels\audio") and I get 24 files with .WAV extension, but actually they are XMAs. How to convert them to PCM WAVs?

```

```
## Post #5
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-11-12T02:33:59+00:00
- Post Title: Fable III XMA Bank

You need to add the proper XMA header to the files.
## Post #6
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2010-11-12T19:17:15+00:00
- Post Title: Fable III XMA Bank

These files starts with RIFF (WAVEfmt ) header.
Where I can get info about the "proper header"?
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-11-12T19:37:00+00:00
- Post Title: Fable III XMA Bank

Use this script made by AlphaTwentyThree.

Add RIFF header to headerless XMA files

```

set FREQ 48000
set CH 2

get NAME basename
get SIZE asize
string NAME += ".xma"
set RIFFSIZE SIZE
math RIFFSIZE += 0x34
putVarChr MEMORY_FILE 0x04 RIFFSIZE long
putVarChr MEMORY_FILE 0x24 FREQ long
putVarChr MEMORY_FILE 0x31 CH byte
putVarChr MEMORY_FILE 0x38 SIZE long

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 0x3c
log NAME 0 SIZE MEMORY_FILE
```


Once you've added the proper header, try running the files in Winamp with the VGMStream plugin.
## Post #8
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-11-13T14:24:34+00:00
- Post Title: Fable III XMA Bank

But vgmstream doesn't support xma yet....
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-11-14T09:37:52+00:00
- Post Title: Fable III XMA Bank

> Reply from bxaimc
>
> But vgmstream doesn't support xma yet....

Then use "towav" to convert the files.
