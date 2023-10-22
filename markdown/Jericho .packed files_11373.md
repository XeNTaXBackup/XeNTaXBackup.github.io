## Post #1
- Username: Ivan123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 30, 2014 3:58 am
- Post datetime: 2014-03-30T07:25:10+00:00
- Post Title: Jericho .packed files

Hi everybody. I am having trouble extracting Jericho .packed files. I use Gobread for that and run it through DOSBox 0.74. When i execute the command gobread gives me no errors and logs the first file it is trying to extract. It even creates the file and all necessary directories on the hard drive. Unfortunately it doesnt go anywhere after this. Created file has size 0 bites and doesnt grow and Gobread doesnt go to the next file. I've waited quite some time but no results.

Did anyone have similar problem with Gobread?
## Post #2
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-03-30T08:23:49+00:00
- Post Title: Jericho .packed files

Did you try unpack script for Castlevania LoS?
Format same, but maybe with some changes, if script not work, do screenshot of begin of the file in Hex editor.
## Post #3
- Username: Ivan123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 30, 2014 3:58 am
- Post datetime: 2014-03-30T08:57:40+00:00
- Post Title: Jericho .packed files

Here is the screenshot of data file in hex editor: 



Sadly i dont have Castlevania LoS.
## Post #4
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-03-30T10:36:08+00:00
- Post Title: Jericho .packed files

```
get version long
get files long
savepos TMP
for i = 0 < files
goto TMP
get NSIZE long
getdstring name NSIZE
get size long
get offset long
savepos TMP
goto offset
get zsize long
savepos OFFSET
if zsize == size
log name offset zsize
else
clog name offset zsize size
endif
goto TMP
next i
```

This is quickbms script for unpack .packed files in CLoS, did you try it for Jericho .packed archives?
Seems format absolutely same.
## Post #5
- Username: Ivan123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 30, 2014 3:58 am
- Post datetime: 2014-03-30T11:08:07+00:00
- Post Title: Jericho .packed files

This script worked. Thanks a lot!
