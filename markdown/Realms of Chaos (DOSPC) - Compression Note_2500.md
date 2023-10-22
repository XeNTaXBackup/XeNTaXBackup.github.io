## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-07T06:09:41+00:00
- Post Title: Realms of Chaos (DOS/PC) - Compression Note

For those people out there who still have this game who wish to open up the datafile... well... you can. The DAT file is just a LHA archive. You can use your favorite archive tool and just decompress it easy.

Now a few notes: Some TXT files are encoded but the music and sounds seem to work just fine. The sprites are ".SPR" which will probably be no hassle to view. Sounds are just Creative Voice Files (VOC) and music is MIDI. There are uncertainties though but everything decompresses right. And should also recompress right as well if you wish to make a modification. Afterall, the level data is all there I believe.

Why am I stateing this? Just shareing my findings. Cheers! 

-Darkfox
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-07T09:19:54+00:00
- Post Title: Realms of Chaos (DOS/PC) - Compression Note

Ok, an extra thing to answer some things.

For now it will not work to just make a LZH and call it ROC.DAT and expect it to work. It won't. It MIGHT be possible to use the old DOS LHA program but only to replace a file existing in the archive with one of a similar size.

I may be missing somthing here but I tested the theory, doesn't work. Might be possible with replaceing with a file INSIDE the archive otherwise forget it.

I don't know what to do with that but anyways...

You can extract everything with TUGZip or the DOS program LHA.EXE both are freeware.

-Darkfox
## Post #3
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-03-07T10:59:46+00:00
- Post Title: Realms of Chaos (DOS/PC) - Compression Note

LHA archives have different compression methods, usually newer LHA versions were backwards-compatible. Probably the game itself doesn't support a newer method.
Iirc you can display the compression method used when using LHA to list the archive contents. Maybe the methods from the original archive and the new archive are different.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-07T20:09:28+00:00
- Post Title: Realms of Chaos (DOS/PC) - Compression Note

Thats what I was thinking but I'm not exactly sure. Most files in the datafile are lh5... hmmmm... guess I should try getting the older LHA version and see how that does.
