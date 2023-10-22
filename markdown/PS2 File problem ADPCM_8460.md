## Post #1
- Username: Nuvedoron858
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 03, 2012 6:47 am
- Post datetime: 2012-03-03T09:05:58+00:00
- Post Title: PS2 File problem? ADPCM

i tried MFAudio but it failed miserably  . I dont know anything about hexadecimal with interleaves and so on... So can anyone help me. I saw someone on this forum used ADPCM Player v.144h to play an Mib file viewtopic.php?f=17&t=5755

Anyway, i tried that but it showed me an error. Now im stuck. Can you help me please?


Here is what the error look like:
[http://www.2shared.com/photo/P2eIrApK/Error.html](http://www.2shared.com/photo/P2eIrApK/Error.html)


This is the file I'm trying to convert:
[http://www.2shared.com/file/EonTwisf/CASINO4.html](http://www.2shared.com/file/EonTwisf/CASINO4.html)


Its from High Rollers Casino 2004
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-03-03T17:08:11+00:00
- Post Title: PS2 File problem? ADPCM

Works fine with the [vgmstream WinAmp plugin](http://hcs64.com/files/vgmstream/).  Be sure to read the readme file in the zip as it requires some additional .dll files.

Just FYI, the interleave is 0x6200.  In the future, for most PS2 ADPCM files, you can copy the first 0x10 bytes of data, and do a search for them in your hex editor.  Typically the next instance of those bytes will indicate the interleave.

For example, your sample has the following bytes at offset 0x00:

```
00000000000000000000000000000000
```

Doing a search for those bytes, you'll find that they occur again at offset 0x6200, there's your interleave.

Can you please share what game this track is from?
## Post #3
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2016-07-20T04:26:19+00:00
- Post Title: PS2 File problem? ADPCM

> Reply from snakemeat
>
> 

Just FYI, the interleave is 0x6200.  In the future, for most PS2 ADPCM files, you can copy the first 0x10 bytes of data, and do a search for them in your hex editor.  Typically the next instance of those bytes will indicate the interleave.

For example, your sample has the following bytes at offset 0x00:
Code: Select all00000000000000000000000000000000
Doing a search for those bytes, you'll find that they occur again at offset 0x6200, there's your interleave.

Hello Snakemeat Can you please tell me exactly how to do this? I'm having the same issue with a song from kelly slater's pro surfer. I've ripped the song files from the audio archive with ADPCM player but cannot play them b/c for some reason the program tries to crash when I hit play. I can play them using another program MFAudio v1.1, but I cannot find the right interleave number. I've tried every value from 100 bytes up to maybe 2000 bytes and the song does not play right. there are a few points along the way where the song sounds like it's going to sound right but then it gets glitchier. I would like to find the correct number. I have a hex editor but its new to me and I just can't get it. you say to copy the first 0x10 bytes of data then do a search for those bytes. Hope to finally figure this out. I've been at it for over two weeks and have even lost sleep over it but I will not stop until I figure this out. 

Here's a link to the file: [http://files.videohelp.com/u/115761/068 ... cf44c0.zip](http://files.videohelp.com/u/115761/068%20-%20STREAM_03cf44c0.zip)
Thanks for your help.
