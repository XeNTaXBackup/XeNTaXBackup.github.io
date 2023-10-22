## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-02T13:54:25+00:00
- Post Title: DXT Filesize

I have a DXT file, with the following header:

```
00 02 00 00 00 80 00 00 00 00 00 00 0A 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 20 00 00 00
04 00 00 00 44 58 54 33 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 08 10 40 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00

```


It's a 0x40 by 0x200 (64 by 512) DXT3 compressed file with 0xA (10) mipmaps.
To compute the filesize, it's basically 128 bytes (header) + image data size. I
compute the image data size using:

512 * 64 * 4 = 131072 uncompressed level 1 bytes
512 * 64 * 1 = 32768 compressed level 1 bytes

level 1: 32768
level 2: 8192
level 3: 2048
level 4: 512
level 5: 128
level 6: 32
level 7: 16 (minimum block size reached)
level 8: 16
level 9: 16
level 10: 16
------------------------
total size = 43,872 bytes

However, the actual filesize is listed as 43,920 bytes, 0x30 or 48 bytes extra, which are all zeros. Is there something I've forgotten in my calculation? The silly game I'm working on extracting textures out of is a list of DDS, BMP and TGA files and I need to be able to calculate the filesizes for all DDS files correctly.

Thanks

EDIT:

Hmm.... 

1: 32768 - 512 x 64
2: 8192 - 256 x 32
3: 2048 - 128 x 16
4: 512 - 64 x 8
5: 128 - 32 x 4
6: 32 - 16 x 2 -> 16 x 4 actually 64 - +32
7: 16 - 8 x 1 -> 8 x 4 actually 32 - +16
8: 16 - 4 x 1 -> 4 x 4
9: 16 - 2 x 1 -> 4 x 4
10: 16 - 1 x 1 -> 4 x 4

I guess that adds 48?
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-02T20:44:05+00:00
- Post Title: DXT Filesize

Lol solved  silly me.  

Rant: stupid game uses dds dxt1 dxt3 dxt4 dxt noncomp dds, tga,  rle tga,  and even ffing windows bmp for textures. This game was programmed by a retard lol. If my parser runs into png and gif imma rant some more mmorpg sux ass.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-04T09:22:03+00:00
- Post Title: DXT Filesize

lol, this game's models are modeled in a pose. how strange.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-29T14:50:56+00:00
- Post Title: DXT Filesize

The extra zeroes are just padding to make it 16-byte aligned?
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-04T01:17:21+00:00
- Post Title: DXT Filesize

oh, I didn't see this earlier ha ha ha. lol this thread brings back memories... I was working on that shitty game, heroes of thessolonica or something like that. there was even photoshop PSD files stored in the archive of textures to boot. And at that point I had given up on that game cuz the models sucked and it was too much work to extract shitty models. Whoever their programmer for that game is, he is a big retard. I have never seen a game use so many different texture formats before.

padding, yes; 16-byte alignment no. DDS files that use DXTn compression store data in 4x4 blocks, so even if you have a 256x1 DXT1 DDS, the actual filesize is 256x4, with the last three rows padded with zeros. this padding also affects stored mipmaps, which I wasn't accounting for. In the EDIT section of the first post I had corrected all the 1's to 4's and that became the basis for my current DDS code.
