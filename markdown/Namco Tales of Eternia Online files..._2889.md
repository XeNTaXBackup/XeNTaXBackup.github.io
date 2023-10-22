## Post #1
- Username: Lamhirh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 02, 2008 7:13 am
- Post datetime: 2008-01-03T20:56:28+00:00
- Post Title: Namco Tales of Eternia Online files...

I people,

I'd like to know if someone could help  me to find a solution to extract graphic files from Tales of Eternia Online.

Here's an attachment containing 3 different types of files.

bnd, pkd, mpd.

Thx in advance  
[TOEO.rar](https://xentaxbackup.github.io/file/1419_TOEO.rar)
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-01-04T16:14:27+00:00
- Post Title: Namco Tales of Eternia Online files...

Here there are the basic file details about PKD files.

They're used to store files (probably, it means PacKeD)...

File header:
(all field are little endian)

(char[4]) magic "PKDF"
(int) reserved?
(int) version?
(int) number of entries
(int) size of the file table - 4 (not sure what it's used for)
(int) size of the header
(int) size of the file table
(int) number of files (number of entries - 1)

Entries:
All entries have 32 bytes

1st entry
(int) Offset (always 60?)
(20 bytes) SHA1 hash of the block
(int) Filesize
(int) Pointer to the unknown zone

All other entries (files)
(int) Offset
(int) Filesize
(20 bytes) SHA1 hash of the file
(int) Pointer to the unknown zone

I'm not sure about what the unknown zone between the file offsets and the content is used for. Maybe encrypted filenames?
## Post #3
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-01-04T17:23:34+00:00
- Post Title: Namco Tales of Eternia Online files...

Here's an small unpacker (in C). The file names are just obtained from the 4 first characters of every file.

I think that the section after the file names is encrypted, too. If you go to the the part after it, there's something like:

(8 byte) ???
(int) Size of something (probably the filename)
(Filename?)
(int) Size of something
...

In both files, the file name table entries start with the same 4 bytes. This could mean that the filename (if it is the filename) is inverted. I've tried the possible extensions (".clt", ".a??", etc...) but I can't see any relation. Any help?
[PKDF.rar](https://xentaxbackup.github.io/file/1420_PKDF.rar)
## Post #4
- Username: Lamhirh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 02, 2008 7:13 am
- Post datetime: 2008-01-04T18:52:08+00:00
- Post Title: Namco Tales of Eternia Online files...

Thx for the info, gonna try that unpacker  

I'm still trying to figure out how to decode those graphics.

TOEO I'll rip your sprites, yes I'll do
## Post #5
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-01-05T10:23:48+00:00
- Post Title: Namco Tales of Eternia Online files...

I'm not an expert in graphics, but the "bkn" header seems to be:

(char[4]) "BKND" (magic)
(int) version
(int) number of entries
(40 bytes * number of entries) entries

Each entry

(int) filesize
(int) offset
(32 bytes) identifier?

No idea about the files inside it. I think that there's a palette
## Post #6
- Username: Lamhirh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 02, 2008 7:13 am
- Post datetime: 2008-01-09T22:22:54+00:00
- Post Title: Namco Tales of Eternia Online files...

Hmm I guess I will have to forget about that game tilesets...

Too bad
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-10T00:22:33+00:00
- Post Title: Namco Tales of Eternia Online files...

I doubt that data is filenames. Just look at those 12 bytes that are always the same.

As well I think it must be like that:

```
	uint offset;
	byte SHA1[20];
	uint filesize;
} firstEntry;

struct Entry {
	uint pointerUnknownZone;
	uint offset;
	uint filesize;
	byte SHA1[20];
}entries[numFiles];
```

Oddly enough the last entry in that file area is only 16 bytes long (cause file data starts after it) though those entries should be 20 bytes in size regarding the structure and the pointer values. 
[hex.JPG](https://xentaxbackup.github.io/file/1423_hex.JPG)
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-10T00:41:41+00:00
- Post Title: Namco Tales of Eternia Online files...

Would need the executable and all dlls to say more.
## Post #9
- Username: Lamhirh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 02, 2008 7:13 am
- Post datetime: 2008-01-12T16:10:58+00:00
- Post Title: Namco Tales of Eternia Online files...

No problem, here's an attachment with the content of the game exec files folder.

[http://www.yvchina.com/files/toeo/toeonline.rar](http://www.yvchina.com/files/toeo/toeonline.rar)

Do not hesitate to ask for any other files. Some bnd's and other files come in a variety of sizes.
## Post #10
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-01-13T11:02:33+00:00
- Post Title: Namco Tales of Eternia Online files...

I have no idea about how to convert the BND entries to TGA (they're images, right? I will seem completely retarded if they aren't   ).

Here's what I have now   

```
{
       int unknown1;
       int unknown2;
       int unknown3;
       int size_image_data;
       int unknown4;
       int entries_palette;
} __attribute__((packed));
```


After this, there's some data that seems a palette of 1024 bytes (256 entries * 4 bytes/pixel).

And after this, there should be the image data. But I always get a lot of junk     

Also, a thing to extract the contents of the BND file... but it isn't too much useful since we don't know what to do with the files  
[BNDExtract.zip](https://xentaxbackup.github.io/file/1425_BNDExtract.zip)
## Post #11
- Username: Lamhirh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 02, 2008 7:13 am
- Post datetime: 2008-01-23T22:20:35+00:00
- Post Title: Namco Tales of Eternia Online files...

Well thanks for your attempts, I'm currently looking in Japanese forums to see if someone might have found a way to extract those resources.

Tales I'll rip you, yes I will. 

(If you need some other files to run some tests just tell me I'll upload some more)
