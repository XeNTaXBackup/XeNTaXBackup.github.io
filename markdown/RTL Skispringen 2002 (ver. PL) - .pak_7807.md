## Post #1
- Username: 2xcastx2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 10, 2010 9:21 pm
- Post datetime: 2011-12-04T17:14:50+00:00
- Post Title: RTL Skispringen 2002 (ver. PL) - *.pak

Hi,
Could you please look at the *.pak archives from RTL Skispringen 2002 (ver. PL) - *.pak - I think they contain the sounds and textures
I used some programs to extract texture files but it doesn't work:
PakExplorer
PakScape
Dragon UnPACKer
WinRar
WinZip
Smith Micro Stuffit Deluxe
Depacker
PakBuilder
HBPak_Editor 
Please help
I cutted piece of packfile.pak
LINK
[http://speedy.sh/TwNNC/packfile.zip](http://speedy.sh/TwNNC/packfile.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-04T20:44:59+00:00
- Post Title: RTL Skispringen 2002 (ver. PL) - *.pak

the format is trivial but I don't know what compression it uses (yeah it looks easy but none of the default ones I scanned gave me the right result), so for the moment this is an useless script (aka DON'T USE IT):

```
for
    get ZSIZE long
    get OFFSET long
    get XSIZE long
    get SIZE long
    getdstring NAME 0x40
    if NAME == ""
        break
    endif
    math OFFSET *= 0x800
    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next
```
## Post #3
- Username: 2xcastx2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 10, 2010 9:21 pm
- Post datetime: 2011-12-10T10:07:21+00:00
- Post Title: RTL Skispringen 2002 (ver. PL) - *.pak

any ideas?
## Post #4
- Username: danciechan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 19, 2017 2:09 am
- Post datetime: 2017-01-18T18:33:05+00:00
- Post Title: RTL Skispringen 2002 (ver. PL) - *.pak

Hi, could anyone look at this file again (RTL Skispringen 2002/ RTL Ski Jumping 2002 / Skoki Narciarskie 2002), and maybe get the solution how to unpack this file. I like this game and I want to change some things to make update to current season. 

I also know, that jumpers are hide on 003.dat, propably on HEX , but when we edit values (even if control sum is the same) game open with error "wrong file". 

[https://www.dropbox.com/sh/jnwk7oqu25zp ... Ed0Va?dl=0](https://www.dropbox.com/sh/jnwk7oqu25zpzar/AADLJvIDFAvOGmMPkK7TEd0Va?dl=0)

I upload packfile.pak with graphics and sound game, and also 001, 002, 003 dat files. 

Maybe someone know how to edit 003 file (and unlock file, because every change jumper on game changing 0 values on file) ?
