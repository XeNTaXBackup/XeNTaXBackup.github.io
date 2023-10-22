## Post #1
- Username: Rafulpower
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 15, 2007 1:15 am
- Post datetime: 2007-11-14T17:50:03+00:00
- Post Title: Silent Hill Origins - ARC archive

Hello! I am new for here. 
I need to unpack/pack *.arc archives from Silent Hill Origins [PlayStation Portable].

I want to translate the texts for Portuguese.

Thanks.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-18T22:53:55+00:00
- Post Title: Silent Hill Origins - ARC archive

Please upload some sample files. 
(preferably not rapidshare, [http://uploaded.to](http://uploaded.to) is quite good imho)
## Post #3
- Username: Rafulpower
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 15, 2007 1:15 am
- Post datetime: 2007-11-19T15:43:41+00:00
- Post Title: Silent Hill Origins - ARC archive

[http://uploaded.to/?id=7pbtye](http://uploaded.to/?id=7pbtye)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-20T00:39:54+00:00
- Post Title: Silent Hill Origins - ARC archive

Had a short look. Here's my current template which might be horribly wrong:

```

struct Entry {
	uint uk1;
	uint offset;
	fpos=FTell();
	FSeek(offset);
	uint uk2[5];
	string name;
	FSeek(fpos);
	uint uk3;
	uint uk4;
};

uint magic;
Entry directory[36]<optimize=false>;
```


However this archive contains only video files. Even if you managed to unpack it, you would have to somehow convert the AT3 movies.

Are there other ARC files?
## Post #5
- Username: Rafulpower
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 15, 2007 1:15 am
- Post datetime: 2007-11-20T19:57:31+00:00
- Post Title: Silent Hill Origins - ARC archive

Yes, there are other ARC files!

SH.arc - 270MB

Part1 - [http://uploaded.to/?id=5s5n8j](http://uploaded.to/?id=5s5n8j) (229 MB)
Part2 - [http://uploaded.to/?id=ksciu1](http://uploaded.to/?id=ksciu1) (25 MB)

Thanks.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-20T22:10:07+00:00
- Post Title: Silent Hill Origins - ARC archive

Thanks.

```
	uint FilenameOffset; // Offset in the string table
	uint Offset;
	uint Size;
	uint DecompressedSize; // 0 if it isn't compressed
};

char magic[4];
uint NumFiles;
uint OffsetData;
uint OffsetStringTable;
uint StringTableSize;

Entry directory[NumFiles];
```

This is the correct one. Files may be compressed (best compression level) with zlib(otherwise DecompressedSize is 0).  Decompress them with [zlibc](http://www.gameformats.de.vu/index.php?cat=progs&site=zlibc).
## Post #7
- Username: Rafulpower
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 15, 2007 1:15 am
- Post datetime: 2007-11-21T02:35:28+00:00
- Post Title: Silent Hill Origins - ARC archive

Wow.. thank you very much. Excuse my ignorance, but I don't know how to run zlibc.exe!

How do I do to extract files from SH.arc using zlibc.exe?

Thanks.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-21T02:39:10+00:00
- Post Title: Silent Hill Origins - ARC archive

Oh I'm sorry, I didn't mention zlibc is a pure zlib de-/compressor.
It is no ARC unpacker.
You have to extract the files manually, then you can use zlibc to decompress them.
## Post #9
- Username: Rafulpower
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 15, 2007 1:15 am
- Post datetime: 2007-11-21T02:42:48+00:00
- Post Title: Silent Hill Origins - ARC archive

Right.. I will try. Thank you once again.
## Post #10
- Username: zakos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 15, 2008 3:59 am
- Post datetime: 2008-02-16T12:36:04+00:00
- Post Title: Silent Hill Origins - ARC archive

> Reply from Rheini
>
> Oh I'm sorry, I didn't mention zlibc is a pure zlib de-/compressor.
It is no ARC unpacker.
You have to extract the files manually, then you can use zlibc to decompress them.

And how can I extract the files manually?I cant extract it with any app.
Which application did you use tu unpack sh.arc archive?
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-16T13:11:53+00:00
- Post Title: Silent Hill Origins - ARC archive

A hex editor, that's why I said "manually" i.e. by hand.
I use [010 Editor](http://www.sweetscape.com/010editor/), the code I posted above is a 010 binary template.
## Post #12
- Username: zakos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 15, 2008 3:59 am
- Post datetime: 2008-02-16T13:20:29+00:00
- Post Title: Silent Hill Origins - ARC archive

> Reply from Rheini
>
> A hex editor, that's why I said "manually" i.e. by hand.
I use 010 Editor, the code I posted above is a 010 binary template.

Ohh,now everything is clear!
Danke Besten Rheini
