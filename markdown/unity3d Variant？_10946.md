## Post #1
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-11-10T07:51:04+00:00
- Post Title: unity3d Variant？

i use aluigi unity3d_webplayer.bms，no luck:(
get error:the requested amount of bytes to allocate is negative 0xff68ddf5
[battle.unity3d.7z](https://xentaxbackup.github.io/file/6761_battle.unity3d.7z)
## Post #2
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-11-10T07:52:42+00:00
- Post Title: unity3d Variant？

head: UnityWeb
[20131110154710.gif](https://xentaxbackup.github.io/file/6762_20131110154710.gif)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-10T08:48:30+00:00
- Post Title: unity3d Variant？

The offset 0x99003C is bigger than file size (0x1DE31).
To get a clue what's going wrong here you should
get an elder unity3d file that's being unpacked by the script.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-10T08:54:25+00:00
- Post Title: unity3d Variant？

Try this script

[http://aluigi.altervista.org/papers/bms ... player.bms](http://aluigi.altervista.org/papers/bms/unity3d_webplayer.bms)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-10T08:58:09+00:00
- Post Title: unity3d Variant？

That's the script in question. Did it work for you??
(The unity3d file seems to be the problem.)

edit: I tried MBMain.unity3d from the last link in barracuda's post: [viewtopic.php?f=10&t=10085&p=86378&hilit=unity3d#p86378](http://forum.xentax.com/viewtopic.php?f=10&t=10085&p=86378&hilit=unity3d#p86378)

and it's unpacked by Aluigi's script without any problems.
The offset in the header is 0x0000003C. Used it on mappy's sample 
(since the headers being very similar up to 0x003F) but of no avail.
## Post #6
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-11-10T12:58:35+00:00
- Post Title: unity3d Variant？

> Reply from mappy2012
>
> i use aluigi unity3d_webplayer.bms，no luck:(
get error:the requested amount of bytes to allocate is negative 0xff68ddf5

Have you tried this one? -> [viewtopic.php?f=33&t=10739](http://forum.xentax.com/viewtopic.php?f=33&t=10739)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-11-13T20:51:23+00:00
- Post Title: unity3d Variant？

I'm checking the file and the bms script, looks like OFFSET is a 16bit field but it's not clear what's different in the lzma algorithm.
## Post #8
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2013-11-16T17:44:39+00:00
- Post Title: unity3d Variant？

The offset seems to be at byte 60, like in other typical .unity files for that version. However, if my program tries to read the stream, it will instantly hit EOF. No idea, why.

What's the name of the game?
## Post #9
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-20T01:14:55+00:00
- Post Title: unity3d Variant？

I was just sent a unity3d file that failed to work with aluigi's script. I started analyzing it back to back with other files, including one that had the same issue.
The problem is not the same as mappy's sample, but nevertheless it's a "variant" worth looking into. I'd like to share my findings and maybe get some help/clarifications.

Samples:
[game.unity3d](https://mega.co.nz/#!aJVGUSSb!sgwELqbcyjjqEVe-Imea689n5d49YpbikWv7meMqs44) - Lamborghini Huracan web game
[SP.unity3d](https://mega.co.nz/#!ad1AEDTY!Z2ctZdF6tT3b9G_BUNM_GrGEGxeaoQfiPmlI6U8BZ-I) - Sucker Punch web game

1. The first long after the version string (let's call it SIZE like in the script) doesn't seem to be related to the compressed size. Instead it works by coincidence, and sometimes it doesn't.

2. After the OFFSET there are 2 longs, usually 0x1 and 0x1. I don't know what the first one is, but the second indicates pairs of longs, compressed size and uncompressed size.
If there is only one pair, like in most cases, the values are correct as compressed and uncompressed size. Also SIZE - OFFSET = compressed size (the coincidence I was talking about).

Here's where things get interesting. If there is more than one pair like in these samples, only the last pair works. The others appear to be compressed and uncompressed sizes, but they don't do anything and I only see a single lzma stream anyway.
Another interesting fact is that SIZE - OFFSET still matches the first pair, but as I've said it doesn't work for decompression.

The samples have 2 and 18 pairs respectively. So if I use only the last pair the decompression works. And of course, unity3d files with only one pair work as well.
However this seems like a workaround and not a solution. I'd like to understand what the other pairs are and what they're supposed to do.

Here's aluigi's script edited with the above in mind:

```
# script for QuickBMS http://quickbms.aluigi.org

endian big
comtype lzma86head
idstring "UnityWeb"
get DUMMY long
get VER byte
get VER string
get VER string
get SIZE long	#unknown size
get DUMMY short
get OFFSET short
get ONE long
get PAIRS long
for i = 0 < PAIRS
    get ZSIZE long	#last one is actual compressed size
    get SIZE long	#last one is decompressed size
next i

get FSIZE long	#unity3d filesize
#sometimes there is a long before the compressed stream

get NAME filename
string NAME += "_unpacked"
#unpacker only
#clog NAME OFFSET ZSIZE SIZE
set PATH string NAME

clog MEMORY_FILE OFFSET ZSIZE SIZE
get FILES long MEMORY_FILE
for i = 0 < FILES
    get NAME string MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE
    set FNAME string PATH
    string FNAME += /
    string FNAME += NAME
    log FNAME OFFSET SIZE MEMORY_FILE
next i
```
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-03-20T09:38:41+00:00
- Post Title: unity3d Variant？

so it looks like they introduced chunks, rights?
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-03-20T10:08:39+00:00
- Post Title: unity3d Variant？

anyway I have updated the script with the additional info of Chipicao, but this doesn't change the behaviour of the script because lzma in quickbms is used dynamically so it automatically finds the uncompressed size, only the compressed one matters.

Regarding the first file (battle.unity3d) it's damaged because it's the only one that can't be decompressed even if you just select the lzma stream.
## Post #12
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-20T10:23:45+00:00
- Post Title: unity3d Variant？

> Reply from aluigi
>
> Regarding the first file (battle.unity3d) it's damaged because it's the only one that can't be decompressed even if you just select the lzma stream.Just to confirm, I tried dropping the file in my browser and Unity says it's corrupted as well.
## Post #13
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-06-17T10:23:07+00:00
- Post Title: unity3d Variant？

I've been contacted by the user chococat9001 regarding unity files with a .bytes extension. They contain additional content and are downloaded when you run the game.
They are identical to UnityWeb but with a different header "string". Instead of "UnityWeb" it has eight 0xFA bytes.


I thought I'd have a go at adapting the script, and I also wanted to include a case for uncompressed "UnityRaw" files.
So I tried to read 8 bytes with getdstring, but it fails the "==" condition with "\xfa\xfa\xfa\xfa\xfa\xfa\xfa\xfa".
UnityWeb and UnityRaw files work fine. Any idea what's happening?

```
get NAME filename
getdstring FTYPE 8
if FTYPE == "UnityWeb" || FTYPE == "\xfa\xfa\xfa\xfa\xfa\xfa\xfa\xfa"
    comtype lzma86head
elif FTYPE == "UnityRaw"
else
    print "%NAME% is not a recognized Unity archive"
    cleanexit
endif

get DUMMY long
get VER1 byte
get VER2 string
get VER3 string
get SIZE long
get DUMMY short # not supported at the moment
get OFFSET short

get DUMMY long
get ENTRIES long
for i = 0 < ENTRIES # last entry remain saved
    get ZSIZE long
    get SIZE long
next i
get LAST_OFFSET long
get DUMMY byte

string NAME += "_unpacked"
#unpacker only
#clog NAME OFFSET SIZE SIZE
set PATH string NAME

if FTYPE == "UnityRaw"
    log MEMORY_FILE OFFSET SIZE
else
    clog MEMORY_FILE OFFSET ZSIZE SIZE
endif

get FILES long MEMORY_FILE
for i = 0 < FILES
    get NAME string MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE
    set FNAME string PATH
    string FNAME += /
    string FNAME += NAME
    log FNAME OFFSET SIZE MEMORY_FILE
next i
```
## Post #14
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2014-06-30T15:21:16+00:00
- Post Title: unity3d Variant？

I think I figured out the format that Xianjian is using. The game uses the default Unity asset bundle file format, but in combination with a fairly simple XOR scrambler to break the files for other programs. Here's the Java code to fix the data:

```
    byte[] key = new byte[]{};
    for (int exp = 5; 1 << exp < data.length; exp++) {
        data[1 << exp] ^= key[exp % key.length];
    }
}

```


So basically: XOR byte 32 with key[5], then XOR byte 64 with key[6], then XOR byte 128 with key[7] and so on. The descrambled asset bundle is then loaded using AssetBundle.CreateFromMemory(), as explained in the [official documentation](http://docs.unity3d.com/Manual/protectingcontent.html).

Edit: removed the key in case it's against the forum rules, it's in the Disunity repo in case anyone needs it.
## Post #15
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2015-12-16T01:39:46+00:00
- Post Title: unity3d Variant？

Anyway of playing the Sucker punch web game, I can't find it anywhere?
