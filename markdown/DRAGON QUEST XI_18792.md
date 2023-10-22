## Post #1
- Username: Zolodei
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 19, 2017 2:15 am
- Post datetime: 2018-09-09T20:20:13+00:00
- Post Title: DRAGON QUEST XI

Hi, do tell me, which algorithm to use for encryption?

> Structure_PAK (EndFiles - Structure_PAK)
>
> 00 04 Hender (0x5a6f12e1)
>
> 04 04 Version
>
> 08 08 Offset_DATA00
>
> 12 08 Size_DATA00
>
> 24 20 HASH_SHA1
>
> 
>
> Structure_DATA00
>
> 00 04 Size_Text
>
> 04 ?? Text
>
> ?? 04 Number Data01
>
> 
>
> Structure_DATA01
>
> 00 04 04 LengthText Unicode (NEG Number)
>
> 04 ?? LengthText FilePath Unicode(KEY_XOR: 0xDE00AD00FA00DE00BE00EF00CA00FE00)
>
> ?? 00 08 OffsetData
>
> ?? 08 08 Size
>
> ?? 16 08 zSize
>
> ?? 24 04 Pack
>
> ?? 28 20 HASH_SHA1
>
> 
>
> Pack = 0
>
> 00 04 Number
>
> 04 01 Unknown00
>
> 
>
> Pack = 1 | KEY_XOR: 0xDEADFADEBEEFCAFE , (DataFiles  XOr KEY_XOR) XOr $FF, zlib
>
> 00 04 Number
>
> 04 (Number * Structure_DATA02) 
>
> ?? 01 Unknown00
>
> ?? 04 zSize
>
> 
>
> Structure_DATA02
>
> 00 08 OffsetStart
>
> 08 08 OffsetEnd
[DRAGON_QUEST_11.rar](https://xentaxbackup.github.io/file/14832_DRAGON_QUEST_11.rar)
## Post #2
- Username: Zolodei
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 19, 2017 2:15 am
- Post datetime: 2018-09-10T17:40:39+00:00
- Post Title: DRAGON QUEST XI

Can be closed, the script from [here](https://zenhax.com/viewtopic.php?f=9&t=1005&start=520#p38235) helped
