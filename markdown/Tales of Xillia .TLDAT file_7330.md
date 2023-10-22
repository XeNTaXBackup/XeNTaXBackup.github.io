## Post #1
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2011-09-10T03:13:24+00:00
- Post Title: Tales of Xillia .TLDAT file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-10T15:14:25+00:00
- Post Title: Tales of Xillia .TLDAT file

Quickbms script
there are a lot of files.
use the 4gb quickbms.

```
Open FDSE "TLFILE.TLDAT" 1
endian big
comtype MSF
goto 0xC
get files long
goto 0x1248D8
set counter 0
for j = 0 < files
get size longlong
get zsize longlong
get offset longlong
get hash long
getdstring ext 8
get six long
if ext == "TOHRCB"

elif ext == "TOSHPB"

elif ext == "TOSHPS"

elif ext == "TOSHPP"

elif ext == "TOMDLB"

elif ext == "TOHRCB"

elif ext == "TOTEXP"

else
math counter + 1
endif
if zsize == size
set name counter
string name + .
string name + ext
log name offset size 1
else
set name counter
string name + .
string name + ext
endian little
log MEMORY_FILE4 offset zsize 1
get TLZC long MEMORY_FILE4
get version long MEMORY_FILE4
get Tzsize long MEMORY_FILE4
get Tsize long MEMORY_FILE4
getdstring null 9 MEMORY_FILE4
get ChunkSize long MEMORY_FILE4
set files2 Tsize
math files2 / ChunkSize
set test files2
math test * chunksize
if test != Tsize
math files2 + 1
endif
for i = 0 < files2
get zsize2 short MEMORY_FILE4
putarray 0 i zsize2
next i
comtype msf
savepos offset MEMORY_FILE4
for i = 0 < files2
getarray zsize2 0 i
append
clog MEMORY_FILE5 offset zsize2 0x10000 MEMORY_FILE4
append
math offset + zsize2
goto offset MEMORY_FILE4
next i
append
log name 0 Tsize MEMORY_FILE5
append
set MEMORY_FILE4 ""
set MEMORY_FILE5 ""
endian big
endif
next j

```
## Post #3
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2011-09-10T23:33:59+00:00
- Post Title: Tales of Xillia .TLDAT file

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-11T01:00:44+00:00
- Post Title: Tales of Xillia .TLDAT file

try the script now i updated one thing.
## Post #5
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2011-09-11T02:12:22+00:00
- Post Title: Tales of Xillia .TLDAT file

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-11T02:17:51+00:00
- Post Title: Tales of Xillia .TLDAT file

yeah they are models.
and the file right before them tells you how to open them.
im gonna post a texture converter soon testing it out.
## Post #7
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2011-09-11T02:26:04+00:00
- Post Title: Tales of Xillia .TLDAT file

Ohhh, that makes sense! I hadn't thought about that, it makes sense with the .*b .*p files. 

I really appreciate all the work you're doing, looking forward to seeing the cut in textures!
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-11T03:45:51+00:00
- Post Title: Tales of Xillia .TLDAT file

I may have to adjust my first script one more time but that is OK anyway here is a sample to hold people over.
## Post #9
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2011-09-11T04:01:54+00:00
- Post Title: Tales of Xillia .TLDAT file

Man, I'm so excited! For once i wont have to use an emulator to rip cut ins
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-11T14:02:07+00:00
- Post Title: Tales of Xillia .TLDAT file

Ok here is a new script to extract the game you need to use this new one i edited the post above.

