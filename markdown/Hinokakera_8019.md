## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T05:19:00+00:00
- Post Title: Hinokakera

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-01-10T07:30:29+00:00
- Post Title: Hinokakera

This is what I did a few months ago.

```
# http://r-region.net/
# by fatduck     updated Nov2011
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

getdstring VER 4
if ver == "dat1"
   get NUMRES long
   for i = 0 < NUMRES
      get LEN long
      getdstring RESNAME LEN
      get OFSRES long
      get SIZERES long
      log RESNAME OFSRES SIZERES
   next i
elif ver == "dat0"
   get TBLNAME fullname
   string TBLNAME -= 5
   set DATNAME TBLNAME
   string TBLNAME += 2.dat
   string DATNAME += 1.dat

   open FDSE TBLNAME 0
   open FDSE DATNAME 1
   
   getdstring DAT0 4 0
   get LEN long 0 
   getdstring ARCNAME LEN 0
   get NUMRES long 0 
   for i = 0 < NUMRES
      get LEN long 0 
      getdstring RESNAME LEN 0 
      get OFSRES long 0
      get SIZERES long 0
      goto OFSRES 1
      get LEN long 1
      getdstring  RESNAME LEN 1
      savepos OFS 1
      log RESNAME OFS SIZERES 1
   next i    
endif
```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T17:39:51+00:00
- Post Title: Hinokakera

I'm still getting "no such file or folder"" even though the input name is correct.
Weird. I've tried placing the archives in the same folder as quickbms.

Maybe my computer doesn't handle the paths properly.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-10T17:40:31+00:00
- Post Title: Hinokakera

check your quickbms version, there was a bug regarding the opening of the files till a couple of versions ago and I guess it's that one
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-10T21:51:19+00:00
- Post Title: Hinokakera

Oh, there we go.
I was using 0.5.2.
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-01-10T22:05:04+00:00
- Post Title: Hinokakera

Use it in command-line!
The dialog version had been broken since version 0.43!? And still broken!
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-10T22:51:52+00:00
- Post Title: Hinokakera

quickbms has no problems with the dialog version so I don't have the minimal idea about what you refer.
and I don't remember pms or mails from your reporting similar problems.
## Post #8
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-01-11T00:37:28+00:00
- Post Title: Hinokakera

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-11T01:32:51+00:00
- Post Title: Hinokakera

ah I understand.
it's not a real bug, in short you can't specify files that have a full path to avoid to load/write external files.

correcting the script is very easy:

```
   string TBLNAME -= 1
```
so that TBLNAME will contain the name of the input file without extension and "-= 1" will remove the last char.

try it, it should work correctly now
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-11T04:31:13+00:00
- Post Title: Hinokakera

> Reply from fatduck
>
> Use it in command-line!
The dialog version had been broken since version 0.43!? And still broken!

I only use command-line
## Post #11
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-01-11T08:41:20+00:00
- Post Title: Hinokakera

Thanks for the explaination, Luigi!

But why command-line works?
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-11T10:54:36+00:00
- Post Title: Hinokakera

because in command-line you use relative paths like "quickbms file.bms file.dat" and so when quickbms tries to open the file from the same folder it does "c:\current_folder" + "fullname.dat" where fullname is just the one you provided at command-line.
in dialog you have absolute paths so you have "c:\current_folder" + "c:\current_folder\fullname.dat".

indeed in command-line you had the same error if you specify full paths.
"get NAME fullname" is only for debugging purposes, it should be never used.
probably what you wanted to use was "get NAME filename" in which case it worked perfectly as you expected with both relative and absolute paths.
