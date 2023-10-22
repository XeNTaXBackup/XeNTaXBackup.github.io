## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-20T13:07:27+00:00
- Post Title: Code/library for decoding Microsoft Xbox 360 XMA audio?

Is there code or a library out there that can decode audio compressed with the Microsoft Xbox 360 XMA codec?
Not interested in tools that can decode it, I need code or a library I can use (as the XMA audio I am working with is inside another larger file and I want to be able to feed XMA audio in and get uncompressed samples out).
Also not interested in anything that is copied from Microsoft SDKs or leaked or otherwise not legally usable since this is going to be part of a tool I will be shipping.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-20T17:53:56+00:00
- Post Title: Code/library for decoding Microsoft Xbox 360 XMA audio?

ffmpeg's libavcodec has WMA Pro support that does XMA and XMA2 (RIFF codec 0x165 and 0x166):
[https://github.com/FFmpeg/FFmpeg/blob/5 ... dec.c#L294](https://github.com/FFmpeg/FFmpeg/blob/54ccaaeb2b93e19d2a19267db1781bc9d5d36f27/libavcodec/wmaprodec.c#L294)

XMA is essentially just WMA Pro with decode_flags = 0x10d6, though the blocking is different (especially with XMA2).

You may need to use my xma_parse tool to massage the data into a format that this can deal with, and add a RIFF header (or use xmash, if your particular container is supported). xmash and xma_parse are here: [https://hcs64.com/vgm_ripping.html](https://hcs64.com/vgm_ripping.html)

[edit]
AlphaTwentyThree's XMA transform ( [viewtopic.php?f=17&t=9023](http://forum.xentax.com/viewtopic.php?f=17&t=9023) ) has support for extracting from a whole lot of different containers for XMA, using xma_parse on the backend.