also here is what you need to extract textures.
just drag the extracted folder into the bat file and edit the bat file first to point to where you want your files.
i used 3 programs to open the dds files.
The compressonator
infraview
and windows texture viewer.
[18018.png](https://xentaxbackup.github.io/file/4707_18018.png)
## Post #11
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2011-09-11T16:18:59+00:00
- Post Title: Tales of Xillia .TLDAT file

Awesome, everything worked perfectly, thanks!
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-11T16:24:31+00:00
- Post Title: Tales of Xillia .TLDAT file

I updated the script to fix one image type download the new one.
[17244.PNG](https://xentaxbackup.github.io/file/4710_17244.PNG)

[texv2.rar](https://xentaxbackup.github.io/file/4709_texv2.rar)
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-11T21:38:55+00:00
- Post Title: Tales of Xillia .TLDAT file

one last post this fixes the problem with a few images.

```
open FDDE TOTEXB 1
endian big
get name basename
string name + .dds
get MTEX long 1
get unk01 long 1
get unk02 long 1
get unk03 short 1
get width short 1
get height short 1
get null short 1
get type byte 1
get mips byte 1
get null short 1
get null long 1
get size asize
math size - 0x100
endian little
set MEMORY_FILE2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
if type == 0xA5
set MEMORY_FILE2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x00\x00\x00\x04\x00\x00\x08\x07\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x41\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\xFF\x00\x00\xFF\x00\x00\xFF\x00\x00\x00\x00\x00\x00\xFF\x02\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
endif
putVarChr MEMORY_FILE2 0x10 width long
putVarChr MEMORY_FILE2 0xC height long
if type == 0x88
putVarChr MEMORY_FILE2 0x57 0x35 byte
endif
if type == 0xA8
putVarChr MEMORY_FILE2 0x57 0x35 byte
endif
if type == 0x86
putVarChr MEMORY_FILE2 0x57 0x31 byte
endif
putVarChr 
append
goto 0xF4
get test1 longlong
goto 0
if type == 0xA5
if test1 != 0
math size + 0x100
set tmp size
math tmp / 4
else
set tmp size
math tmp / 4
goto 0x100
endif
for i = 0 < tmp
set a i
math a * 4
endian little
get test long
endian big
putVarChr MEMORY_FILE3 a test long
next i
for i = 0 < 64
set a i
math a * 4
math a + size
putVarChr MEMORY_FILE3 a 0 long
next i
math size + 0x100
log MEMORY_FILE2 0 size MEMORY_FILE3
else if test1 != 0
math size + 0x100
log MEMORY_FILE2 0 size
else
log MEMORY_FILE2 0x100 size
endif
append
math size + 0x80
log name 0 size MEMORY_FILE2

```
## Post #14
- Username: Itadaki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 12, 2011 4:49 am
- Post datetime: 2011-09-12T01:44:57+00:00
- Post Title: Tales of Xillia .TLDAT file

Forgive me for asking a stupid question but when using QuickBMS I get the "Error: Invalid Command "putVarchar" or arguments 0 line 35" right after I chose the output folder. Where exactly did I go wrong? I'm a little new at this... -_-;
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-12T02:59:50+00:00
- Post Title: Tales of Xillia .TLDAT file

update quickbms
## Post #16
- Username: buckybean
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 17, 2011 12:01 pm
- Post datetime: 2011-09-12T22:47:36+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

Everything worked out like a champ.  

Thank you OP and chrrox.
## Post #17
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-12T22:50:08+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

op?
## Post #18
- Username: buckybean
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 17, 2011 12:01 pm
- Post datetime: 2011-09-12T23:18:07+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

Hehe, I meant Original Poster.
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-12T23:34:33+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

ah ok well thanks for your thanks but the original poster dint really do anything i dint even use the files he posted was already working on the game.
## Post #20
- Username: buckybean
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 17, 2011 12:01 pm
- Post datetime: 2011-09-15T16:19:21+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

I see I see. I thought you started on it after you saw the files posted by the OP. Anyway, thanks!
## Post #21
- Username: DaniGoon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 20, 2011 9:09 am
- Post datetime: 2011-09-21T15:50:06+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

Wow, thanks for providing these scripts, chrrox; everything worked great!

> Reply from chrrox
>
> i used 3 programs to open the dds files.
The compressonator
infraview
and windows texture viewer.I noticed that several of the images show up with working alpha channels in Windows Texture Viewer, but when using The Compressonator to save in a different format, the alpha channel seems lost? I was able to keep it in some images, but not in others, such as the cut-ins. Is there anything I can do about this?

> Reply from chrrox
>
> ah ok well thanks for your thanks but the original poster dint really do anything i dint even use the files he posted was already working on the game.By any chance, were you able to find the textures for the items? This was the main thing I was hoping to find, but I didn't have any luck... Thanks again, either way.
## Post #22
- Username: ultima
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 08, 2009 12:37 pm
- Post datetime: 2014-06-10T07:00:03+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

I get an error when I try to extract:

```
 TLFILE_ext

QuickBMS generic files extractor and reimporter 0.5.31a (64bit test)
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
        (Apr  6 2014 - 01:14:25)

                  http://quickbms.aluigi.org
               http://twitter.com/luigi_auriemma

- open input file E:\PS3\Tales of Xillia\extract\TLFILE.TLDAT
- open script TOX_TLDAT.bms
- set output folder TLFILE_ext

  offset           filesize   filename
--------------------------------------
- enter in folder E:\PS3\Tales of Xillia\extract
  coverage file 0     0%   0          2425378503
- open input file E:\PS3\Tales of Xillia\extract\FILEHEADER.TOFHDB
- enter in folder E:\PS3\Tales of Xillia\extract
- open input file E:\PS3\Tales of Xillia\extract\TLFILE.TLDAT

Error: [myfseek] the offset 0xfaa2be1a000197f6 in the file 1 can't be reached

E:\PS3\Tales of Xillia\extract>pause
Appuyez sur une touche pour continuer...
```
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-06-10T12:30:10+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

what version of the game are you using.
also make sure you use the 64 bit quickbms.
## Post #24
- Username: ultima
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 08, 2009 12:37 pm
- Post datetime: 2014-06-10T22:22:35+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

I tried on European French version (BLES01815) and on European French version UNDUB, I have exactly the same error.
## Post #25
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-06-11T03:49:40+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

This was for the japanese version i think
you will have to adjust this line for your version
goto 0x1248D8
## Post #26
- Username: ultima
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 08, 2009 12:37 pm
- Post datetime: 2014-06-11T05:42:28+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

Oh ok. Thank's 

Is it possible to make a script for the dlc?

[https://www.mediafire.com/?kh9b7a1dufwlyhk](https://www.mediafire.com/?kh9b7a1dufwlyhk)


Edit : I decrypted the edat file, and I get a dat file. 
Maybe is it possible Decompressed the archive?

[https://www.mediafire.com/?9969v6upqaeb8eu](https://www.mediafire.com/?9969v6upqaeb8eu)
## Post #27
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2014-09-12T14:31:08+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

Where's you find this number i try on 2eur
## Post #28
- Username: Paladin946
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 19, 2014 7:49 pm
- Post datetime: 2014-09-23T15:42:32+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

i need know how can find the number too... i have the same error
## Post #29
- Username: techchol
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 26, 2014 3:22 am
- Post datetime: 2014-10-22T22:38:49+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

I have the same problem. need to know how can I find that line too.
## Post #30
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-10-23T02:28:14+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

near the end of the file you will see the file extentions in the file table
like TOSHPB , TOSHPP, TOMDLB
you have to go before the first one of those
28 bytes before that first one is where you need to set the script to go to.
## Post #31
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2014-10-23T10:05:33+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

thank's i have try to look but noob in hexa i will see the that's other time
## Post #32
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-01-16T19:03:13+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

I get this error when I run the script, I've got the most recent version of QuickBMS, so I'm not really sure why it doesn't want to work.

This is the European version, but I don't think that has anything to do with the errors since its a source error in quickbms according to the output.

Anyone have any advice?
## Post #33
- Username: rballad
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 11, 2014 9:40 am
- Post datetime: 2015-05-31T13:31:26+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

Chroxx,sorry for being a noob. I want to ask how to open the models?

will you support the dlcs?  because all the good and sexy costumes are DLCs. I added files of japanese dlc
[http://www.mediafire.com/download/7y6ll ... iajapan.7z](http://www.mediafire.com/download/7y6ll4ywy4zgckb/xilliajapan.7z)
## Post #34
- Username: Gokusaaan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 26, 2016 3:16 pm
- Post datetime: 2016-03-26T07:43:02+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

How open lzma files when u extract TLDAT
## Post #35
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-05-04T08:27:31+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

Can someone please explain how to unpack these files ?
## Post #36
- Username: Himawari Mawari
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 18, 2021 3:03 pm
- Post datetime: 2021-10-15T09:02:50+00:00
- Post Title: Re: Tales of Xillia .TLDAT file

I tried to extract the the file but it end up with this error:

```
by Luigi Auriemma
e-mail: me@aluigi.org
web:    aluigi.org
        (Apr  5 2021 - 13:47:43)

                          quickbms.com  Homepage
                            zenhax.com  ZenHAX Forum
                     @zenhax @quickbms  Twitter & Scripts

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select BMS script. type ? for using the content of clipboard like a script
- select input archives/files, type * for the whole folder and subfolders
- select output folder where extracting files
- open input file H:\BLES01815-[Tales of Xillia]\PS3_GAME\USRDIR\TLFILE.TLDAT
- open script D:\Favorite Animes\Datamines\QuickBMS\shellshock_nam67.bms
- set output folder H:\BLES01815-[Tales of Xillia]\PS3_GAME\USRDIR

  offset           filesize   filename
--------------------------------------
- enter in folder H:\BLES01815-[Tales of Xillia]\PS3_GAME\USRDIR
  coverage file 0     0%   0          2366031463 . offset 0000000000000000
- open input file H:\BLES01815-[Tales of Xillia]\PS3_GAME\USRDIR\ASSETS.DAT

- error in src\file.c line 615: fdnum_open()
Error: No such file or directory

Last script line before the error or that produced the error:
  3   open FDSE "ASSETS.DAT"

Press ENTER or close the window to quit
```


Can you find out what's happening? =
