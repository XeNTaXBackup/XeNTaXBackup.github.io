## Post #1
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2011-04-19T08:40:16+00:00
- Post Title: Help extract files from .pk file!

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-04-20T00:44:43+00:00
- Post Title: Help extract files from .pk file!

try changing the extension to ".zip"
## Post #3
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2011-04-20T10:11:23+00:00
- Post Title: Help extract files from .pk file!

thx Caboose !
I tried,but it 's not a zip file.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T18:12:08+00:00
- Post Title: Help extract files from .pk file!

the format is simple but the compression is unknown.

if someone is interested in figuring the compression the following is the format in quickbms script.

```
get DUMMY long
get FILES long
for i = 0 < FILES
    get ZSIZE long
    get SIZE long
    get OFFSET long
    getdstring NAME 32
    clog NAME OFFSET ZSIZE
next i
```

THIS IS ONLY FOR DEVELOPERS, DO NOT USE THIS SCRIPT
## Post #5
- Username: crisalex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 24, 2012 5:19 pm
- Post datetime: 2012-07-24T09:26:16+00:00
- Post Title: Help extract files from .pk file!

hey frndz m looking information about ".pk" plz help...
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-24T13:19:25+00:00
- Post Title: Help extract files from .pk file!

> Reply from crisalex
>
> hey frndz m looking information about ".pk" plz help...
from where?
