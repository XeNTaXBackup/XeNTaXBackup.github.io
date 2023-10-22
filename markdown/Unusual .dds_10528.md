## Post #1
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-06-17T23:49:00+00:00
- Post Title: Unusual .dds

I have some .dds files, but can't figure out, how to open them. They have unusual header. Here are some examples: <snip>
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-06-18T10:16:42+00:00
- Post Title: Unusual .dds

They are packed with Snappy. 

This rough QuickBMS script can unpack them (except 2.dds). But better choice should be to use original compression library from [https://code.google.com/p/snappy/](https://code.google.com/p/snappy/)

```
set SIZE 0
if SIZE <= 0
    math SIZE = ZSIZE
    math SIZE *= 20
endif
comtype snappy
get NAME filename
string NAME += ".new.dds"
clog NAME 0 ZSIZE SIZE

```


Example of 9.dds
[](http://imgur.com/Y24MqX0)
## Post #3
- Username: TERAB1T
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 28, 2012 7:40 am
- Post datetime: 2013-06-18T12:38:23+00:00
- Post Title: Unusual .dds

merlinsvk, thanks a lot for your help!
