## Post #1
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2016-07-20T09:09:00+00:00
- Post Title: Life Is Strange .XXX Compress Files (PS3)

Hi everyone 

I want help with compress xxx files in Life Is Strange ps3 version 
i able to decompress files using offzip and edit what i want in hex editor 
so from what i know unreal engine 3 in ps3 xxx files should be compressed because i tried to run my edit and it seem not work like pc which it able to run decompress files.
so is there anyway to compress files again 
i tried to re-import by offzip but my edit file bigger than original

here example file and compressed
[EXAMPLEGAME_LOC_INT.rar](https://xentaxbackup.github.io/file/11305_EXAMPLEGAME_LOC_INT.rar)
## Post #2
- Username: Sura Modder
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-22T15:30:47+00:00
- Post Title: Life Is Strange .XXX Compress Files (PS3)

```
{
	unsigned int m_compressedDataSize;
	unsigned int m_uncompressedDataSize;
};

struct xxx
{
	unsigned int m_magic;                         //0x9E2A83C1
	unsigned int m_totalZlibData;                 //Entire size of zlib data
	unsigned int m_totalUncompressedData;         //Size of file when uncompressed
	struct compressedEntry[6];
};

```
