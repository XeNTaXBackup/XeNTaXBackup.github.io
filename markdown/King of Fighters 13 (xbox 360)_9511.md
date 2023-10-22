## Post #1
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-08-19T22:15:45+00:00
- Post Title: King of Fighters 13 (xbox 360)

A tool I made for unpacking and repacking the media.kof file: [http://www.tzarsectus.com/tools/kof13media.rar](http://www.tzarsectus.com/tools/kof13media.rar)

The tool is made for the xbox 360 version, but it's possible it works with PS3 version too.

The format is very simple. There's no header, just a repeating entry list with uncompressed files:

```
	char fileName[0xEE];
	unsigned short unknownA; //Some kind of counter
	unsigned int unknownB; //Always 0?
	unsigned int offset;
	unsigned int unknownC; //Always 0?
	unsigned int size;
};
```


UnknownA counts up now and then, but I don't know the pattern and having it set to 0 during repacking didn't seem to matter anyway, the new media.kof file still worked fine. Many files in media.kof are common formats like PNG and DDS, so the game is easily moddable. I'm tempted to try to reverse engineer the sprite texture format, but that may not be an easy task.
