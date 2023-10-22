## Post #1
- Username: salvatore10
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 15, 2010 8:46 am
- Post datetime: 2010-11-17T17:07:48+00:00
- Post Title: Formula 1 '97 .res files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-11-17T23:06:23+00:00
- Post Title: Formula 1 '97 .res files

*shrugs*

as an archive format it seems simple. the data; not so much

```
get HeaderSize long
math HeaderSize += 4

math curSize = 0

for

  get FILENAME string
  get FILESIZE long
  get FILEPNTR long

  math FILEPNTR += HeaderSize
  log FILENAME FILEPNTR FILESIZE

  savepos POS
  if POS >= HeaderSize
    cleanexit
  endif

next

```
## Post #3
- Username: salvatore10
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 15, 2010 8:46 am
- Post datetime: 2010-11-19T18:06:24+00:00
- Post Title: Formula 1 '97 .res files

Thanks very much for your reply WRS!   
I used that script with quick BMS and extracted the files from the .RES archive.
Is it possible to do the reverse process, and create a .RES archive containing the files?

Attached is one of the .ai files I would like to edit. Does anybody know of a way I could decrypt, edit and encrypt them? I would be very very grateful for any help.
Thanks for reading  
[NURBURG.AI](https://xentaxbackup.github.io/file/3620_NURBURG.AI)
## Post #4
- Username: salvatore10
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 15, 2010 8:46 am
- Post datetime: 2010-12-22T22:11:43+00:00
- Post Title: Formula 1 '97 .res files

Anyone?
