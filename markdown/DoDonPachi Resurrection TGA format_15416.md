## Post #1
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2016-10-26T12:05:44+00:00
- Post Title: DoDonPachi Resurrection TGA format

There is one of .bin-containers with strange TGA files. It is from PC version of DoDonPachi Resurrection game.
[http://rgho.st/89XsxHWf8](http://rgho.st/89XsxHWf8)

I think the content of .bin-file looks like follows:

```
DWORD Unknown0[2];
DWORD StartOfData <format=hex>;
DWORD NumberOfFiles;
DWORD Unknown[5];

struct Entry
{
    DWORD Unknown10;
    DWORD dataSize0;
    DWORD dataSize;
    DWORD Unknown12;
    WORD Unknown1;
    CHAR Name[0x102];
};

Entry files[NumberOfFiles];

local int i;
for(i = 0; i < NumberOfFiles; i++)
{
    struct { BYTE data[files[i].dataSize ? files[i].dataSize : files[i].dataSize0]; } fileEntry <optimize=false>;
}
```


Here is a 010 Editor template. I have a problem with the opening of extracted TGA files. Is it TGA format or something else with .tga extention? Help me to figure out please.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-26T17:50:35+00:00
- Post Title: DoDonPachi Resurrection TGA format

made a bms script to split the files from the bin  

```
goto 0xc
get FILES long
goto 0x24
for i = 0 < Files
	savepos TMP
	get SKIP long
	get SKIP long
	get SIZE long
	get OFFSET long
	get SKIP short 
	get NAME string
	log NAME OFFSET SIZE
	math TMP + 0x114
	goto TMP
next i
```


i don't know about the texture data though, it might be rle compressed or something
## Post #3
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2016-10-26T20:28:01+00:00
- Post Title: DoDonPachi Resurrection TGA format

> Reply from AceWell
>
> 
i don't know about the texture data though, it might be rle compressed or something
Thanks, but already I have extracted files. I have a problem with the format of the texture only.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-26T23:26:52+00:00
- Post Title: DoDonPachi Resurrection TGA format

> Reply from destrator
>
> Thanks, but already I have extracted files. I have a problem with the format of the texture only.
this i know, the bms script is for anyone who doesn't have or use "010 Editor"
