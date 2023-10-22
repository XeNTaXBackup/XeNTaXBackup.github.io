## Post #1
- Username: Tanner
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 03, 2009 7:15 pm
- Post datetime: 2009-01-03T13:51:26+00:00
- Post Title: Test Drive Eve Of destruction Xbox

Hi, i am new on xentax and have interest in modding games on ps2, xbox and pc.

I wanted to upload 2 files (*.car and *.res) but these 2 extensions are not allowed to upload?  

What's wrong with these extensions ?
 
Thanks.
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-03T19:41:23+00:00
- Post Title: Test Drive Eve Of destruction Xbox

you have to rar them
## Post #3
- Username: Tanner
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 03, 2009 7:15 pm
- Post datetime: 2009-01-03T23:07:12+00:00
- Post Title: Test Drive Eve Of destruction Xbox

Ok thanks. the *.car file should contain the 3d model and the *.res file , some textures or other files.
It would be great if you can add support in MultiEx Commander for this game.


I have made changes to the game by swapping and renaming the *.car files.

I have also made changes to the xbe file of driv3r with an hex editor.

Thanks in advance. 
[files.rar](https://xentaxbackup.github.io/file/1797_files.rar)
## Post #4
- Username: Tanner
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 03, 2009 7:15 pm
- Post datetime: 2009-01-13T21:38:53+00:00
- Post Title: Test Drive Eve Of destruction Xbox

Hey Mr. Mouse, where are you?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-06T02:10:11+00:00
- Post Title: Test Drive Eve Of destruction Xbox

the following is a quick and basic script for [QuickBMS](http://aluigi.org/papers.htm#quickbms), hope it helps:

```
goto 20
get INFO_OFFSET long
get FILES long

goto INFO_OFFSET
for i = 0 < FILES
    getdstring NAME 0x20
    get TYPE long
    get DUMMY long
    get SIZE long
    get OFFSET long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long

    math OFFSET += INFO_OFFSET
    log NAME OFFSET SIZE
next i
```
