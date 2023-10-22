## Post #1
- Username: powoct
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 12, 2011 5:59 pm
- Post datetime: 2013-10-30T09:43:36+00:00
- Post Title: Compression Question for <iOS - Tales of Hearts R>

I like this game very much and want to translate it. After I unpacked the game, I found that the text files were compressed. It is not simple LZ compression because I cannot find the 01 / 10 / 11 file header. And I did not find any file length information. Is anyone know how to decompress this files? Could you help me to take a look. Thanks very much.

Here are some compressed files:(xxx.bin)
[tohr.zip](https://xentaxbackup.github.io/file/6741_tohr.zip)
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2013-11-04T11:14:33+00:00
- Post Title: Compression Question for <iOS - Tales of Hearts R>

The 0x01/0x10/0x11 (and 0x20/0x30/0x40 actually..) are the flag for the nintendo BIOS  compression, it's normal that you don't find them in a iOS port..
