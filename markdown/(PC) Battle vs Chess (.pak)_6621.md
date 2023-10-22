## Post #1
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-05-15T13:18:24+00:00
- Post Title: (PC) Battle vs Chess (.pak)

Please, help me with unpacking (pak) file.

[http://www.multiupload.com/2SM6U3PAHH](http://www.multiupload.com/2SM6U3PAHH)
## Post #2
- Username: Sniperello
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 08, 2011 7:26 am
- Post datetime: 2011-05-20T06:50:18+00:00
- Post Title: (PC) Battle vs Chess (.pak)

Good 3d models in this game 
Please unpack pack +1
## Post #3
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-08-23T23:56:41+00:00
- Post Title: (PC) Battle vs Chess (.pak)

A little bit more info (and guesswork) about the format:

```
int versionNum;
int unknown2;
unsigned int numFiles;
int unknown3;
unsigned int realSizeOfFilelist;
unsigned int compressedSizeOfFilelist;
```

After that is the compressed list of files (which would include filenames and offsets I assume). And after that are the actual files, where many (if not all) are uncompressed.

I have no which type of compression is used for that file list. I tried aluigi's quickbms script which tries every bms compression on a file list, and I only got gibberish.

The game is released with the name Check vs Mate in USA by the way.
