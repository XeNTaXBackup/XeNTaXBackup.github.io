## Post #1
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2012-02-26T01:25:58+00:00
- Post Title: Asura's Wrath UT3 .SOUNDNODEWAVE

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-02-28T21:20:11+00:00
- Post Title: Asura's Wrath UT3 .SOUNDNODEWAVE

The headers are slightly different in this game. It doesn't put the Hz rate in the usual place for the script to find.

Update this line to the following and it will work

```
goto 0xDA
```

or if that doesn't work on a file, try this:

```
goto 0x72
```


Additionally, some of the files use a different XMA flag, change the following line in the script

```
FindLoc OFFSET STRING \xfc\x03\x80\x00 0 ""
```
