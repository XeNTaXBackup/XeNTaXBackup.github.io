## Post #1
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-26T03:54:21+00:00
- Post Title: Star Wars The Force Unleashed II .LP files [PS3]

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-26T09:46:00+00:00
- Post Title: Star Wars The Force Unleashed II .LP files [PS3]

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
idstring "APak"
get DUMMY long
get FILES long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get NAMES_SIZE long
get OFFSET1 long
get OFFSET2 long

math NAME_BASE = 0x50
math OFFSET3 = NAME_BASE
math OFFSET3 += NAMES_SIZE

for i = 0 < FILES
    goto OFFSET3
    getdstring DUMMY 0x14
    get NAME_OFF long
    getdstring DUMMY 0x14
    get SIZE long
    getdstring DUMMY 0x10
    savepos OFFSET3

    goto OFFSET1
    get NUM long
    get OFFSET long
    get DUMMY long
    get DUMMY long
    savepos OFFSET1

    math NAME_OFF += NAME_BASE
    goto NAME_OFF
    get NAME string
    goto TMP

    math OFFSET += OFFSET2
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-26T11:16:01+00:00
- Post Title: Star Wars The Force Unleashed II .LP files [PS3]

Thanks I managed to make even the re-import the file, if necessary I will remove the text in Italian for example to apply the translation PT-BR so that the file does not get big problem at the time of reimport.

Thank you, The more I post the result later.
## Post #4
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-14T14:34:09+00:00
- Post Title: Star Wars The Force Unleashed II .LP files [PS3]

Luigi, you will be able to update the script to work with files Star Wars The Force Unleashed 1? 
[TEM_JEDITEMPLE_B_PS3-edit.rar](https://xentaxbackup.github.io/file/5992_TEM_JEDITEMPLE_B_PS3-edit.rar)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-11-14T15:56:17+00:00
- Post Title: Star Wars The Force Unleashed II .LP files [PS3]

if you have a bigger chunk of that file and also a sample of a lp file of unleashed 2 I guess I can do the job, because I need to find the difference to make an universal script.
## Post #6
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-14T16:06:24+00:00
- Post Title: Star Wars The Force Unleashed II .LP files [PS3]

understood, since I send the files.
## Post #7
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-14T16:39:34+00:00
- Post Title: Star Wars The Force Unleashed II .LP files [PS3]

Files. [http://www.mediafire.com/download.php?geopoucdx783jvq](http://www.mediafire.com/download.php?geopoucdx783jvq)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-11-14T18:49:02+00:00
- Post Title: Star Wars The Force Unleashed II .LP files [PS3]

I have updated the script (not yet on my website) but there is still no full support for this game.
it takes time so at the moment I prefer to give up.
## Post #9
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-14T19:03:28+00:00
- Post Title: Star Wars The Force Unleashed II .LP files [PS3]

I did a quick test and it is extract .WAD of Star Wars The Force Unleashed 1  
Only not yet .LP files.

Thanks Luigi.

Edit.
Luigi, It extracts only some thing. WAD, I have one. WAD with more than 4GB, it extracts only 7mb.
