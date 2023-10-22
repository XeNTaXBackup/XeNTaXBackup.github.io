## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-08T13:33:36+00:00
- Post Title: The Invincible Online GFPK

> Reply from chrrox
>
> start a new topic with a client download and a sample archive if you want help with the format.
Archives are the same as in Dragona and QueensBlade but without xoring filenames. Example attached.

@Edited: Attach removed.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-08T14:23:15+00:00
- Post Title: The Invincible Online GFPK

in this case it's enough that you take one of the 2 scripts made for the other games and add a # before the filexor command, like the following:

```
# filexor "0x78 0x6C 0x61 0x71 0x6A 0x23 0x65 0x6D 0x24 0x25 0x5E 0x66 0x6B 0x40 0x23 0x24 0x72 0x68 0x21 0x40 0x23 0x73 0x6B 0x40 0x23 0x24 0x21 0x00"
```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T14:34:35+00:00
- Post Title: The Invincible Online GFPK

It's not reading the paths properly
Other than that, same model format as their other two games.

Try extracting PC archive and you'll find it gives names, but the names are cut off and it's getting numbers at the end.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-08T14:43:24+00:00
- Post Title: The Invincible Online GFPK

Thanks aluigi. i trying but the extracted files without a name and directory

Example log:

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select the BMS script or plugin to use
- select the input archives/files to extract, type "" for whole folder and subfo
lders
- select the output folder where extracting the files
- open input file D:\BP\EngineRes\eng_res.gfpk
- open script D:\Projects\GameTools\Aluigi\QuickBMS\Scripts\GFPK_BP.bms
- set output folder D:\BP\EngineRes\Extracted

  offset   filesize   filename
------------------------------
  00001080 16512      00000000.dat
  00005100 22000      00000001.dat
  0000a6f0 1398256    00000002.dat

- 3 files found in 0 seconds

Press RETURN to quit
```
## Post #5
- Username: Ekey
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-08T18:10:27+00:00
- Post Title: The Invincible Online GFPK

the format is a little different.
can you post the full game client download link.

```
get files short
get null short
for i = 0 < files
get id long
putarray 0 i id
next i
for i = 0 < files
get id1 long
putarray 1 i id1
next i
for i = 0 < files
getarray OFFSET 1 i
if OFFSET == -1
getdstring null 0x310 #this is the recursive directory info but we can skip it in this game
endif
if OFFSET != -1
getdstring basename 0xF8
get SIZE long
get UNK01 long
get UNK02 long
getdstring NULL 0x2
getdstring NAME 0x20A
putarray 2 i SIZE
putarray 3 i NAME
endif
next i
savepos base
for i = 0 < files
getarray OFFSET 1 i
getarray SIZE 2 i
getarray NAME 3 i
math OFFSET + base
if NAME != 0
log NAME OFFSET SIZE
endif
next i

```
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T18:19:13+00:00
- Post Title: The Invincible Online GFPK

[http://bp.zcdn.co.kr/bp/Client/BPOnline ... 0_0_17.exe](http://bp.zcdn.co.kr/bp/Client/BPOnlineSetup_1_0_0_17.exe)
## Post #7
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-08-20T11:01:28+00:00
- Post Title: The Invincible Online GFPK

sorry for this necroposting but i've the same error of ekey.

I want to know if ekey or otherone succeded to extract from this different gfpk format...

p.s:finale the link of your client doesn't work...
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-20T16:17:32+00:00
- Post Title: The Invincible Online GFPK

Script work fine.

```
------------------------------
  00001080 16512      EngineRes\Tex\CircleShadow.dds
  00005100 22000      EngineRes\Tex\DefaultTex.dds
  0000a6f0 1398256    EngineRes\Tex\sun.dds

