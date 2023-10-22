## Post #1
- Username: alon
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-30T19:26:54+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

[http://pgdp.channel.or.jp/gundam/ps3/](http://pgdp.channel.or.jp/gundam/ps3/)

```
#Mobile Suit Gundam Battle Operation
endian big
getdstring magic 8
get files short
get unk1 short
get unk2 long
savepos ftbl
for i = 0 < files
goto ftbl
get offset long
math offset + 0x19800
get size long
get null long
get secsize short
get nsize short
savepos tmp
get null byte
if null != 0
goto tmp
endif
getdstring name nsize
math ftbl + secsize
log name offset size
next i
```
## Post #2
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-07-03T18:18:34+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

Help me how to unpack fpk file.

```
6D 65 64 69 61 66 69 72 65 2E 63 6F 6D 2F 3F 36 61 68 6E 68 78 37 30 78 34 7A 71 64 72 33
```
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-04T05:02:02+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

Data looks really strange. It doesn't look compressed or encrypted... looks like archive starts at XMB section but there's a bunch of data at the top of that. look easy to you chrrox? hmmm where have I heard of xmb before....?
## Post #4
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-07-04T14:43:15+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

Everything just seems so strange.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-04T14:45:07+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

i do not have the game to look at it someone just sent me a cut section from the file and i made the extractor.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-07T23:00:49+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

for the BfPk files I have an experimental script.
translated: it works for extracting some files, then something with the offset becomes wrong.

```
idstring "BfPk"
get DUMMY short
get OFFSET short
get FILES short
get DUMMY byte
get DUMMY short
math OFFSET += 1
math OFFSET *= 0x800

for i = 0 < FILES
    savepos MYOFF
    get ENTRYSZ short
    reverseshort ENTRYSZ
    get NAMESZ short
    reverseshort NAMESZ
    getdstring NAME NAMESZ
    math MYOFF += ENTRYSZ
    math MYOFF -= 13
    goto MYOFF
    get CRC long
    get SIZE long
    get DUMMY long
    get DUMMY byte

    if NAME != ""
        math OFFSET x= 0x800
        log NAME OFFSET SIZE
        math OFFSET += SIZE
    endif
next i
```
## Post #7
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-08-23T07:23:27+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

I extracted some file half-manually.
The epk file includes XMB. 

```
68 74 74 70 3A 2F 2F 77 77 77 2E 6D 65 64 69 61 66 69 72 65 2E 63 6F 6D 2F 3F 66 74 62 36 66 31 76 74 6E 64 32 76 39 68 32
```
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-23T15:56:57+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

Send any EPK
## Post #9
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-08-23T18:05:38+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

I need a little help.
How to decompress a ZLBB compression.

```
6D 65 64 69 61 66 69 72 65 2E 63 6F 6D 2F 3F 6B 67 71 33 75 64 74 6B 31 34 39 78 73 78 70
```

Open with Hex Editor.
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-08-23T19:18:50+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

for ZLBB header

```
# by Fatduck     Aug 2012
# http://aluigi.org/quickbms.htm

idstring "ZLBB"
endian big

get BLKSIZE long
get NUMPART long
get UKN long
get DATASTART long
get PACKSIZE long
get UNPACKSIZE long

goto 0x40
log MEMORY_FILE 0 0

comtype UNZIP_DYNAMIC

for i = 0 < NUMPART
   get CPARTSIZE word
   get DMY short
   get OFSPART long
   append 
   clog MEMORY_FILE OFSPART CPARTSIZE BLKSIZE
   append
next i

get USIZE asize MEMORY_FILE
get RESNAME FILENAME
log RESNAME 0 USIZE MEMORY_FILE
```


for epk/fpk

```
# by Fatduck     Aug 2012
# http://aluigi.org/quickbms.htm

idstring "FPK\0"
endian big
get NUMRES long
get OFSIDX long
get OFSDATA long
goto OFSIDX
for i = 0 < NUMRES
   getdstring RESNAME 0x40
   get OFSRES long
   get LENRES long
   get BLKRES long
   get NULL long   
   math OFSRES += OFSDATA
   log RESNAME OFSRES LENRES
next i
```
## Post #11
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-08-24T06:39:47+00:00
- Post Title: Mobile Suit Gundam Battle Operation (PS3) (arb)

> Reply from fatduck
>
> for ZLBB header
Code: Select all# Game: Mobile Suit Gundam Battle Operation [PS3/PSN]
# by Fatduck     Aug 2012
# http://aluigi.org/quickbms.htm

idstring "ZLBB"
endian big

get BLKSIZE long
get NUMPART long
get UKN long
get DATASTART long
get PACKSIZE long
get UNPACKSIZE long

goto 0x40
log MEMORY_FILE 0 0

comtype UNZIP_DYNAMIC

for i = 0 < NUMPART
   get CPARTSIZE word
   get DMY short
   get OFSPART long
   append 
   clog MEMORY_FILE OFSPART CPARTSIZE BLKSIZE
   append
next i

get USIZE asize MEMORY_FILE
get RESNAME FILENAME
log RESNAME 0 USIZE MEMORY_FILE

for epk/fpk
Code: Select all# Game: Mobile Suit Gundam Battle Operation [PS3/PSN]
# by Fatduck     Aug 2012
# http://aluigi.org/quickbms.htm

idstring "FPK\0"
endian big
get NUMRES long
get OFSIDX long
get OFSDATA long
goto OFSIDX
for i = 0 < NUMRES
   getdstring RESNAME 0x40
   get OFSRES long
   get LENRES long
   get BLKRES long
   get NULL long   
   math OFSRES += OFSDATA
   log RESNAME OFSRES LENRES
next i
Thanks, fatduck
