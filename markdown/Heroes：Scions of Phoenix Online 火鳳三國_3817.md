## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-30T01:27:30+00:00
- Post Title: Heroes：Scions of Phoenix Online 火鳳三國

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T02:22:50+00:00
- Post Title: Heroes：Scions of Phoenix Online 火鳳三國

interesting format, practically the "shake" files are totally useless because the "pak" ones are normal zip files with UZ instead of PK and filenames xored with 0xb2 :)

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype deflate
for
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
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-30T02:35:08+00:00
- Post Title: Heroes：Scions of Phoenix Online 火鳳三國

Thanks for this I was suspecting the name was xored and I saw the offsets but I never thought it was a zip format. thanks so much
