## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-19T19:03:38+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

Hey there!

I'm looking to decode the Ubisoft MPEG files found in Tonic Trouble, and I'd be forever grateful if anyone could help.

Here are some examples of stereo Ubisoft MPEG files: [https://app.box.com/s/4a8u0kbfe1izlewedqjl](https://app.box.com/s/4a8u0kbfe1izlewedqjl) and [download/file.php?id=6911](http://forum.xentax.com/download/file.php?id=6911)
Here are 3 examples of mono Ubisoft MPEG files (they're voice tracks): [https://app.box.com/s/qypjqe1pypd9dtmncern](https://app.box.com/s/qypjqe1pypd9dtmncern)
The stereo files are likely a little harder to handle, as the channels in those files seem to be interleaved.

The tracks seem to be 16-bit 44100Hz files, and from what I've found, the format is a bit like this:

```
0x4 - "2RUS" header for stereo, "1RUS" header for mono
0x??- frame header, starting with at least 8 "on" bits (11111111). This start is just like MPEG, but the rest of the header isn't...
[ frame ]
0x?? - frame header, not offset to a particular byte (as in, there can be 2 "on" bits at the end of one byte and 6 at the beginning of the following byte)
[ frame ]
etc.
```

If it can be of any help, these are the DLL files the game uses to play them: [download/file.php?id=6928](http://forum.xentax.com/download/file.php?id=6928)

Many thanks,
Droolie.
## Post #2
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2013-05-21T21:49:34+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

Sorry for necroing this super old thread, but I've had a recent resurgence of interest in decoding these streams.  DecUbiSnd isn't recognizing them.


> Reply from Droolie
>
> Maybe the MPX files are bigfiles containing segments of music, each of them with a header with "2RUS" in it? Just a guess.
Droolie is definitely correct; the MPX files are bigfiles, while the corresponding CSB file stores the stream offsets and seems to define an array for sample play order/volume/repeat info, etc.  The CSB is in plain-text and describes individual segments as "SAMPLE_MPEG" but I can't seem to find any layer 1, 2, or 3 decoder that will play them.

Attaching the CSBs that should be paired with Droolie's earlier upload (which is still online), on the off-chance someone is willing to take a look at this.
[CSB.7z](https://xentaxbackup.github.io/file/6419_CSB.7z)
## Post #3
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2014-01-08T01:35:02+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

My apologies for again necroing this old thread, but could anyone please look at this? I've attached two files to my post that should each contain a small segment of a song. According to descriptions in the CSB and BNK soundbank files, they should be 44100Hz, 16 bits and stereo...

 2RUS.zip
Two of the 2RUS parts extracted from GROTTH1.MPX (225.66 KiB) Downloaded 33 times


This is what I've managed to figure out about the format:
0x4 - The first 4 bytes are always larger than the amount of bytes in the file itself. Could the file be compressed somehow?
0x4 - "2RUS" header
0x??- block header, starting with a FF byte (or 11111111 if you like bits). The FF start is just like MPEG, but the rest of the header isn't...
[ block ]
0x?? - block header
[ block ]
etc.
That's what I have so far, but I could be wrong...

Can anyone help?
## Post #4
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2014-01-19T00:10:36+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

Here's a quick bump, adding more files and hoping that someone might look at it: [https://app.box.com/s/4a8u0kbfe1izlewedqjl](https://app.box.com/s/4a8u0kbfe1izlewedqjl)
I also attached the DLL files that are used to play these MPEG audio files.


 dll.zip
The DLLs that are used to play these "MPEG" audio files. (116.49 KiB) Downloaded 34 times


Will anyone take a look or am I doomed to search alone forever?
## Post #5
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2014-02-04T12:02:45+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

I'm still looking at this and still quite stuck. I've started actually playing the game and trying to see how it plays the music. It seems if you change the "2RUS" to "1RUS", it attempts to play the tracks in mono, showing how the channels in these files are interleaved.

Any help please?
## Post #6
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2014-07-10T22:27:17+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

My apologies for the constant necroing of this topic... but whoever helps with this will be my personal hero!
## Post #7
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2015-01-14T14:01:15+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

I'm still looking for this, and any help at all would be fantastic.

I figured out a little more by doing some tests while playing and updated the first post with all the relevant details on the format I was able to figure out  (not much).
I also added 3 examples of mono Ubisoft MPEG files (they're voice tracks): [https://app.box.com/s/qypjqe1pypd9dtmncern](https://app.box.com/s/qypjqe1pypd9dtmncern)
The stereo files I attached to my previous posts are likely a little harder to handle, as the channels in those files seem to be interleaved.

I'd be forever grateful if you could at least try to help figure it out!
## Post #8
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2016-06-07T03:28:30+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

Okay... I'm not sure if I'm getting anywhere here, but it feels like I'm on the right track.  MPGMXBVR.DLL has several functions, but the most prominently interesting is SND_fn_lPlayMPEG, which I saw running in memory by using Cheat Engine.

That led me to experimenting with OllyDbg, which offered the very much enticing prospect of loading a DLL.  Unfortunately, I hit some roadblocks when I discovered that SND_fn_lPlayMPEG wants 5 different integers passed to it, which I have yet to determine how to define...

Using IDA, I was able to get some pseudo-code which looks like it could possibly be the decryption method:

```
{
  int v6; // [sp+4h] [bp-10h]@5
  int v7; // [sp+4h] [bp-10h]@16
  __int16 v8; // [sp+8h] [bp-Ch]@7
  __int16 v9; // [sp+8h] [bp-Ch]@18

  if ( !dword_10024CBC )
    return -1;
  if ( dword_10024CB8 )
  {
    sub_10006BA2(dword_10024CAC);
    dword_10024CB8 = 0;
  }
  if ( *(_DWORD *)(a1 + 40) )
  {
    v6 = sub_100046E3(a1 + 48, *(_DWORD *)(a1 + 64));
    if ( v6 )
    {
      if ( *(_DWORD *)(a1 + 24) )
        v8 = *(_BYTE *)(a1 + 12) * *(_BYTE *)(a2 + 4) >> 7;
      else
        v8 = *(_BYTE *)(a1 + 12);
      *(_BYTE *)(v6 + 146) = *(_BYTE *)(a1 + 12);
      *(_BYTE *)(v6 + 147) = v8;
      *(_BYTE *)(v6 + 148) = byte_100266A0[v8];
      *(_DWORD *)(v6 + 60) = *(_DWORD *)(a1 + 24);
      if ( *(_DWORD *)(v6 + 160) )
      {
        *(_BYTE *)(*(_DWORD *)(v6 + 160) + 146) = *(_BYTE *)(a1 + 12);
        *(_BYTE *)(*(_DWORD *)(v6 + 160) + 147) = v8;
        *(_BYTE *)(*(_DWORD *)(v6 + 160) + 148) = byte_100266A0[v8];
        *(_DWORD *)(*(_DWORD *)(v6 + 160) + 60) = *(_DWORD *)(a1 + 24);
      }
      if ( a4 )
      {
        *(_DWORD *)(v6 + 40) = a4;
        *(_DWORD *)(v6 + 36) = a5;
      }
      else
      {
        *(_DWORD *)(v6 + 40) = 0;
      }
      return v6;
    }
    return -1;
  }
  v7 = sub_100048A6(*(_DWORD *)(a1 + 48), *(_DWORD *)(a1 + 56));
  if ( !v7 )
    return -1;
  if ( *(_DWORD *)(a1 + 24) )
    v9 = *(_BYTE *)(a1 + 12) * *(_BYTE *)(a2 + 4) >> 7;
  else
    v9 = *(_BYTE *)(a1 + 12);
  *(_BYTE *)(v7 + 146) = *(_BYTE *)(a1 + 12);
  *(_BYTE *)(v7 + 147) = v9;
  *(_BYTE *)(v7 + 148) = byte_100266A0[v9];
  *(_DWORD *)(v7 + 60) = *(_DWORD *)(a1 + 24);
  if ( *(_DWORD *)(v7 + 160) )
  {
    *(_BYTE *)(*(_DWORD *)(v7 + 160) + 146) = *(_BYTE *)(a1 + 12);
    *(_BYTE *)(*(_DWORD *)(v7 + 160) + 147) = v9;
    *(_BYTE *)(*(_DWORD *)(v7 + 160) + 148) = byte_100266A0[v9];
    *(_DWORD *)(*(_DWORD *)(v7 + 160) + 60) = *(_DWORD *)(a1 + 24);
  }
  if ( a4 )
  {
    *(_DWORD *)(v7 + 40) = a4;
    *(_DWORD *)(v7 + 36) = a5;
  }
  else
  {
    *(_DWORD *)(v7 + 40) = 0;
  }
  return v7;
}
```


I am still having a really hard time making sense of it.  I would love to have one of our many forum experts give a helping hand!
[MPGMXBVR.7z](https://xentaxbackup.github.io/file/11028_MPGMXBVR.7z)
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-11T07:29:36+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

You really should mention that these mpeg files come from special version of the game. I'm going to look into that now, if you still need it.
## Post #10
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2016-06-20T04:44:07+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

Yes, sorry, I forgot to mention, these are from the special edition (or beta) version of the game.  Thank you so much for looking into it!

If you need any additional files I would be happy to provide them.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-20T15:45:08+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

No, I have all the files. Did some research. There are 2 possible ways to decode this.

1. reverse the decoding function. That code you provided is only one tiny part of it. The whole thing includes dozens of subroutines and floating point tables. You could expect that from mpeg-like codec. So reversing this will probably take months, and if its only for 1 game, its just not worth it.

2. find a way to call their DLL. This may be possible, but again, many troubles. They call many different DLLs one from another, and probably make callbacks. I have no idea yet how to do it.
## Post #12
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2016-06-21T13:49:27+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

That's really unfortunate.  I thought I was on to something there.

On another note, I tried editing a CSB file to get it to load parts from another MPX and it completely ignored my changes.  I am not sure if those are even used by the compiled game...  they may just be remnants from source code.
## Post #13
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2016-07-26T17:01:29+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

Would it be possible to figure out the encryption/compression scheme if the file contained within is a known format?  

See attached example - the header states that this is completely normal 44.1kHz 16-bit stereo wave file, yet it certainly doesn't play properly, and in a hex editor, the character distribution looks absolutely nothing like a wave file. 

The game's CSB files indicate that these (as well as .MPX files) are stored/encrypted in a container:  "SetZipFormat(SAMPLE_MPEG)"
[__do01.7z](https://xentaxbackup.github.io/file/11382___do01.7z)
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-28T06:24:53+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

> Reply from kooz
>
> Would it be possible to figure out the encryption/compression scheme

No, they are not encrypted or compressed. This file is encoded into some kind of mpeg. The header doesn't mean anything. It's just information about the audio data.
## Post #15
- Username: bsod49
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 30, 2016 6:29 am
- Post datetime: 2019-09-22T02:12:02+00:00
- Post Title: Ubisoft MPEG files (Tonic Trouble)

I asked for help on CTPAX, here's what I got:

"We tried to look into this format. It's more complex than it may look like.

Actual information about .MPX files stored inside .BNM files. Even more, .BNM files itself can have inside .WAV files, or packed ADPCM files.

By now we only can extact uncompressed .WAV files:
bnm_dump.zip (deleted for the group's request, I should have a copy, though).

We will look into .MPX decompression, but can't promise anything, since it's very complex and required .DLL files, it needs a lot of internal structures to be initialized properly to work."

I'll let you know on something new if I'll receive.
## Post #16
- Username: bsod49
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 30, 2016 6:29 am
- Post datetime: 2019-09-23T16:35:02+00:00
- Post Title: Re: Ubisoft MPEG files (Tonic Trouble)

"Regarding to this last topic post.

1) First of all it's not CTPAX it's CTPAX-X Team. You're probably won't be pleased if someone cut your name in a half.

2) We should apologize since we didn't state it clearly but this tool we send you intended only to show you the progress we made so far. It's a test tool and by any means we do not want to distribute it. We have around 160 tools at our site and almost all of them released with the source codes - anyone can change it, compile or redistribute.
But we really don't want to distibute unfinished work since we have a few situations in the past when our WIP work was leaked but even after we released proper and finished work many years later people still somehow find our old unfinished tools somewhere in the Internet and complain that it didn't work or have bugs or errors. It's very unpleasant, frustrating and ruining any motivation to continue our work.

You can have this tool, but please do not post links to our software unless it was officially published at main [www.CTPAX-X.org](http://www.CTPAX-X.org) site."


PS. Forgot to post Luigi's script for QuickBMS for extracting all files inside MPX using CSB (use this two files together during extracting). It's on QuickBMS site.
## Post #17
- Username: bsod49
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 30, 2016 6:29 am
- Post datetime: 2019-09-24T20:13:27+00:00
- Post Title: Re: Ubisoft MPEG files (Tonic Trouble)

"We have some progress on .MPX files but need some data to examine."
They're still in the game. I've been asked for mono 1RUS files. I only provided Droolie's mono.zip file from the first post.
By the way, don't know from where it was taken, maybe BNM files, maybe it's not important right now.

Trivia
APM where for sure decoded by Synthesis Ray2Get, but the tool also covered every single audio in Rayman 2, so I think also BNMs, not only APMs, but the format inside was probably different in those BNMs than in TC beta since Ray2Get uses only one decoder for all audio, and it is not the same like in TC beta.
## Post #18
- Username: bsod49
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 30, 2016 6:29 am
- Post datetime: 2019-09-28T22:20:36+00:00
- Post Title: Re: Ubisoft MPEG files (Tonic Trouble)

The tool has been released with source codes:
[http://www.ctpax-x.org/?goto=files&show=161](http://www.ctpax-x.org/?goto=files&show=161)

You can consider donating CTPAX-X on Kiwi, Yandex Money, Webmoney (data provided in the left of the main page) helping them keep their site online.
