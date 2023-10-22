## Post #1
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2023-07-27T22:27:54+00:00
- Post Title: Gameloft AMZ fails to extract

Sooo Zenhax is dead so I guess I'll move here, there's an issue using order_chaos_online.bms from aluigi. There are two variants that fail to extract, versionless, 101, 102 ,103. Versionless works with the original code with simple modifications but doesn't include the version string and alignment variable. 102 was introduced sometime in Disney Magic Kingdoms (?) 3.5.0+. It's mostly identical to 101, but uses ZStandard and I think int64 values for I think the offset. 103 (DMK 3.0.0?) introduced two I64s(?) after the size, there's also 64 bytes after the info size for the first entry I don't know about that appears before the file data (unless that's part of the astc file in ./config). Any plans to fix it? Thanks.

[https://workupload.com/file/4CX3DWXNBcW](https://workupload.com/file/4CX3DWXNBcW)

UPDATE: I made this mod which supports all of DMK's files from my testing, not sure about ./config/astc, I gotta download it on an actual device to check accuracy.
[https://raw.githubusercontent.com/LolHa ... IP_MOD.bms](https://raw.githubusercontent.com/LolHacksRule/GameFileFormatsRE/main/Gameloft/GameloftAndroidMarketZIP_MOD.bms)
