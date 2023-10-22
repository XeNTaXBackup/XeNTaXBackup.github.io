## Post #1
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-11-23T16:44:48+00:00
- Post Title: Ready 2 Rumble BOXING.RAT

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-23T23:13:36+00:00
- Post Title: Ready 2 Rumble BOXING.RAT

```
{
   char magic[4]; // "RAT\0"
   char version[4]; // "1.0A"
   uint32_t unk1, unk2, unk3, unk4;
   uint32_t nFiles;
   uint32_t unk5;
}

struct RATFileEntry
{
   char name[16]; // Not sure how it works exactly
   uint32_t size;
   uint32_t unk1, unk2;
   uint32_t offset;
}

```
## Post #3
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-11-23T23:37:28+00:00
- Post Title: Ready 2 Rumble BOXING.RAT

Haven't I see you in ElOtroLado? Thanks for the information.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-26T18:06:43+00:00
- Post Title: Ready 2 Rumble BOXING.RAT

in case someone needs it, this is the quickbms script:

```
goto 24
get FILES long
get DUMMY long
for i = 0 < FILES
    getdstring NAME 16
    get SIZE long
    get DUMMY long
    get DUMMY long
    get OFFSET long
    log NAME OFFSET SIZE
next i
```
