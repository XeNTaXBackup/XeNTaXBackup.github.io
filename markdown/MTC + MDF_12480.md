## Post #1
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2015-01-07T19:40:31+00:00
- Post Title: MTC + MDF

Any script to pack/unpack data from this files? (images, text, maps...)

[https://www.sendspace.com/file/thbepe](https://www.sendspace.com/file/thbepe)

Game: Monaco

Thanks for your help!
## Post #2
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-01-12T12:20:39+00:00
- Post Title: MTC + MDF

```
//--- 010 Editor v6.0 Binary Template
//
// File: .mtc in monaco
// Author: MiRiKan
// Revision: 1.0
// Purpose: unpacking monaco files
//--------------------------------------
local uint i, pos0, pos1;
uint header;
uint count;

struct pointers{
    for (i = 0; i < count; i++){
        struct _POS{
            uint pointer;
            pos0 = FTell();
            FSeek(pointer);
            uint _pos;
            uint _ID;
            pos1 = FTell();
            FSeek(_pos);
            uint unk;
            uint unk <hidden=true>;
            uint realpointer; //pointer for .mdf
            uint unk <hidden=true>;
            uint unk;
            uint64 realFileSize; // files in .mdf
            FSeek(pos0);
        }Data;
    }
}data;
```


it looks nonencrypted files in .mdf. but i can not find any name of file, so that i can not make unpacking tool as easy.
making tool now...
## Post #3
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2015-01-12T13:05:42+00:00
- Post Title: MTC + MDF

Thank you MiRiKan. Good luck with that
## Post #4
- Username: swixel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 29, 2015 11:04 am
- Post datetime: 2016-10-17T23:08:33+00:00
- Post Title: MTC + MDF

> Reply from MiRiKan
>
> it looks nonencrypted files in .mdf. but i can not find any name of file, so that i can not make unpacking tool as easy.

Just dump to keys when that happens? 

---

Anyway, the reason I'm replying is I've been sitting on this for years now ... I fully intended to post this when I saw it last January, but things got out of hand and I forgot.  Someone just reminded me I need to rebuild the safe code for release so here's the name list a bit early.

As I rewrote part of my old Monaco code in Go in 2014-2015 I have this in a Go file with it which should help you if you need it ... typically you'd build a lookup table, but since I usually write daemons for modding (tcp/ip connections for requests to save time/lookup nonsense for offsets on data I want cached) I keep JSON dumps 

Here's the Go code snippet I kept with it in dropbox:

```
	"hash/crc32"
	"path/filepath"
)

// StringCRC32 does case sensitive CRC32 calculations for Monaco.
func StringCRC32(raw string) (crc int32) {
	crc = 0
	p := []byte(raw)
	for _, v := range p {
		crc = int32(crc32.IEEETable[uint8(crc^(int32(v)&0xFF))]) ^ (crc >> 8)
	}
	return
}

// StringICRC32 does case insensitive CRC32 calculations for Monaco.
func StringICRC32(raw string) (crc int32) {
	crc = 0
	p := []byte(raw)
	for _, v := range p {
		crc = int32(crc32.IEEETable[uint8(crc^(int32(v)&0xDF))]) ^ (crc >> 8)
	}
	return
}

// PlatformStringCRC32 is used for filename calculation (sensitive)
func PlatformStringCRC32(raw string) (crc int32) {
	plat := filepath.Clean(raw)
	crc = StringCRC32(plat)
	return
}

// PlatformStringCRC32 is used for filename calculation (insensitive)
func PlatformStringICRC32(raw string) (crc int32) {
	plat := filepath.Clean(raw)
	crc = StringICRC32(plat)
	return
}

```


Due to size limitations the name list is in the original JSON form (a 7ziped .txt file).  I got the names by using pattern based brute-forcing and CRCing them.  Given all of that you should be able to repackage if you want.

Notably the CRC differs marginally, here it is without all of the casting hell to clarify the difference:

```
// crc ^ (byte & mask)
crc = crc32_tab[crc^(v & 0xFF))] ^ (crc >> 8)

// Normal
// (crc ^ byte) & mask
crc = crc32_tab[(crc ^ v) & 0xFF] ^ (crc >> 8)

```

[magazine_filenames.7z](https://xentaxbackup.github.io/file/11800_magazine_filenames.7z)
