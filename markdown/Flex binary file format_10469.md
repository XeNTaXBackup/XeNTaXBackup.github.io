## Post #1
- Username: cf2004
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 01, 2011 11:52 am
- Post datetime: 2013-05-29T05:38:23+00:00
- Post Title: Flex binary file format

Hi, I was looking at some binary files I found in a flex project and I managed to uncompress one of them, but it still seems to be either encrypted or compressed, so I was wondering if you guys want to take a look, to point me in the right direction. Thanks!
[after_uncompress.zip](https://xentaxbackup.github.io/file/6435_after_uncompress.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-29T10:17:45+00:00
- Post Title: Flex binary file format

Neither encrypted nor compressed I guess.
You could order the bytes such like this:

```
 04 00 04   83 24   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 03 01 04 01 06 7E 
 04 00 04   83 60   01 04 83 42 04 FF FF FF FF  01 0A 09  06 66 01 03 06 4E 04 02 06 48 
 04 00 04   84 1C   01 04 83 42 04 FF FF FF FF  06 78 0A  09 01 01 03 01 04 01 06 21 74 75

 tunnel_borderSE1
 04 00 04   84 58   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01 04 00 01 
 04 00 04   85 14   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01 04 00 01 
 04 00 04   85 50   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01 04 00 01 
 04 00 04   86 0C   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01 04 01 06 81 04
 04 00 04   86 48   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 03 01 04 01 06 7C 
 04 00 04   87 04   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 03 01 04 01 06 7C 
 04 00 04   87 40   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 03 01 04 01 06 21 74 75 6E 6E 65

 tunnel_borderSE2
 04 00 04   87 7C   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01 
 04 00 04   88 38   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01 
 04 00 04   88 74   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01 
 04 00 04   89 30   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01 
 04 00 04   89 6C   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01  
 04 00 04   8A 28   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01 
 04 00 04   8A 64   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01 
 04 00 04   8B 20   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01 
 04 00 04   8B 5C   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01 
 04 00 04   8C 18   01 04 83 42 04 FF FF FF FF  01 0A 09  01 01 02 01  04 00 01 
 04 00 04   8C 54   01 04 83 42 04 FF FF FF FF  ...
```

and then try to get a meaning.

I'm not familiar with this but did you try to import the Flex Project into Adobe Flash Builder 4?
[http://www.videosoftware.pro/forum/THRE ... -Builder-4](http://www.videosoftware.pro/forum/THREAD-Importing-Flex-Project-into-Adobe-Flash-Builder-4)
## Post #3
- Username: cf2004
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 01, 2011 11:52 am
- Post datetime: 2013-05-29T17:12:29+00:00
- Post Title: Flex binary file format

Hi, thanks for your reply! What I was expecting was that after uncompress this file would have been either a SWF or an XML file, because currently I don't understand how flex make sense out of the file the way it is now, in the current code the only line I see after the uncompress() method is readObject() method, and nothing else. So I was just wondering how would flex make sense out of the file the way it is, still being in binary format. But again, thank you very much for your reply!
## Post #4
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2013-05-30T12:59:34+00:00
- Post Title: Flex binary file format

Well, the readObject deserializes a byte[] into an object/class, so there you have your object. It's serialized using the standard amf0/amf3 formatter in flash. Look up for the documentation on the format online. It's open source.
## Post #5
- Username: cf2004
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 01, 2011 11:52 am
- Post datetime: 2013-05-30T19:24:42+00:00
- Post Title: Flex binary file format

Got it! Thanks for your reply!
