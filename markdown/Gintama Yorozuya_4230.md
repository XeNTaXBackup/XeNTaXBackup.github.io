## Post #1
- Username: Daimyo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 07, 2010 4:27 am
- Post datetime: 2010-03-16T17:59:23+00:00
- Post Title: Gintama Yorozuya

Hello ,
I beg for help because even if it seem easy ,I wasn't able to extract and uncompress  from this game with quickbms.
Here is two file from this game :
[http://www.megafileupload.com/en/file/2 ... 0-rar.html](http://www.megafileupload.com/en/file/206834/1A0101-01-00-rar.html)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-16T20:36:44+00:00
- Post Title: Gintama Yorozuya

the format of the archive is simple:

```
idstring "add\0"
goto 16
get FILES long
get PACSIZE long
for i = 0 < FILES
    get DUMMY long
    get DUMMY long
    get OFFSET long
    get SIZE long
    get DUMMY long
    get DUMMY long
    get NAMEOFF long
    get DUMMY long

    savepos TMP
    goto NAMEOFF
    get NAME string
    goto TMP

    log NAME OFFSET SIZE
next i
```
while the format (divided in 2 parts?) and the compression of the LZS files is not easy.
## Post #3
- Username: Daimyo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 07, 2010 4:27 am
- Post datetime: 2010-03-16T22:57:07+00:00
- Post Title: Gintama Yorozuya

Thanks for the code , its helped me to see all the mistake that I made .  
Its a pity for the LZS compression ,but since I tried to extract only for trainning purpose  it doesn't matter for now .
