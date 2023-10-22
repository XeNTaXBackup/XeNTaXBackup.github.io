## Post #1
- Username: Qova
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 21, 2015 6:39 am
- Post datetime: 2015-06-20T22:47:37+00:00
- Post Title: Tianyu Revelations Online (CH)

I'm been looking at the files and noticed it's in a .PG format. So I roamed around ZenHax and here and found an older version that Ekey and Aluigi created. However these were the keys for the CBT, the game is now in OBT and has changed quite a bit. By looking at other posts about this I'm thinking it need new "keys" in order for it to unpack. I'm not really sure what to do from here.

```
#   Dragon Sword, JianLong, Revelation
#   thanks Ekey :)
# script for QuickBMS http://quickbms.aluigi.org

comtype lzo1x

math VER = 0
get MAGIC long
get dwTotalFiles long
get dwTableOffset long
    math XOR_FILES = 0
    math XOR_OFFSET = 0
    math XOR1 = 0
    math XOR2 = 0
    math XOR3 = 0
if MAGIC == 0x62616731
    math XOR_FILES = 0xe7356461
    math XOR_OFFSET = 0xcb449442
    math XOR1 = 0x698346BD
    math XOR2 = 0x867389FE
    math XOR3 = 0xABEDC59D
elif MAGIC == 0x62616732
    math VER = 1
    math XOR_FILES = 0x27252421
    math XOR_OFFSET = 0x3b343432
    math XOR1 = 0x5953565D
    math XOR2 = 0x6663696E
    math XOR3 = 0x7B7D757D
elif MAGIC == 0x70677479
    math VER = 1
    math XOR_FILES = 0x20141203
    math XOR_OFFSET = 0x6F61A5EA
else
    print "Error: unsupported magic signature %MAGIC|x%"
    cleanexit
endif
math dwTotalFiles  ^ XOR_FILES
math dwTableOffset ^ XOR_OFFSET

if MAGIC == 0x70677479
    encryption aes "\x51\x04\xcf\x12\x17\x97\xcb\xce\xd6\x33\xa1\x90\xd4\xff\xf4\xbf"
endif
xmath TMP "dwTotalFiles * (4 * 6)"  // 6 or more elements for the future
get TMP2 asize
math TMP2 -= dwTableOffset
if TMP u> TMP2
    math TMP = TMP2
endif
log MEMORY_FILE dwTableOffset TMP
encryption "" ""

for i = 0 < dwTotalFiles
    savepos ENTRY_OFF MEMORY_FILE

    math ENTRY_OFF += dwTableOffset
    if MAGIC == 0x70677479
        math ENTRY_OFF = 0
    endif

    get NAME_CRC long MEMORY_FILE
    xmath NAME_CRC "NAME_CRC ^ ENTRY_OFF ^ XOR1"

    if VER >= 1
        get NAME_CRC2 long MEMORY_FILE  # ???
    endif

    get OFFSET long MEMORY_FILE
    xmath OFFSET "OFFSET ^ ENTRY_OFF ^ XOR2"

    get ZSIZE long MEMORY_FILE
    xmath ZSIZE "ZSIZE ^ ENTRY_OFF ^ XOR3"

    goto OFFSET
    math ZIP = 0
    if ZSIZE >= 0x20
        getdstring DUMMY 0x18
        if MAGIC == 0x70677479
            math ZIP = 0x5a5a5a5a
        else
            get ZIP long
        endif
        if ZIP == 0x5a5a5a5a
            get SIZE long
        endif
    endif

    if MAGIC == 0x70677479
        filexor 0xd7
    endif

    if ZIP == 0x5a5a5a5a
        savepos OFFSET
        clog "" OFFSET ZSIZE SIZE
    else
        log "" OFFSET ZSIZE
    endif

    filexor ""
next i

```
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-06-24T18:08:43+00:00
- Post Title: Tianyu Revelations Online (CH)

W.I.P - Now unpacker can detect file names.

Edited: Outdated
## Post #3
- Username: island2008
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 15, 2014 6:28 pm
- Post datetime: 2015-06-25T04:42:55+00:00
- Post Title: Tianyu Revelations Online (CH)

Great Ekey,
the model & textures of this game is not good enough .they kill the d3dx9.dll  of ripper tools can someone know how to make d3dx9.dll useable? that is an easy way to get the model
## Post #4
- Username: OutSide
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 12, 2013 9:39 pm
- Post datetime: 2016-06-07T09:49:51+00:00
- Post Title: Tianyu Revelations Online (CH)

Bump on this. @Ekey. Any news with your unpacker?
