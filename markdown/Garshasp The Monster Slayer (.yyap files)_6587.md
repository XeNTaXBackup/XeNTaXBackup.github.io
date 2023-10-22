## Post #1
- Username: Fenris93
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Jul 20, 2010 6:51 am
- Post datetime: 2011-05-09T22:15:59+00:00
- Post Title: Garshasp: The Monster Slayer (.yyap files)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Isilfor
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 20, 2010 12:01 am
- Post datetime: 2011-05-10T07:24:07+00:00
- Post Title: Garshasp: The Monster Slayer (.yyap files)

It looks like files are simply stored without compression and encryption.
## Post #3
- Username: Fenris93
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Jul 20, 2010 6:51 am
- Post datetime: 2011-05-10T08:38:38+00:00
- Post Title: Garshasp: The Monster Slayer (.yyap files)

Yes, but i don't really have the knowledge to extract, edit, an repack the files. Can anyone help me? Thanks for reply
## Post #4
- Username: Hioushi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 06, 2008 8:03 am
- Post datetime: 2011-05-16T17:06:29+00:00
- Post Title: Garshasp: The Monster Slayer (.yyap files)

Could someone take another look on how to unpackage the yyap files? I'm givin it a try but is it really not encripted?

Thanks.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-05-16T17:32:37+00:00
- Post Title: Garshasp: The Monster Slayer (.yyap files)

script for quickbms:

```
goto 0x2a
get FILES long
get OFFSET long
get DUMMY long
get DUMMY long
get BASE_OFF long
goto OFFSET
for i = 0 < FILES
    get OFFSET long
    get DUMMY long
    get SIZE long
    getdstring DUMMY 0x16
    get NAMESZ short
    math NAMESZ *= 2
    getdstring NAME NAMESZ
    set NAME unicode NAME
    math OFFSET += BASE_OFF
    log NAME OFFSET SIZE
next i
```
