## Post #1
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-24T11:30:54+00:00
- Post Title: The secret world

is rdbdata i found this information

> The format of the data files is simpler. A small 4-byte header with a file signature followed by data and more data. As mentioned earlier, you need to know the start offset of the content file you're after (which you find in the index). Each file entry has a 16 header before the actual data. This header contains some of the same information as what you find in the index, i.e. RDB type, file id, data length.

```
File part	Length	
Header	4	
Data	---	
		
Header		
Offset	Length	Contents
0	4	Magic (0x52 0x44 0x42 0x30 = RDB0)
		
Data Entry		
Offset	Length	Contents
0	4	Data type
4	4	RDB Id
8	4	Data length
12	4	???
16	DataLength	File data
```


i looking for extrating sound i see one man do it for english version 
 try to concact him but maybie someone can be more speed here
## Post #2
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-24T16:47:08+00:00
- Post Title: The secret world

i try conan exporter but lot of bug corrupt file

edit: dragon unpacker working
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-12-26T16:25:58+00:00
- Post Title: The secret world

le.idx - seems contain hashes and other info for work with rdbdata
## Post #4
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-02-05T12:53:48+00:00
- Post Title: The secret world

RDB data file formats

[http://forums.thesecretworld.com/showthread.php?t=59924](http://forums.thesecretworld.com/showthread.php?t=59924)