- 3 files found in 0 seconds
```
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-20T19:16:20+00:00
- Post Title: The Invincible Online GFPK

> Reply from Drawing
>
> sorry for this necroposting but i've the same error of ekey.

I want to know if ekey or otherone succeded to extract from this different gfpk format...

p.s:finale the link of your client doesn't work...

Did you use chrrox's script?

Check the client request thread in 3D section. Iaw posted a newer link cause they updated the client to some other version.
## Post #10
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-08-20T19:40:31+00:00
- Post Title: The Invincible Online GFPK

i've tried with chroox's script...
I run quick bms i chose the bms script, the file and the folder where export but i've this problem,
Quick ask me to put another name and if i put a name i got this error
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-20T20:29:22+00:00
- Post Title: The Invincible Online GFPK

Maybe in newest client packs now XORed.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-20T20:42:35+00:00
- Post Title: The Invincible Online GFPK

Maybe you can add in that filexor command that aluigi has lol
## Post #13
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-08-21T10:18:35+00:00
- Post Title: The Invincible Online GFPK

ok i've to add this: 
# filexor "0x78 0x6C 0x61 0x71 0x6A 0x23 0x65 0x6D 0x24 0x25 0x5E 0x66 0x6B 0x40 0x23 0x24 0x72 0x68 0x21 0x40 0x23 0x73 0x6B 0x40 0x23 0x24 0x21 0x00"

But where? in the bms script or where it asks me to put a new name?
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-21T14:05:04+00:00
- Post Title: The Invincible Online GFPK

after

```
get files short
get null short

```


add

```
filexor "0x78 0x6C 0x61 0x71 0x6A 0x23 0x65 0x6D 0x24 0x25 0x5E 0x66 0x6B 0x40 0x23 0x24 0x72 0x68 0x21 0x40 0x23 0x73 0x6B 0x40 0x23 0x24 0x21 0x00"
```
## Post #15
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-08-21T15:32:33+00:00
- Post Title: The Invincible Online GFPK

I've tried to unpack weapon.gfpk but it doesn't work.

This is weapon.gfpk if you want to try [http://www46.zippyshare.com/v/63895430/file.html](http://www46.zippyshare.com/v/63895430/file.html)
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-21T15:36:32+00:00
- Post Title: Re: The Invincible Online GFPK

Send me main executable from game with all DLL's in PM.
## Post #17
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-08-21T16:50:05+00:00
- Post Title: Re: The Invincible Online GFPK

ok
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-21T21:01:45+00:00
- Post Title: Re: The Invincible Online GFPK

So key for this game

```
0065D249    B8 506AB700      MOV EAX,BPClient.00B76A50                ; ASCII "qnfvovozldgkfkrn"

```


```
filexor "0x71 0x6E 0x66 0x76 0x6F 0x76 0x6F 0x7A 0x6C 0x64 0x67 0x6B 0x66 0x6B 0x72 0x6E"
```
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T21:48:12+00:00
- Post Title: Re: The Invincible Online GFPK

Here is the updated script. Supports both the unencrypted archives as well as the new ones.

```
goto 0x104
get files short
get unk byte
get flag byte

if flag != 0
  filexor "0x71 0x6E 0x66 0x76 0x6F 0x76 0x6F 0x7A 0x6C 0x64 0x67 0x6B 0x66 0x6B 0x72 0x6E 0x00"
endif

for i = 0 < files
  get id long
  putarray 0 i id
next i

for i = 0 < files
  get id1 long
  putarray 1 i id1
next i

for i = 0 < files
  getarray OFFSET 1 i
  if OFFSET == -1
    getdstring null 0x310 #this is the recursive directory info but we can skip it in this game
  endif
  if OFFSET != -1
    getdstring basename 0xF8
    get SIZE long
    get UNK01 long
    get UNK02 long
    getdstring NULL 0x2
    getdstring NAME 0x20A
    putarray 2 i SIZE
    putarray 3 i NAME
    print %SIZE%
  endif
next i

filexor ""
savepos base
for i = 0 < files
  getarray OFFSET 1 i
  getarray SIZE 2 i
  getarray NAME 3 i
  math OFFSET + base
  if NAME != 0
    log NAME OFFSET SIZE
  endif
next i


```
## Post #20
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-08-21T22:40:41+00:00
- Post Title: Re: The Invincible Online GFPK

thanks a lot guys ç.ç
