## Post #1
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2006-01-05T18:05:31+00:00
- Post Title: UFO Aftershock vfs

anyone looked at this yet.. if not
i would love if someone could have a go

included is both a cutted (5mb maingame bigfile)
and a complete smaller archive (localization)
probraly txt

[http://rapidshare.de/files/10458178/packedUFO.zip.html](http://rapidshare.de/files/10458178/packedUFO.zip.html)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-05T19:19:47+00:00
- Post Title: UFO Aftershock vfs

Hi mate .... please test VFSTool for UFO....

You can download VFS plugin for Total Commander here
[http://www.geocities.com/sigget2003/UFO_tcvfs_v01.zip](http://www.geocities.com/sigget2003/UFO_tcvfs_v01.zip)

Download VFS Tool v1.3 here
[http://www.geocities.com/sigget2003/UFO ... ol_v13.zip](http://www.geocities.com/sigget2003/UFO_vfs_tool_v13.zip)

And visit this site 
[http://www.strategycore.co.uk/ufo/](http://www.strategycore.co.uk/ufo/)

Enjoy
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-05T19:28:17+00:00
- Post Title: UFO Aftershock vfs

VFS File Specification

```

Name :                            Size :

header                             sizeof(header)
fat table                           clustercount*sizeof(fat_entry)
root directory                   maxrootfiles*sizeof(file_entry)
clusters                            clustersize*clustercount

The header describes the file system. It contains version information, sizes and limits of the system and an md5 checksum that is computed using the normal md5 algorithm. The header is followed by the fat table, which has one entry for each cluster in the volume and describes what clusters are used and how the clusters are linked together to form files. The root directory is a fixed-size area that contains the file entries for the root files/directories. Directories are normal files that contains sequences of file_entry. And last are the clusters.

Structures

struct header
{
  float  version             // format version, always 1.0
  uint32 clustersize         // observed values are 160 and 4096
  uint32 clustercount
  uint32 maxrootfiles        // 32 in save games, otherwise 64
  uint32 zero                // could be that maxrootfiles is 64bit, but its not very likely
  uint32 filenamelength      // always 64
  uint32 windowsize          // for compressed data, always 50000
  char   md5sum[16]          // calculated from offset 44 to EOF
  uint32 versionstringlength // always 256
  char   versionstring[256]
  uint32 usedclusters
}

struct file_entry
{
  char   name[64]             // padded with '\0'
  char   unknown1[4]          // unknown, not used by the game
  uint32 type                 // 1=file,2=directory,9=compressed file
  char   unknown2[4]          // always 0xFFFFFFFF
  uint32 startcluster         // one-based
  uint32 size
  uint32 size_uncompressed    // 0 if uncompressed
}

struct fat_entry
{
  uint32 usage                // 0=unused,1=used
  uint32 nextcluster          // 0xFFFFFFFF to signal end cluster
}

Compressed streams

The compressed files, type 9, are series of compressed chunks. The compression library is used is regular zlib. Each uncompressed chunk is at most the size of windowsize from the header. Before each chunk is a marker, uint32, that describes the size of the chunk. Then follows the compressed data. On some files the last marker is repeated after the last chunk, this is probably caused by a bug in the generator tool. 
Notes

Always respect the size of a file. One many of the files the last cluster contains some extra data that isnt used. This is especially true for directories. Apparently Altar's vfs packing utility reused buffers when creating directories, because of this the last part of directories contain data from previous directories. So if you overread directories you'll get a file system with hard links.

In the type field of file_entry the gap between 2 and 9 could be the result of bit 3 being a flag that signals compression, this way, theoretically there can be compressed directories.

Cluster indices range from 1 and up to and including clustercount

Issues of the format

Problems and downsides of the way this format was designed.
Clusters arent stored at efficient offsets.Cluster sizes found on ntfs and fat are always 2^x and the most common size nowadays is probably 4096. Due to this fact reads and writes to files are more efficient when they align to cluster boundaries. For example, when reading 500 bytes and the first 200 is in one cluster and the rest is in the next cluster two clusters will have to be read in. While if the whole 500 bytes were in the same cluster there would be one cluster read. The VFS-format could exploit this by storing its clusters on even cluster boundaries, so that a vfs cluster perfectly matches a cluster on disk. One way of achieving this as the format looks now would be to extend to version string so that the fat-table starts at offset 4096. And then use a fat-table with a size dividable in 4096, since a fat_entry is 8 bytes and 4096/8 is 512, use multiples of 512 as your clustercount. I'm still unsure of what performance increases this can give.
```
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-01-06T00:00:43+00:00
- Post Title: UFO Aftershock vfs

i already wrote an extractor.  A week later, the company that wrote it, released a program to extract and create the files for you, and that was for UFO: Aftermath, VFS (Virtual File System) hasn't changed in UFO: Aftershock.  Besides the MD5 checksum and header, the file is almost exactly like FAT32.
