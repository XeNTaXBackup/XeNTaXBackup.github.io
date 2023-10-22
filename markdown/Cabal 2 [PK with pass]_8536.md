## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-13T00:50:18+00:00
- Post Title: Cabal 2 [PK with pass]

As many of you know Cabal2 is based on crytek .cgf files. The .pak files have password and I tried with aluigis crysis 2 bms but pass is wrong. I have been skimming through some exe files and dlls and can't find it. The best bet is probably to run .exe and find it but I am bad at that stuff 

I found this line in one of the files but did not work:
publicKeyToken="1fc8b3b9a1e18e3b"

Was hoping that was the key 

Here are some files to check, exe,dll,pak

[http://www.2shared.com/file/KculkDzs/CABAL_II.html](http://www.2shared.com/file/KculkDzs/CABAL_II.html)

There are actually some .pak files in LEVELS folder that works because they are plain PK without pass

Found this site about the file format of .cgf to for future noesis 

[http://tresed.trescom.org/jpog/x-isle_formats.html](http://tresed.trescom.org/jpog/x-isle_formats.html)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-13T02:54:53+00:00
- Post Title: Cabal 2 [PK with pass]

What cabal 2 is available for DL???

Or was it out for awhile and I just didn't know the right places to look...
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-13T07:43:26+00:00
- Post Title: Cabal 2 [PK with pass]

```
publicKeyToken="1fc8b3b9a1e18e3b"
```

It's not password 

upload all dll's or link for download client is better.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-13T14:18:06+00:00
- Post Title: Cabal 2 [PK with pass]

```
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate
set XOR_KEY string "0x16 0x95 0x50 0x54 0x9F 0x75 0x7D 0xAC 0x81 0xA3 0xAA 0x95 0x31 0xB3 0x09 0x54 0xA8 0x8A 0x75 0x32 0x12 0x73 0x14 0xCF 0xC3 0x56 0x7C 0x2E 0xCD 0xDE 0xEE 0xEE 0xEB 0x3C 0xd3 0x85 0x16 0x37 0x30 0x28 0x7c"  # incomplete!

for OFFSET = 0
    goto OFFSET
    filexor XOR_KEY OFFSET
    get SIGN long
    if SIGN != 0x04034b50
        cleanexit
    endif
    get ver             short
    get flag            short
    get method          short
    get modtime         short
    get moddate         short
    get crc             long
    get comp_size       long
    get uncomp_size     long
    get name_len        short
    get extra_len       short
    savepos OFFSET
    filexor XOR_KEY OFFSET
    getdstring name     name_len
    getdstring extra    extra_len
    savepos OFFSET
    filexor ""

    if name_len > 41
        putvarchr name 41 0
    endif

    if method == 0
        log name OFFSET uncomp_size
    else
        clog name OFFSET comp_size uncomp_size
    endif
    math OFFSET += comp_size
next
```
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-13T14:26:40+00:00
- Post Title: Cabal 2 [PK with pass]

Works partially but seems that the file ending is getting screwed in some way.

Yeah this client was from september 2011 and I dont see it now anywhere. The weird thing is that the client seems to update even though it was closed beta in september or november
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-13T14:40:38+00:00
- Post Title: Cabal 2 [PK with pass]

I don't have the full key or the algorithm that generates it, so this is the max I can do
## Post #7
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-13T14:42:20+00:00
- Post Title: Cabal 2 [PK with pass]

It is very nice indeed  Is there anything I can do from here? WHen I run launcher it actually downloads a huge .pak file etc, I tried your C9 tutorial but did not find anything.

PS. the generated .chr can be viewed in noesis
## Post #8
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-03-13T15:12:49+00:00
- Post Title: Cabal 2 [PK with pass]

Client Torrent:


[http://www.mediafire.com/?msy822ld44xl0ej](http://www.mediafire.com/?msy822ld44xl0ej)
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-13T15:30:47+00:00
- Post Title: Cabal 2 [PK with pass]

I have updated the script so that if the name is longer than 41 chars it gets truncated.
the good thing is that when it will ask about a duplicate filename you must only select the 'r' choice and it will automatically rename all the duplicated names.
## Post #10
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-13T18:52:29+00:00
- Post Title: Cabal 2 [PK with pass]

Working good. Just need to figure out how to do some animation stuff now
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-13T22:36:38+00:00
- Post Title: Cabal 2 [PK with pass]

Someone already wrote the model script when the archives were just unpacked? Lol
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-14T01:36:18+00:00
- Post Title: Cabal 2 [PK with pass]

I think it's plugin for 3DMAX or Maya from CryEngine SDK
## Post #13
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-14T16:20:53+00:00
- Post Title: Cabal 2 [PK with pass]

well it's crytek modified so only needed to do some tweaking. You have crysis, aion and other games already done so this was a small change I guess
## Post #14
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2012-10-15T05:41:30+00:00
- Post Title: Cabal 2 [PK with pass]

Above torrent doesn't work properly.
Could anyone do share the full client of cabal2 ?
I am researching the cryengine3 cgf file format. ^^
## Post #15
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-10-16T06:19:42+00:00
- Post Title: Cabal 2 [PK with pass]

> Reply from MrMoonKr
>
> Above torrent doesn't work properly.
Could anyone do share the full client of cabal2 ?
I am researching the cryengine3 cgf file format. ^^
[http://down.cabal2.co.kr/setup/cabal2setup.exe](http://down.cabal2.co.kr/setup/cabal2setup.exe)
