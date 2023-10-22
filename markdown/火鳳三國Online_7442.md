## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-30T21:24:40+00:00
- Post Title: 火鳳三國Online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-30T23:59:06+00:00
- Post Title: 火鳳三國Online

I saw PKO on this forum before. I think chrrox posted a thread on it, but don't remember what he called it.

Phoenix Knights Online or something.

EDIT: here it is  [viewtopic.php?f=10&t=3817&start=0](http://forum.xentax.com/viewtopic.php?f=10&t=3817&start=0)
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-10-01T17:44:19+00:00
- Post Title: 火鳳三國Online

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-10-01T22:38:00+00:00
- Post Title: 火鳳三國Online

offzip still works on the files.
I see what they did they moved the zip information to the end of the file.
they left the name where it was but moved the zsize and size information at the end of the archive.
if you want to see a directory listing you can use this bms.

once i look at the ending headers i should be able to get this to work again i am just buys playing a game now so mabee later.

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
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-10-24T22:16:10+00:00
- Post Title: 火鳳三國Online

Thanks chroxxx
## Post #6
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-12-10T17:39:54+00:00
- Post Title: 火鳳三國Online

Any idea or news?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-14T00:23:30+00:00
- Post Title: 火鳳三國Online

I used the bms script up there on the pak file but got a bunch of 0 KB files lol
Only the textures seem to came out properly.
## Post #8
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-08-30T06:11:19+00:00
- Post Title: 火鳳三國Online

> Reply from finale00
>
> I used the bms script up there on the pak file but got a bunch of 0 KB files lol
Only the textures seem to came out properly.
Great tool, but I've tested this tool can only extract a DDS file. Model file is 0 bytes, I hope God can update
