## Post #1
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-09-29T05:44:32+00:00
- Post Title: Carrier Command: Gaea Mission

unpacking works fine, but many of the DDS texture look damaged :(

unpack.cmd:

```

rem set game directory
set ccdir=f:\lalala\Carier Command
set files=data00.cc data01.cc data02.cc patch00.pak

for %%i in (%files%) do quickbms -d unpack_cc.bms "%ccdir%\%%i" .\
```

unpack_cc.bms:

```

endian big
get size long           # =filesize-8

idstring PAC1
idstring HEAD
get headerz long        # 35
get tmp long            # 256
for i = 0 < 6
    get zero long
next i

endian little
get year short
get month byte
get day byte
get hour byte
get min byte
get sec byte
print "archive date: %year%-%month%-%day%, %hour%:%min%:%sec%"

idstring DATA
endian big
get dataz long
savepos tmp
math tmp += dataz
goto tmp

idstring FILE
get filez long
get zero short

endian little
get dirs long
for d = 0 < dirs
    set fullpath string ""
    callfunction SaveFile
next d

startfunction SaveFile
    get type byte
    get namez byte
    getdstring name namez
    if type == 0
        string fullpath += name
        string fullpath += \
        get files long
        for f = 0 < files
            callfunction SaveFile
        next f
    elif type == 1
        set fullname string fullpath
        string fullname += name
        get offset long
        get zsize long
        get size long
        get unk1 long
        get unk2 long
        if zsize != size
            clog fullname offset zsize size
        else
            log fullname offset size
        endif
    else
        print "ERROR: unknown type - %type%"
        cleanexit
    endif
endfunction

```
## Post #2
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-10-02T09:57:35+00:00
- Post Title: Carrier Command: Gaea Mission

ok, now DDS format (CC edition :)

```
{
    'COPY' or 'ZLIB' (raw or packed mipmap), chars
    size of mipmap, int
} * N, N = number mipmaps
mipmap[N][] - last mipmap
mipmap[N-1][]
mipmap[N-2]][
...
mipmap[1][] - first mipmap
```
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2012-10-05T12:10:48+00:00
- Post Title: Carrier Command: Gaea Mission

Thanks but how i use the DDS converter? it's bms?
## Post #4
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-10-05T12:55:06+00:00
- Post Title: Carrier Command: Gaea Mission

> Reply from Savage
>
> it's bms?
no, just description ;)

you can use small lua script for unpack resources and convert dds to 1-mip texture ([https://github.com/hhrhhr/Lua-utils-for-Carrier-Command](https://github.com/hhrhhr/Lua-utils-for-Carrier-Command), Downloads, Download as zip). it work with retail and demo versions.

[](http://s1.hostingkartinok.com/uploads/images/2012/10/0b5996e1c8f3315152e28181ca897d6c.jpg) [](http://s1.hostingkartinok.com/uploads/images/2012/10/e7cf239001b8f449b1a710ebbcf9f810.jpg)
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2012-10-05T13:19:25+00:00
- Post Title: Carrier Command: Gaea Mission

Works great, thanks.. time to add Lara to the game
