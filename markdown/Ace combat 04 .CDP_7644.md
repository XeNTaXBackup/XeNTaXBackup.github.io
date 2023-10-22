## Post #1
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-11-08T02:33:42+00:00
- Post Title: Ace combat 04 .CDP

[http://www.gamefront.com/files/17864260/04.rar/](http://www.gamefront.com/files/17864260/04.rar/)

we yea I need to get this opened a friend of mine wants to make a make script for the games models and is fairly sure he could do it but neither of us know archives. he needs it for a supreme commander mod and me for a comic. any help would be great

Namco Playstation 2 2001
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-12T18:08:58+00:00
- Post Title: Ace combat 04 .CDP

the files contain raw data, the index table (name/offset/size) is somewhere else and without it you can't extract the files
## Post #3
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-11-13T00:18:54+00:00
- Post Title: Ace combat 04 .CDP

wow thanks so much for getting back to me!

I assume its this because its the only file with the same extension

[http://www.gamefront.com/files/20983993/BD.rar](http://www.gamefront.com/files/20983993/BD.rar)

and once more thanks even if no one can help hearing back is so nice
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-14T16:36:13+00:00
- Post Title: Ace combat 04 .CDP

no, it's a data file too.
except for these CDP files what other extensions exist?
exists a small possibility that the file list is directly in the executable.

maybe try to post a list of the files you have there and the executable
## Post #5
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-11-14T21:28:30+00:00
- Post Title: Ace combat 04 .CDP

these seem to be the most likely candidates for the needed file as I feel the others a simply video files
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-14T21:31:20+00:00
- Post Title: Ace combat 04 .CDP

the TBL files! :)
they should contain what I'm searching, upload them
## Post #7
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-11-14T21:52:38+00:00
- Post Title: Ace combat 04 .CDP

[http://www.gamefront.com/files/20989903/ac04.rar](http://www.gamefront.com/files/20989903/ac04.rar)

ok this is it let me know
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-16T05:59:48+00:00
- Post Title: Ace combat 04 .CDP

```
open FDDE "cdp" 1
get FILES asize
math FILES /= 8
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    math OFFSET *= 0x800
    log "" OFFSET SIZE
next i
```
note that probably there is a little bug in quickbms which is not able to find the cdp/tbl files if the output folder is different than the input one, I will fix when I will be back at home but you can extract the files without problems if you use the same folder
## Post #9
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-11-16T15:39:53+00:00
- Post Title: Ace combat 04 .CDP

my god thank you
## Post #10
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2011-11-19T19:06:56+00:00
- Post Title: Ace combat 04 .CDP

> Reply from aluigi
>
> Code: Select allopen FDDE "tbl"
open FDDE "cdp" 1
get FILES asize
math FILES /= 8
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    math OFFSET *= 0x800
    log "" OFFSET SIZE
next inote that probably there is a little bug in quickbms which is not able to find the cdp/tbl files if the output folder is different than the input one, I will fix when I will be back at home but you can extract the files without problems if you use the same folder

I have tried this script on the files linked to above and can't get it to extract anything. I keep getting the following error in QuickBMS v0.5.3a:

```
-------------------------
- open input file DATA.tbl
- open input file DATA.cdp
  00000000 12624       DATA\00000000.dat

Error: incomplete input file number 0, can't read 9744 bytes.
```


I'm trying to extract the files to the same folder as the input files. It goes as far as creating a new folder called "DATA" and creates a 0 byte file called "00000000.neo".
What am I doing wrong? Is it the version of QuickBMS I'm using or the files themselves? Any help here would be much appreciated!
## Post #11
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-11-20T02:39:21+00:00
- Post Title: Ace combat 04 .CDP

I am having the same issue I thought it was me but if others are having it could be something else or we might just be making the same mistake
## Post #12
- Username: Spellca
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 22, 2011 10:39 am
- Post datetime: 2011-12-20T12:36:41+00:00
- Post Title: Ace combat 04 .CDP

I am having the same trouble
## Post #13
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2012-01-02T20:24:27+00:00
- Post Title: Ace combat 04 .CDP

I tried once more but no results I must be doing something wrong but I don't know what I could post the error if someone might be able to help
