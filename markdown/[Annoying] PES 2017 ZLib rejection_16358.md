## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-06-04T13:53:55+00:00
- Post Title: [Annoying] PES 2017 ZLib rejection

Hi, I am pretty familiar with the file format for the pro evo series but i have come across some files that refuse to unzip

```
{
   char magic[8]; // "\x00\x10\x01WESYS"
   uint32_t cmprSize;
   uint32_t uncmprSize;
   uint8_t wesys[cmprSize]; // Uncompress with Zlib
}

```

The general structure is as stated above but this file has a different magic[8]

```

```


Here is a sample

 bill_body.zip
(28.71 KiB) Downloaded 18 times
