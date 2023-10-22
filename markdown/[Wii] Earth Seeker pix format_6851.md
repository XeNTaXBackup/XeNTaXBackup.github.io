## Post #1
- Username: quantico
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 19, 2010 6:19 pm
- Post datetime: 2011-06-25T19:53:55+00:00
- Post Title: [Wii] Earth Seeker pix format

I am not really into graphics formats so maybe someone with more knowledge will be able to work with this.

The sample should be a map form the game, most of the files in this game are very standard so its possibly very easy to figure out...

Hopefully someone can help me out. Thanks.
[s_map00.zip](https://xentaxbackup.github.io/file/4376_s_map00.zip)
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-06-26T09:56:52+00:00
- Post Title: [Wii] Earth Seeker pix format

Looks like the header is in little endian byte order and contains some information for the use of the image. After the first 4 bytes ("FPIX") there comes the filesize and, there are similar values after the "DPIX" and "XPIX" but smaller. Maybe some pointer.
Anyway the image starts at 0x6C and its the standard TPL (0x0020AF30) format (see [http://hitmen.c02.at/files/yagcd/yagcd/ ... l#sec15.35](http://hitmen.c02.at/files/yagcd/yagcd/chap15.html#sec15.35)) at the end right after the TPL there comes some gameinfo again (28 bytes - "XNAM"...).
I was able to dump the TPL with TplMii and tplx by just cutting it out from the archive first
[](http://imageshack.us/photo/my-images/4/unled1do.png/)
## Post #3
- Username: quantico
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 19, 2010 6:19 pm
- Post datetime: 2011-06-26T10:44:00+00:00
- Post Title: [Wii] Earth Seeker pix format

Kickass I suspected it would be a tpl with some kind of added content. Should have looked for the tpl header format! Thanks a lot for helping me out this fast!
