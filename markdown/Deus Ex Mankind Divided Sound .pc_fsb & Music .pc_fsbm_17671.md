## Post #1
- Username: y1560730
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 07, 2018 7:15 am
- Post datetime: 2018-02-06T23:28:42+00:00
- Post Title: Deus Ex: Mankind Divided Sound .pc_fsb & Music .pc_fsbm

I want to extract music from the .pc_fsbm files that are located in Deus Ex Mankind Divided\runtime. There are four .pc_fsb files (77.7 MB) and 143 .pc_fsbm files (539 MB).

For example:
A2E93924B183A3AFF36579340E3ACFDC.pc_fsbm

I drag the file into [http://aezay.dk/aezay/fsbextractor/](http://aezay.dk/aezay/fsbextractor/)

```
Failed to open file. Content may be encrypted, or it's not a valid FSB file format (FileID: 0x4653424D)
```


I use File/Scan for all Headers



I right-click the file and extract it to c_sting_bank_v1.ogg

VLC can't play the file. drgunpack5 (dup570beta) can't find anything.

I try fsbext from [http://aluigi.altervista.org/search.php?src=fsbext](http://aluigi.altervista.org/search.php?src=fsbext)

```

FSB files extractor 0.3.8a
by Luigi Auriemma
e-mail: me@aluigi.org
web:    aluigi.org

- input file:   A2E93924B183A3AFF36579340E3ACFDC.pc_fsbm
- probably the file uses encryption, insert the needed keyword:
  type ? for viewing the hex dump of the first 176 bytes of the file because
  it's possible to see part of the plain-text password in the encrypted file!
  ?
- encryption type 1
4d 42 53 46 00 00 00 00 00 00 00 00 40 ea 01 00   MBSF........@...
ff ff ff ff ff ff ff ff 46 53 42 35 01 00 00 00   ........FSB5....
01 00 00 00 5c 00 00 00 28 00 00 00 80 e9 01 00   ....\...(.......
0f 00 00 00 01 00 00 00 00 00 00 00 08 49 0c 1e   .............I..
f8 0a e9 ca 32 12 88 7d 04 f4 21 60 7c 1a ec f5   ....2..}..!`|...
93 44 6b a3 33 00 00 00 24 c9 1a 00 a0 00 00 16   .Dk.3...$.......
ce 59 aa 38 48 00 00 00 c0 b7 00 00 e9 33 00 00   .Y.8H........3..
40 76 01 00 5f 68 00 00 00 32 02 00 b6 a0 00 00   @v.._h...2......
80 ed 02 00 b4 dc 00 00 40 a8 03 00 6f 15 01 00   ........@...o...
40 64 04 00 41 48 01 00 40 20 05 00 95 7b 01 00   @d..AH..@ ...{..
40 d8 05 00 5c ad 01 00 40 94 06 00 57 e0 01 00   @...\...@...W...

- encryption type 2
f4 11 88 24 00 00 00 00 00 00 00 00 02 57 80 00   ...$.........W..
ff ff ff ff ff ff ff ff 62 ca 42 ac 80 00 00 00   ........b.B.....
80 00 00 00 3a 00 00 00 14 00 00 00 01 97 80 00   ....:...........
f0 00 00 00 80 00 00 00 00 00 00 00 10 92 30 78   ..............0x
1f 50 97 53 4c 48 11 be 20 2f 84 06 3e 58 37 af   .P.SLH.. /..>X7.
c9 22 d6 c5 cc 00 00 00 24 93 58 00 05 00 00 68   ."......$.X....h
73 9a 55 1c 12 00 00 00 03 ed 00 00 97 cc 00 00   s.U.............
02 6e 80 00 fa 16 00 00 00 4c 40 00 6d 05 00 00   .n.......L@.m...
01 b7 40 00 2d 3b 00 00 02 15 c0 00 f6 a8 80 00   ..@.-;..........
02 26 20 00 82 12 80 00 02 04 a0 00 a9 de 80 00   .& .............
02 1b a0 00 3a b5 80 00 02 29 60 00 ea 07 80 00   ....:....)`.....

- probably the file uses encryption, insert the needed keyword:
  type ? for viewing the hex dump of the first 176 bytes of the file because
  it's possible to see part of the plain-text password in the encrypted file!

- use encryption type -1

Error: your password seems wrong
```


I am at a loss.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-02-09T01:45:33+00:00
- Post Title: Deus Ex: Mankind Divided Sound .pc_fsb & Music .pc_fsbm

Uploading a sample of the files helps
## Post #3
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2018-02-10T04:51:13+00:00
- Post Title: Deus Ex: Mankind Divided Sound .pc_fsb & Music .pc_fsbm

Try trimming the header up to “FSB5” and see if that works.
## Post #4
- Username: skyboxeye
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 17, 2017 7:24 am
- Post datetime: 2018-11-25T22:54:39+00:00
- Post Title: Deus Ex: Mankind Divided Sound .pc_fsb & Music .pc_fsbm

Use this QuickBMS script on the .pc_fsbm files:

```
    goto OFFSET
    findloc OFFSET string "FSB5"
    goto OFFSET
    getdstring FSB_SIGN 4   # FSOUND_FSB_HEADER_FSB5 (fsb.h)
    get version long
    get numsamples long
    get shdrsize long
    get namesize long
    get datasize long
    xmath SIZE "0x3c + shdrsize + namesize + datasize"
    get NAME filename
    set NAME1 long OFFSET
    string NAME1 p= "%08x" NAME1
    set NAME2 long SIZE
    string NAME2 p= "%08x" NAME2
    string NAME += "_"
    string NAME += NAME1
    string NAME += "_"
    string NAME += NAME2
    string NAME += ".fsb"
    log NAME OFFSET SIZE
next OFFSET + SIZE

```


And then use the scripts in [this project]([https://github.com/HearthSim/python-fsb ... ag/b7bf605](https://github.com/HearthSim/python-fsb5/releases/tag/b7bf605)) to get at the .ogg files.

Bonus:
To make conversion easier, you can do it in batch (I'm on Windows):

```
    "C:\Program Files\Python36\python.exe" extract.py --verbose "%%f"
)

```

Copy-paste the above into a .bat file and run it from the Windows command prompt.
## Post #5
- Username: Naomi9
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 30, 2018 6:46 pm
- Post datetime: 2018-11-30T11:21:13+00:00
- Post Title: Deus Ex: Mankind Divided Sound .pc_fsb & Music .pc_fsbm

> Reply from brendan19
>
> Uploading a sample of the files helps
Totally agreed with you
