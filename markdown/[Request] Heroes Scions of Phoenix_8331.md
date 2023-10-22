## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T19:36:38+00:00
- Post Title: [Request] Heroes Scions of Phoenix

Hello guys, well here unpacked files of this cool MMORGP, anyway the format is:

*Models: model
*Textures: DDS
*Other files don't know like 

-primitives
-visual

[Heroes Scions of Phoenix](http://www.pko.com.tw)
[Client](http://www.pko.com.tw/download_file.aspx?k=MAIN&did=0000003&subid=0000001)

[Heroes Scions of Phoenix 2D-3D Samples](http://www.mediafire.com/download.php?z08561upgjqraaa)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T20:27:30+00:00
- Post Title: [Request] Heroes Scions of Phoenix

You (or maybe someone else) posted this before and the models are still 0 bytes for me.
Are you sure they were unpacked properly?
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T20:31:12+00:00
- Post Title: [Request] Heroes Scions of Phoenix

> Reply from finale00
>
> You (or maybe someone else) posted this before and the models are still 0 bytes for me.
Are you sure they were unpacked properly?well you right finale00, I checked all folders now, all have 0 bytes in files, so whats happen here? maybe I post Script you can take a look.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype deflate
for
    findloc start string "UZ\x03\x04"
    goto start
    idstring "UZ\x03\x04"

    get ver         short
    get flag        short
    get method      short
    get timedate    long
    get crc         long
    get comp_size   long
    get uncomp_size long
    get name_len    short
    get extra_len   short
    filexor 0xb2
    getdstring name     name_len
    filexor ""
    getdstring extra    extra_len
    savepos offset

    if method == 0
        Log name offset uncomp_size
    elif method == 8
        CLog name offset comp_size uncomp_size
    else
        print "unsupported compression method %method%"
        cleanexit
    endif

    math offset += comp_size
    goto offset
next
```
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T20:33:09+00:00
- Post Title: [Request] Heroes Scions of Phoenix

No I don't have the game. Upload an archive or two.
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T20:51:38+00:00
- Post Title: [Request] Heroes Scions of Phoenix

ok here I open new thread in proper section.

[[Request] Heroes Scions of Phoenix](http://forum.xentax.com/viewtopic.php?f=10&t=8336)
