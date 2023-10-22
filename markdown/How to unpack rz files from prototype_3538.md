## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2009-06-17T14:33:04+00:00
- Post Title: How to unpack rz files from prototype

Hi,

I used ScarfaceExplorer to look on rcf archives and i extracted this file textures.p3d.rz. (header RZ)
I looking on internet and i found rzip but i don't found any compiled exe version...

[http://www.2shared.com/file/6349516/b09 ... esp3d.html](http://www.2shared.com/file/6349516/b097c766/texturesp3d.html)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-17T19:07:33+00:00
- Post Title: How to unpack rz files from prototype

Very simple format, just a short header followed by zlib compressed data.
Just use offzip: [http://aluigi.org/mytoolz/offzip.zip](http://aluigi.org/mytoolz/offzip.zip)
## Post #3
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2009-06-18T12:00:40+00:00
- Post Title: How to unpack rz files from prototype

thanks how to use it? for extract
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-18T14:08:21+00:00
- Post Title: How to unpack rz files from prototype

```
offzip inputfile outputfile 16
```

btw, 16 is the compressed data offset.
