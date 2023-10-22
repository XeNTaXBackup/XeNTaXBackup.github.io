## Post #1
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-11-27T17:58:01+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

Hi all,

I have attached 2 archives from 

Fast And Furious Tokio Drift and Street Racing Syndicate

PS2 Games below, created by Namco and published in nearly the same time (2006/ 2007).

Both games uses the same file structure: The ARCHIVE.AR file is what the name says an archive. Another file, called CDFILES.DAT and stored in the same game directory, seems to be an File Allocation Table file.

Both archive.ar and both cdfiles.dat have the same name, but the file headers are different, therefore it could be that they were versions of the same thing.

Please, can anyone find out the format specifications of the 2 archive.ar archives?

If there were common parts, maybe it is possible that one script works with both (or more) Namco games with small modifications. A really good imagination for the future.

I'm a newbie, so can anyone help me plz and create BMS scripts for these games? 

* --- *


Thanks in advance,
Andreas
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-29T00:02:58+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

taking a look
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-29T11:35:12+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

the extraction of the files is trivial, the problem is their name and the directory tree which is more boring/complex.
so if you don't care about the names (they will have a sequential numeric name) the following script does the job:

*edit* use the subsequent scripts
## Post #4
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-12-01T18:06:23+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

Hi,

for Fast and Furious the script should work, but extracting Street Racing Syndicate's archive.ar file brings some errors. First of all quickbms searches for an archive called IVE.AR . So I have renamed the file in ive.ar . After that the program starts extracting and ends after 12 files (248MB). The size of archive.ar is 2,9 GB. I have attached the error screenshots.

For all that, many thanks for offering your time.

Bye, Andreas
[errors_srs_archive_ar.jpg](https://xentaxbackup.github.io/file/2580_errors_srs_archive_ar.jpg)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-01T18:55:02+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

about the name of the file it's correct, I programmed the script for using the name reported inside cdfiles.dat.
for the other problem I suppose that this archive contains more sub-archives but without having the file for me is impossible to know or guess if that's true and how is handled this data.
can you upload this cdfiles.dat?
## Post #6
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-12-01T19:40:56+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-01T20:04:18+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

ops my error, the following one should work (obviously I have used again a work-around but works at least for these 2 files):

```
#open FDSE "ARCHIVE.AR"  1

get DUMMY long
get BLAH long
goto 4
for i = 0 < BLAH
    get DUMMY long
    get DUMMY long
next i
get FILES long
print "XXX %FILES%"
get DUMMY long
get DUMMY long
get ENTRIES long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
getdstring NAME 12
open FDSE NAME  1

math TMP = FILES
math TMP *= 4
savepos OFFSET
log MEMORY_FILE OFFSET TMP  # offsets
math OFFSET += TMP
log MEMORY_FILE2 OFFSET TMP # sizes

for i = 0 < FILES
    get OFFSET long MEMORY_FILE
    math OFFSET *= 8
    get SIZE long MEMORY_FILE2
    log "" OFFSET SIZE 1
next i
```
## Post #8
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-12-02T19:14:39+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

@aluigi

I've tried it with both game archive.ar's and it works.

Thanks, good job!
## Post #9
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-05-31T04:37:02+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

After unpacking, I got a lot of files. How to change the font of the game? Who can analyze the text .LDA and font .ARC files? Who can make a script or converter?
Thanks!
P.S. Sorry for my bad English.
[.lda_text_and_.arc_fonts_files.rar](https://xentaxbackup.github.io/file/7406_.lda_text_and_.arc_fonts_files.rar)
## Post #10
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-07-01T12:28:24+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

I can't found the script on any site   
I need to extract the archive.ar for Street Racing Syndicate
## Post #11
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-07-01T19:30:32+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

> Reply from KarinFutoGT
>
> I can't found the script on any site   
I need to extract the archive.ar for Street Racing Syndicate

> Reply from aluigi
>
> ops my error, the following one should work (obviously I have used again a work-around but works at least for these 2 files):
Code: Select allopen FDSE "CDFILES.DAT" 0
#open FDSE "ARCHIVE.AR"  1

get DUMMY long
get BLAH long
goto 4
for i = 0 < BLAH
    get DUMMY long
    get DUMMY long
next i
get FILES long
print "XXX %FILES%"
get DUMMY long
get DUMMY long
get ENTRIES long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
getdstring NAME 12
open FDSE NAME  1

math TMP = FILES
math TMP *= 4
savepos OFFSET
log MEMORY_FILE OFFSET TMP  # offsets
math OFFSET += TMP
log MEMORY_FILE2 OFFSET TMP # sizes

for i = 0 < FILES
    get OFFSET long MEMORY_FILE
    math OFFSET *= 8
    get SIZE long MEMORY_FILE2
    log "" OFFSET SIZE 1
next i
It's right here though.
## Post #12
- Username: Lance Boyle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 24, 2015 1:41 pm
- Post datetime: 2016-01-09T10:35:09+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

So I'm trying to extract the ARCHIVE.AR file from the PSP version of Fast and the Furious, and the script posted here does not work. Is there something different about that version's files? 'Cause I have copied over both ARCHIVE.AR and CDFILES.DAT, so I assumed it would work. To note, it's the US PSP version.
## Post #13
- Username: Lance Boyle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 24, 2015 1:41 pm
- Post datetime: 2016-01-10T09:59:56+00:00
- Post Title: [PS2] Namco Games - ARCHIVE.AR files

Turns out the problem wasn't the file, but the script. I had to find a much newer version of the script elsewhere. It did work, it did extract both the PSP and PS2 versions of the files.

The reason why I wanted to extract this was for the music. While there were some .wavs in there, playing them on any music player or through something like Audacity shows that it's all static, so I'm not even sure if it's those to begin with. Anybody know if that's the case?

Thanks in advance.
