## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-13T08:23:57+00:00
- Post Title: Red Steel 2 bbf file

here is a bbf file cut from the red steel 2 game.

aluigi!! 

[http://www.megaupload.com/?d=ALAPUMG0](http://www.megaupload.com/?d=ALAPUMG0)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-13T10:13:03+00:00
- Post Title: Red Steel 2 bbf file

:)

```

idstring "ABE\0"
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get INFO_OFF long
get DUMMY long
get ROOT_OFF long

goto INFO_OFF
get FILES long
get DUMMY long
get DUMMY long

for i = 0 < FILES
    getdstring NAME 0x40
    getdstring DUMMY 0x10
    get DUMMY long
    get DUMMY long
    get SIZE long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get OFFSET long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    getdstring DUMMY 0x40

    if NAME & "."
    else
        strlen NAMESZ NAME
        putvarchr NAME NAMESZ 0x2e
    endif
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-13T11:15:38+00:00
- Post Title: Red Steel 2 bbf file

thx luigi
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-13T20:06:57+00:00
- Post Title: Red Steel 2 bbf file

Here is another file cut, tried the script but it wouldnt extract all the sounds.

[http://www.megaupload.com/?d=PKKNQPZA](http://www.megaupload.com/?d=PKKNQPZA)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-13T22:50:34+00:00
- Post Title: Red Steel 2 bbf file

you should post more data, at least till the offset of the file that gives problems because the script seems to work perfectly (I have checked the offsets and sizes showed with -l and they are ok).

are you sure you have the full file?
it must be at least 515312240 bytes long so if it's smaller it's normal that the script returns an error
## Post #6
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-09-05T16:50:56+00:00
- Post Title: Red Steel 2 bbf file

Hi Aluigi.
I extract 1000 files with .sns extension.What should i do now?
Thanks for script:)
