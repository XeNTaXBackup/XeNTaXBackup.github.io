## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-09-30T11:50:03+00:00
- Post Title: PSP Lost Heroes .PCK

```
2NBFX'...ˆ......libfont.prx.............................................................................................................................ÐP..Battle/Btl_Normal_pk.cmp
```

Hi,
I need help unpack the PSP Lost Heroes .PCK file.

```
6D 65 64 69 61 66 69 72 65 2E 63 6F 6D 2F 3F 39 7A 61 76 6A 36 64 72 70 75 76 34 61 67 78
```
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-09-30T12:26:29+00:00
- Post Title: PSP Lost Heroes .PCK

I did it for my friend weks ago. Hope this help!

```
# by Fatduck     Sept 2012
# http://aluigi.org/quickbms.htm

idstring "2NBF"
get NUMRES long
get OFSBASE long
get BLKSIZE long

for i = 0 < NUMRES
   getdstring RESNAME 0x80
   get OFSRES long
   get NULL long
   get SIZERES long
   math OFSRES += OFSBASE
   log RESNAME OFSRES SIZERES
next i
```
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-09-30T21:23:47+00:00
- Post Title: PSP Lost Heroes .PCK

Thanks fatduck
## Post #4
- Username: BlackDog
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 11, 2015 4:51 am
- Post datetime: 2015-10-11T08:17:46+00:00
- Post Title: PSP Lost Heroes .PCK

Has anyone tried anything further on this game?
## Post #5
- Username: BlackDog
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 11, 2015 4:51 am
- Post datetime: 2016-08-09T05:47:43+00:00
- Post Title: PSP Lost Heroes .PCK

Yes.  
Well I read this because I was trying to use QuickBMS for the first time - for something I think it wasn't designed to do: dump hex (into its textual equivalent, like a hex editor does, but interpreting structures at the same time) to be able to explore it.

Does the FatDuck script above allow re-PCK'ing?
