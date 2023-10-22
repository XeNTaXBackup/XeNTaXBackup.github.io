## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-17T14:45:02+00:00
- Post Title: unpacking dds from emb

Hi, i'm trying to unpack emb files with this:

```
get UNK1 long
get UNK2 long
get FILES long
goto 0x24
get SIZE long
goto 0x40
getdstring EXT 0x3
get NAME filename
string NAME += .
string NAME += EXT

log NAME OFFSET SIZE
```


but quickbms gives me full length of the file everytime
basically i need to delete first 0x40, but how?

[sample file](http://dl.dropbox.com/u/9919707/BOS_01_03_12208.back)
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-03-17T16:16:25+00:00
- Post Title: unpacking dds from emb

Try this 

```
get UNK1 long
get UNK2 long
get FILES long
goto 0x24
get SIZE long
goto 0x40
savepos OFFSET
getdstring EXT 0x3
get NAME filename
string NAME += .
string NAME += EXT

log NAME OFFSET SIZE
```
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-17T16:56:43+00:00
- Post Title: unpacking dds from emb

> Reply from merlinsvk
>
> Try thisthanks, it's working brilliant
