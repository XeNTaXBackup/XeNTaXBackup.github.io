## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-06T15:49:47+00:00
- Post Title: need help with compression

I've attached 3 files from Settlers 2: 10th Anniversary. data.lua is the original file, data.lua.decrypt is the decrypted one and data.lua.decomp is the decompressed one.
Can someone help me identifying the compression algorithm? the structure of data.lua is

```
int uk; // header
int fcc; // header
int datacrc; // crc32 checksum of decompressed data
int pwcrc; // not sure about this
int datasize; // decompressed data size
};
after that crypted data
```

[files.rar](https://xentaxbackup.github.io/file/1016_files.rar)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-07T20:13:11+00:00
- Post Title: need help with compression

Noone can help? 

Any hint would be appreciated.
## Post #3
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-01-09T00:24:12+00:00
- Post Title: need help with compression

Just as a public update, in case anyone else follows this: Rheini sent me a private message, suspecting an LZSS compression on these files, which was quite correct (though the parameters are somewhat unusual). The current work result is attached.
[DeLZSS_2.zip](https://xentaxbackup.github.io/file/1021_DeLZSS_2.zip)
