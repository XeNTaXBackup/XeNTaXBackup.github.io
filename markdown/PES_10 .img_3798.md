## Post #1
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-10-21T16:01:03+00:00
- Post Title: PES_10 .img

I think every one knows the number one soccer game in the world - [http://konami.com/games/pes2010/](http://konami.com/games/pes2010/).

I have searched forum and nothing about this game espacially for PC

At least that newest serie has the .img files.

For the reason Im going to translate this beautiful game.

Can anyone lay a light on it? ...thanks
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-22T17:26:09+00:00
- Post Title: PES_10 .img

You do know how it works, Gocha. We will need example files.
## Post #3
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-10-23T12:14:57+00:00
- Post Title: PES_10 .img

[http://www.xup.in/dl,47523286/dt0f.img/](http://www.xup.in/dl,47523286/dt0f.img/)

one of them


bth atm looks like zlib
## Post #4
- Username: Gocha
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-23T19:38:09+00:00
- Post Title: PES_10 .img

you can extract the archive with offzip
just use offxip.exe -a c:\file.img c:\export 0x0
the files are called .tex which is some type of image format.
## Post #5
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-10-23T21:06:43+00:00
- Post Title: PES_10 .img

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-10-24T13:10:36+00:00
- Post Title: PES_10 .img

chrrox,
Thanks, but that tool extracts just that file, there are other ASF files but with a bit different structure, looks like, coz that ones it couldn't extract, anyway I need also import.

GameZelda,
Tool that you offered, can't extract even that exmpl. file - dt0f.img. Didn't work for me.

Also peaple I want to share with you and interested persons my searching results:
I have had found many tools for editing series of this game, but for now I can't edit just .img needed for the language localization (dt05_x.img, where x means lang ID - e[English], f[French], for exmp. dt05_e.img)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-24T13:16:26+00:00
- Post Title: PES_10 .img

simple script for quickbms:

```
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long

    if SIZE != 0
        log "" OFFSET SIZE
    endif
next i
```
I noticed that these WESYS files have zlib compressed data at offset 16
## Post #8
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-10-24T19:27:23+00:00
- Post Title: PES_10 .img

aluigi
script just extracts anyway.

So what to do with that extracted files...
Here's one more .img file, which contains game's some language data
[http://www.sendspace.com/file/r5n2n7](http://www.sendspace.com/file/r5n2n7)
File Name: dt05_e.7z
Size: 9MB
## Post #9
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-10-24T21:42:52+00:00
- Post Title: PES_10 .img

> Reply from Gocha
>
> 
GameZelda,
Tool that you offered, can't extract even that exmpl. file - dt0f.img. Didn't work for me.

Also peaple I want to share with you and interested persons my searching results:
I have had found many tools for editing series of this game, but for now I can't edit just .img needed for the language localization (dt05_x.img, where x means lang ID - e[English], f[French], for exmp. dt05_e.img)

My program works perfectly on both files. How are you executing it?

I "cd" to the directory where I have the EXE and the img file, then I use:

```
IMGExtract dt05_e.img dt05_e
```


And it extracts the contents perfectly.

---------------

Here's the file structure, in case someone wants to know:

```
{
   char magic[4]; // "AFS\0"
   uint32_t nFiles;
   AFSFileEntry files[nFiles];
}

struct AFSFileEntry
{
   uint32_t offset;
   uint32_t size;
}

---

Most of the files on the container use a filesystem called WESYS.

If the file starts with "\x00\x01\x00WESYS":
struct UncompressedWESYS
{
   char magic[8]; // "\x00\x01\x00WESYS"
   uint32_t size;
   uint32_t zero;
   uint8_t wesys[size];
}

If the file starts with "\x00\x01\x01WESYS"
struct ZlibWESYS
{
   char magic[8]; // "\x00\x01\x01WESYS"
   uint32_t cmprSize;
   uint32_t uncmprSize;
   uint8_t wesys[cmprSize]; // Uncompress with Zlib
}

---

For the two structures above, once you have the real data, the structure is:

struct WESYSFile
{
   uint32_t nFiles;
   uint32_t eight; // Always 8. May be a pointer to the file table, that is always at offset 8.
   WESYSFileEntry files[nFiles];
}

struct WESYSFileEntry
{
   uint32_t offset;
   uint32_t size;
   uint32_t fileNameOffset; // 0xFFFFFFF0 = unnamed file
}

```
## Post #10
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-10-25T05:37:04+00:00
- Post Title: PES_10 .img

GameZelda,
Ya man! Now it works perfectly on this file! Others other .img-s had not tested.
Now remains how to pack back those extracted files.

So that BMSscript by aluigi extracts uncorrectly! Coz IMGExtractor extracts all files correctly, and as GameZelda said, I can remove 16 bytes and it's just a texture.
