## Post #1
- Username: wiaparker
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 20, 2014 11:31 pm
- Post datetime: 2014-10-07T10:22:16+00:00
- Post Title: PS2 audio format - NOB

Welcome, can somebody tell me how could I edit .nob file (with game audio) from Alone in the Dark 4: New Nightmare on PS2? With programs like PSSound, I can extract files from that archive to wav, but I want to edit .nob file, because I want to make polish version to this game and play it on my PS2. 

Here is this file - ENGLISH.NOB
[http://www54.zippyshare.com/v/52303450/file.html](http://www54.zippyshare.com/v/52303450/file.html)

Thank you in advance!
## Post #2
- Username: IlDucci
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 20, 2014 10:01 pm
- Post datetime: 2016-02-08T10:26:14+00:00
- Post Title: PS2 audio format - NOB

This should be in Game Archive. Anyway, you can find a packer/unpacker on the Alone in the Dark 4 ripkits for PlayStation 2, on ConsoleGamingWorld.

Besides that, I've did a quick re-check of the format:

> Two files: NOB and FAT.
>
> FAT: FILELIST
>
> 0x10 byte header.
>
> 0x04 bytes: Full NOB filesize.
>
> 0x04 bytes: Amount of entries located in FAT.
>
> 0x04 bytes: UNKNOWN
>
> 0x04 bytes: 0x00.
>
> 
>
> Each entry has 0x38 bytes.
>
> 0x28 bytes: File name (Ends with a 0x00, padded with 0x0D)
>
> 0x04 bytes: File position (Written as LBA, meaning 0x01= 2048 bytes)
>
> 0x04 bytes: File size (Written as byte per byte)
>
> 0x08 bytes: 0x00.
>
> 
>
> NOB: File contents, everything is padded to 2048 bytes.
