## Post #1
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2012-11-13T02:36:13+00:00
- Post Title: KKND 1&2 Image compression

Hello, i managed to extract the assets and images for KKND 1 & 2 - however some images are packed. Repeating patterns of multiple bytes are packed in a way i cannot find the correct sollution for.

After i found a file i could identify, i made an ingame screenshot and inserted pixel by pixel manualy at the points where the image went wrong, so i found out all places wich are packed. Because i now knew what pixels have to be inserted i created a simple logger which logs all offsets where pixels are packed, and also their packed-bytes and unpacked-bytes.

This is the output: [http://pastebin.com/g41ciWew](http://pastebin.com/g41ciWew)
Also as attachment the image after i did the replacements manualy - where you can see that the output is correct. (its actualy a not fully build-up wall from kknd2 - survivors faction)

So basicaly what im missing is the correct way to read the compressed bytes and to extract a) which bytes have to be written at this position and b) at which position the next compression occurs.

If i should provide any other stuff like the compressed but extracted raw image file, and the uncompressed (manualy replaced) raw image file (so before palette applied output png), just tell me, and ill upload them.

Thanks for all help! 
[3441.png](https://xentaxbackup.github.io/file/5985_3441.png)
## Post #2
- Username: jonwil
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 05, 2011 5:58 pm
- Post datetime: 2012-11-14T16:14:58+00:00
- Post Title: KKND 1&2 Image compression

Based on the age of the game and what I see in the info, I suspect this is some form of RLE.
## Post #3
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2012-11-16T04:44:29+00:00
- Post Title: KKND 1&2 Image compression

Some patterns i could find:
01 81 0f > 00 0f
81 0f 01 > 0f 00
1A 00 96 > 00

looks like those replacements are the same always, still not sure if it packs "00 0f" or simply the "00" only and the "0f" is basicaly an unpacked character
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-16T16:25:17+00:00
- Post Title: KKND 1&2 Image compression

> Reply from IceReaper
>
> If i should provide any other stuff like the compressed but extracted raw image file, and the uncompressed (manualy replaced) raw image file (so before palette applied output png), just tell me, and ill upload them.

i'm not beaten yet - could you upload these?

i copied out your rle file without any uncompressed data:

> 08 00 08 86 0D 00 06 8B 0E 00 05 8C 0E 00 05 8C
>
> 0E 00 05 8C 15 00 02 93 17 00 01 95 18 00 97 1A
>
> 00 96 01 81 0F 18 00 97

and you can sort of parse it (up to a point) with this pseudocode

```
byte values

compressed data length is unknown to me right now

if control1 & 0x18 == 0x18
> byte hint
else
> byte control2
> byte hint

uncompressed data is ( hint ^ 0x80 ) in length


```


this breaks when control1 is 0x01 (are there any values? the next bytes are 81 0F - or 1x 0F byte)

hopefully with more data i can find other patterns
## Post #5
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2012-11-16T18:16:27+00:00
- Post Title: KKND 1&2 Image compression

Okay, here is the raw file - compressed and uncompressed (manualy replaced bytes in the uncompressed one and converted it via palette to verify that its correct)

oh: before i forget that: there is another image (partialy) at the end of the compressed one - at offset 1FF a new image starts - 8 bytes header (width, height) and then image data...
[3441.zip](https://xentaxbackup.github.io/file/5999_3441.zip)
## Post #6
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2012-11-19T15:12:15+00:00
- Post Title: KKND 1&2 Image compression

Ah.. also if this is more helpful: i attached a complete packed sprite-file, which is build like this:
Header-table1 - not sure what it includes or how to read it, i just read an int at offset 4 which points to the table2 entry
Header-table2 - also not sure what it includes or how to read it, reading offset from above + 8 will point to the third table.

Header-table3 has entries for each packed sprite which is exactly 16 bytes long:
4bytes is either 0x53504e53 or 0x53505243 - not sure what it is.
4bytes is 0 (for unpacked images) or something else for packed ones
4bytes is a pointer to some unknown data at sprite-container-file-end
4bytes it the offset to the file itself

Followed now by each image in the format:
4bytes imageX
4bytes imageY
<image data...>

After the last image comes some unknown data, which is referenced from above.

Hope this helps somehow?
[unit1.zip](https://xentaxbackup.github.io/file/6008_unit1.zip)
## Post #7
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2012-11-24T00:58:56+00:00
- Post Title: KKND 1&2 Image compression

Check this out:
08 00 08 86 29 2C 2C 68 2A 68
8 bytes of compressed data
8 transparent pixels 6 (86-80) normal pixels: 29 2C 2C 68 2A 68

18 00 97 72 72 6E 67 67 6C 84 8E BF B7 B7 BE BE 8F 1F 24 1D 6E 66 63 21 1D 0F 
0x18 bytes of compressed data
0x17 normal pixels (97-80)

0E 00 06 89 0F 03 03 03 03 02 02 08 1C 01 81 0F 
0xE bytes of compressed data
6 transparent pixels 9 normal pixels (89-80) 1 transparent pixels 1 normal pixels (81-80)
## Post #8
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2012-11-25T17:46:30+00:00
- Post Title: KKND 1&2 Image compression

Thanks - that worked! Show-off:


However - this only works if the compression flag in the header is "0000000c".
The other flags which do not work:
0x0000008c
0x03000008 (as in the file i posted above)
0x03000088
0x00000080 (this one looks good without applying any compression logic)
## Post #9
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2012-11-25T20:43:38+00:00
- Post Title: KKND 1&2 Image compression

Looks great 
I just had a look at the file in unit1.zip, sprite1.hex @ 0x77C:

```
17 00 00 00	# image height

06 0A 81 60 04 81 80	# 1st line
8E 00 00 00 00 08 60 80 95 07 00 90 00 00 00	# 2nd line
0D 07 81 80 02 89 55 65 48 85 50 01 81 60	# 3d line
0C 05 81 60 01 8E 85 55 84 82 85 58 55
8E 00 00 05 88 88 83 33 44 44 88 58 08 00 00
8E 00 06 05 88 34 31 11 11 12 43 45 58 00 00
8E 00 56 05 C4 22 23 22 21 22 12 43 8C 56 00
0D 03 96 58 A3 42 35 84 42 43 22 12 33 C8
8E 88 5B 8C 46 85 54 54 45 44 32 12 43 8C 00
8E 08 55 55 48 55 88 45 54 64 44 21 12 85 00
8E 00 8A 84 85 85 85 55 58 44 53 32 21 8C 00
8E 08 EB E8 85 85 5B 55 53 55 54 51 13 58 C0
8E 85 0E EE 55 65 88 55 88 85 55 32 22 58 00
8E 00 EE CB 45 45 55 88 58 85 88 32 54 85 00
8E 0A CC 8C E6 58 B8 88 88 88 85 44 18 48 50
8E 0B 58 0B 8C E6 88 88 5B B8 84 55 85 50 00
8E B0 00 58 8B 86 84 58 85 88 55 5B 85 05 00
8E 00 08 98 08 88 8B FC 88 9C 5B 88 86 00 00
0C 06 93 A8 BC 8B E8 58 FE 5B 8B 58 50
8E 00 00 00 05 80 88 E5 85 88 4C 55 00 80 00
8E 00 00 00 5C 00 8E 08 05 EC 85 50 80 00 00
8E 00 00 00 00 00 C0 05 08 0C 08 00 00 00 00
06 0F 81 60 04 81 60
```
The first byte of each line tells us how many bytes we will have to read.
If the value is greater than 0x80, then the following bytes are not compressed.

Let's have a look at the third line:
0D 07 81 80 02 89 55 65 48 85 50 01 81 60
0xD bytes of compressed data
7 transparent pixels-1 normal pixel-2 transparent pixels-9 normal pixels-1 transparent pixel-1 normal pixel
0000000-8-00-556548855-0-6

The remaining pixels are all transparent, this is how the line looks uncompressed:
00 00 00 08 00 55 65 48 85 50 60 00 00 00

This is the uncompressed data of the first sprite:

```
00 00 00 00 08 60 80 95 07 00 90 00 00 00
00 00 00 08 00 55 65 48 85 50 60 00 00 00
00 00 06 08 55 58 48 28 55 85 50 00 00 00
00 00 05 88 88 83 33 44 44 88 58 08 00 00 
00 06 05 88 34 31 11 11 12 43 45 58 00 00
00 56 05 C4 22 23 22 21 22 12 43 8C 56 00
00 05 8A 34 23 58 44 24 32 21 23 3C 80 00
88 5B 8C 46 85 54 54 45 44 32 12 43 8C 00
08 55 55 48 55 88 45 54 64 44 21 12 85 00
00 8A 84 85 85 85 55 58 44 53 32 21 8C 00
08 EB E8 85 85 5B 55 53 55 54 51 13 58 C0
85 0E EE 55 65 88 55 88 85 55 32 22 58 00
00 EE CB 45 45 55 88 58 85 88 32 54 85 00
0A CC 8C E6 58 B8 88 88 88 85 44 18 48 50
0B 58 0B 8C E6 88 88 5B B8 84 55 85 50 00
B0 00 58 8B 86 84 58 85 88 55 5B 85 05 00
00 08 98 08 88 8B FC 88 9C 5B 88 86 00 00
00 00 00 A8 BC 8B E8 58 FE 5B 8B 58 50 00
00 00 00 05 80 88 E5 85 88 00 00 00 00 00
00 00 00 5C 00 8E 08 05 EC 85 50 80 00 00
00 00 00 00 00 C0 05 08 0C 08 00 00 00 00
00 00 00 00 00 00 00 06 00 00 60 00 00 00
```

By the way, 76 1A 00 00 in the Header-table3 probably points to the color palette (16 colors).
## Post #10
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2012-11-27T14:12:00+00:00
- Post Title: KKND 1&2 Image compression

First: Thanks for all your help!
one more single correction which you figured out wrong:

the correct output is actualy:
00 00 00 00 00 00 00 ?? 00 00 ?? ?? ?? ?? ?? ?? ?? ?? ?? 00 ??

so every pixel or palette color is packed into 4 bit somehow - still not sure how that works, if you have anything else i could need, i would be very thankful!
