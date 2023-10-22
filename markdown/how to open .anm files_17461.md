## Post #1
- Username: adam0000
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jul 23, 2015 6:34 am
- Post datetime: 2017-12-27T06:35:34+00:00
- Post Title: how to open .anm files

noesis, blender, 3ds max, do not open

[https://mega.nz/#!ZXwnTLAD!EyC-YOQEEkHo ... nCmlNUn2Mo](https://mega.nz/#!ZXwnTLAD!EyC-YOQEEkHoazPbZ7zYHUNQ7rcQbVc7CnCmlNUn2Mo)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-12-27T09:07:51+00:00
- Post Title: how to open .anm files

We could use some info from what game/software you got this file.
TrID doesn't show anything. It is custom structure-file. No known header. It doesn't look like it even have MAGIC

File is little-endian

Structure so far:

```
0x04 - Unknown pointer??
0x1C - Same structure as 0x00 > Next section?
0xA8 - Data section header. Every pointer from now on is RELATIVE!

```


Data section:

```
0x04 - Size of pointers
0x08 - Relative pointer DWORD
0xYY - Data entry (32 bytes ALWAYS)

```


Example:
0xA8 start data section. First pointer at 0xB4 is: 280 (decimal).
Now add 0xA8 + 280 (decimal) to get address = 0x1C0 which is first data entry


Data entry (32 bytes):

```
0x04 - Always 01 00 (short)
0x06 - Incrementing ID (ushort)
0x08 - Always zero/ Padding?
0x0C - Always 16, data size? (16 bytes to end of data entry)
0x10 - Unknown dword, maybe float?
0x14 - Same as 0x10
0x18 - Same as 0x10
0x1C - Same as 0x10

```


File extension .anm may show it's animation file. Increasing ID may be frame IDs. I can't help you more at this moment. This is all I could read from binary-level.
## Post #3
- Username: adam0000
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jul 23, 2015 6:34 am
- Post datetime: 2017-12-30T09:07:53+00:00
- Post Title: how to open .anm files

> Reply from MaKiPL
>
> We could use some info from what game/software you got this file.
TrID doesn't show anything. It is custom structure-file. No known header. It doesn't look like it even have MAGIC


File extension .anm may show it's animation file. Increasing ID may be frame IDs. I can't help you more at this moment. This is all I could read from binary-level.

thanks for answering
I got these files after extracting q with the aliugi script yugioh_duel

[https://zenhax.com/viewtopic.php?t=3816](https://zenhax.com/viewtopic.php?t=3816)
