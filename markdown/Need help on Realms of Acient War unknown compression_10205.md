## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-03-08T08:18:52+00:00
- Post Title: Need help on Realms of Acient War unknown compression

I need help on these textures which suppose to use their own compression method to compress the texture.
This game engine is called Shine-Engine and I am pretty sure the compressed texture are actually DDS files!
form what I got:

char[12]     Compression_Header     //SHCOMPRESSED
dword        UnCompress_Size
...

And I guess the data are start at 0x20. But then I loss.
Please help. 
Thanks in advance.
[RAW_Texture.zip](https://xentaxbackup.github.io/file/6247_RAW_Texture.zip)
## Post #2
- Username: fatduck
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-08T11:58:09+00:00
- Post Title: Need help on Realms of Acient War unknown compression

```
#quickbms script by chrrox
#http://www.raw-thegame.com/
comtype LZMA
get zsize asize
get name basename
string name + ".dds"
math zsize - 0x20
idstring "SHCOMPRESSED"
get size long
clog name 0x20 zsize size
```
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-03-08T17:56:30+00:00
- Post Title: Need help on Realms of Acient War unknown compression

I did try comtype scan on the files but couldn't find anything! Strange!!!
Thanks!
