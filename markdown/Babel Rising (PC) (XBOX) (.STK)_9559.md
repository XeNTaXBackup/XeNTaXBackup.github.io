## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-28T12:04:25+00:00
- Post Title: Babel Rising (PC) (XBOX) (*.STK)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

goto 0xc
get XORKEY long
get FILES long
get DUMMY byte
get TABLESIZE long

set KEY "0x23 0x3B 0x5C 0x42"  # PC - BR3D_High.stk
#set KEY "0x03 0x81 0xE6 0x47"  # XBOX - Babel3d.stk
#set KEY "0x9E 0xB9 0xD0 0x77"  # XBOX - S3DShaders.stk

for i = 0 < FILES
   filexor KEY
   get NSIZE long
   getdstring NAME NSIZE
   get OFFSET long
   math OFFSET += TABLESIZE
   get ZSIZE long
   get SIZE long
   get CRC32 long
   get FLAG short
   filexor KEY OFFSET
 if ZSIZE == SIZE
    log NAME OFFSET SIZE
 else
   clog NAME OFFSET ZSIZE SIZE
 endif
    savepos TMP
    if TMP == TABLESIZE
  cleanexit
 endif
next i
```
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-28T12:46:26+00:00
- Post Title: Babel Rising (PC) (XBOX) (*.STK)

Ok. Finished
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-28T14:01:18+00:00
- Post Title: Babel Rising (PC) (XBOX) (*.STK)

> Reply from Ekey
>
> Ok. Finished
hey ekey if i give you the files for the xbox version would you be able to add it to the script?
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-28T15:24:53+00:00
- Post Title: Babel Rising (PC) (XBOX) (*.STK)

> Reply from lllccc
>
> Ekey wrote:Ok. Finished 
hey ekey if i give you the files for the xbox version would you be able to add it to the script?
Updated script. If you need unpack files for xbox set # for PC and remove # for XBOX like this.

```
set KEY "0x03 0x81 0xE6 0x47"  # XBOX - Babel3d.stk
#set KEY "0x9E 0xB9 0xD0 0x77"  # XBOX - S3DShaders.stk
```


For each archive different key.
## Post #5
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-08-28T18:07:19+00:00
- Post Title: Babel Rising (PC) (XBOX) (*.STK)

awesome, thank you a lot ekey!
## Post #6
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-09-01T20:02:21+00:00
- Post Title: Babel Rising (PC) (XBOX) (*.STK)

> Reply from Ekey
>
> lllccc wrote:Ekey wrote:Ok. Finished 
hey ekey if i give you the files for the xbox version would you be able to add it to the script?
Updated script. If you need unpack files for xbox set # for PC and remove # for XBOX like this.
Code: Select all#set KEY "0x23 0x3B 0x5C 0x42"  # PC - BR3D_High.stk
set KEY "0x03 0x81 0xE6 0x47"  # XBOX - Babel3d.stk
#set KEY "0x9E 0xB9 0xD0 0x77"  # XBOX - S3DShaders.stk

For each archive different key.
 thank you soo much
## Post #7
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-09-02T17:18:56+00:00
- Post Title: Babel Rising (PC) (XBOX) (*.STK)

hey so you know it doesnt work for the xbox i get this error's






*never mind i just found out sorry for the post*

i just wanted to know is this repackable?

okay i got it to repack thanks soo much for this
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-09-09T16:06:45+00:00
- Post Title: Babel Rising (PC) (XBOX) (*.STK)

You need add comment (#) for PC and remove comment (#) for XBOX 

```
#set KEY "0x03 0x81 0xE6 0x47"  # XBOX - Babel3d.stk
set KEY "0x9E 0xB9 0xD0 0x77"  # XBOX - S3DShaders.stk
```
