## Post #1
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2020-09-14T01:32:12+00:00
- Post Title: DOAX3 texch format

Hi, I hope someone can check this pls:

[http://www.mediafire.com/file/h05fu7io2h3wma0/file](http://www.mediafire.com/file/h05fu7io2h3wma0/file)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-09-14T06:57:31+00:00
- Post Title: DOAX3 texch format

open texchl file in hex editor and delete first 16 bytes and rename extension to gnf then open with Noesis.   
or use bms script to automate process:

```

get NAME basename
string NAME + .gnf
get SIZE asize
math SIZE - 0x10
log NAME 0x10 SIZE
```
