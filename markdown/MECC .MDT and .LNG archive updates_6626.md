## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-05-16T02:01:14+00:00
- Post Title: MECC .MDT and .LNG archive updates

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-22T03:38:44+00:00
- Post Title: MECC .MDT and .LNG archive updates

Hey hey!

You are correct sir.  Same packing method as with Opening Night, except the headers here are missing the string "Jigsaw Calculator."

Regardless, I've written a new script that you can use to extract files from these archives as well as the opening night ones.  It's still rough, but a bit more refined in that it makes separate folders, adds file extensions, and adapts for different length archives.  It's no longer opening night specific.  Now to figure out how these damn .CBMP files are compressed so that I can start modding the game like i wanted to 5 damn years ago.    

anyways, here's the quickbms script:

```
Get HEADERSIZE Short;
Get UNK1 Long;
IDString "MECC";
Goto 0x56;
Get DIRS Short;
Get FILES Long;
Math DIRS *= 16;
Math DIRS += 92;
Goto DIRS;
For i = 0 < FILES;
Getdstring TYPE 0x08;
Get NAMEV Long;
Set NAME = "";
String NAME += TYPE;
String NAME += "\";
String NAME += NAMEV;
String NAME += ".";
String NAME += TYPE;
Get OFFSET Long;
Get FILESIZE Long;
log NAME FILESIZE OFFSET;
Set NAME = "";
next i; 
```


Later,
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-06-28T06:06:22+00:00
- Post Title: MECC .MDT and .LNG archive updates

> Reply from jawharp
>
> Hey hey!

You are correct sir.  Same packing method as with Opening Night, except the headers here are missing the string "Jigsaw Calculator."

Regardless, I've written a new script that you can use to extract files from these archives as well as the opening night ones.  It's still rough, but a bit more refined in that it makes separate folders, adds file extensions, and adapts for different length archives.  It's no longer opening night specific.  Now to figure out how these damn .CBMP files are compressed so that I can start modding the game like i wanted to 5 damn years ago.

Thanks. BTW if you want the full game for experimentation, please, let me know.
## Post #4
- Username: Koragi85
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 01, 2011 9:40 am
- Post datetime: 2011-12-01T01:42:40+00:00
- Post Title: MECC .MDT and .LNG archive updates

Ive been interested in picking apart Opening Night. Would you mind sharing it for testing purposes?

Thanks.
## Post #5
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-12-01T02:29:58+00:00
- Post Title: MECC .MDT and .LNG archive updates

I don't have a copy of it, but I do have an ISO of the American Girls Premiere which runs on the same engine as with Opening Night.
