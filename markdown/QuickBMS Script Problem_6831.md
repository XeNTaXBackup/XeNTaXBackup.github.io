## Post #1
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-22T00:47:59+00:00
- Post Title: QuickBMS Script Problem

Hey,

So I'm having a little trouble here.  I can't seem to figure out why this isn't working right.  I'm trying to multiply the value in the variable "DIRS" by 16 and have the script goto the offset of DIRS*16.  It is absolutely not working.  Any ideas?

```
Get HEADERSIZE Short;
Get UNK1 Long;
IDString "MECC";
Goto 0x56;
Get DIRS Short;
Get FILES Long;
Math DIRS *= 16;
Goto DIRS;
For i = 0 < FILES;
Getdstring TYPE 0x08;
Get NAME Long;
String TYPE += NAME;
Get OFFSET Long;
Get FILESIZE Long;
log TYPE FILESIZE OFFSET;
next i; 
```


Thanks,
## Post #2
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-06-22T02:45:00+00:00
- Post Title: QuickBMS Script Problem

Could it be that DIRS is getting overflowed because it's a short (two bytes, unless I'm mistaken)? Keep in mind I don't know that much about using MexScript, let alone QuickBMS, so I could be wrong/completely off-base. =/
## Post #3
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-22T03:29:30+00:00
- Post Title: QuickBMS Script Problem

This was my fault.  It was multiplying correctly.  I just had the wrong address it was supposed to go to...

there's an hour of my life I can't get back.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-26T22:33:42+00:00
- Post Title: QuickBMS Script Problem

after you waste an hour for a simple problem there are good chances that the same will not happen in future... yeah a sort of investment :)
